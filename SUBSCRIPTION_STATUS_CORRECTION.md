# Roadmap Correction: Subscription Status Mapping

**Date:** January 30, 2026
**Reason:** Discovered actual subscription status targeting via codebase analysis

---

## 🔍 What Was Discovered

### Original Assumption (WRONG):
```
Medal > Special Access > Spin Wheel > Boost
(Features target different user types across the journey)
```

### Reality From Codebase (CORRECT):
```
Non-Subscribers (subscriptionStatus == 'non_subscriber'):
  ├── Medal ✓
  ├── Special Access ✓
  └── Spin Wheel ✓
  (All 3 compete for same users!)

Trial Active (subscriptionStatus == 'trial_active'):
  └── Boost (Commitment/Discovery variants)
  (Isolated, no competition)

Subscription Active (subscriptionStatus == 'subscription_active'):
  └── No engagement features
  (Already paying)
```

---

## 📋 Feature → Subscription Status Mapping

| Feature | Subscription Status | Code Location | Check Logic |
|---------|-------------------|---------------|-------------|
| **Medal** | `non_subscriber` | `trial_onboarding/logic/content_onboarding_cubit.dart:118` | `if (subscriptionStatus == SubscriptionStatusConstant.nonSubscriber)` |
| **Special Access** | `non_subscriber` | `special_access/logic/special_access_bloc.dart:32` | `if (subscriptionStatus != SubscriptionStatusConstant.nonSubscriber) return;` |
| **Spin Wheel** | `non_subscriber` | `spin_wheel/util/spin_wheel_deeplink_helper.dart:32` | `if (!SubscriptionStatusUtil.isNonTrialUser(context))` → checks `nonSubscriber` |
| **Boost (Commitment/Discovery)** | `trial_active` | `consumption/ui/mixins/consumption_exit_mixin.dart:165` | `if (!SubscriptionStatusUtil.isTrialUser(context))` → checks `trialActive` |

---

## 🚨 Critical Conflict Identified

### The Problem:
**Medal, Special Access, and Spin Wheel ALL check for the SAME subscription status** (`non_subscriber`).

This means:
- ❌ All 3 features can show simultaneously to a non-subscriber
- ❌ No built-in coordination between them
- ❌ Each feature independently checks subscription status
- ❌ User gets overwhelmed with multiple overlapping prompts

### Why This Matters:
If a non-subscriber opens the app:
1. Medal system wants to show onboarding
2. Special Access sees deeplink content and shows claim prompt
3. Spin Wheel sees eligible user and shows gamification

**All 3 triggers fire at once!**

---

## ✅ Corrected Orchestrator Design

### Original Design (Incorrect):
```
Priority: Medal > Special Access > Spin > Boost
(Assumed features target different user types)
```

### Corrected Design:
```
Orchestrator Logic by Subscription Status:

IF subscriptionStatus == 'non_subscriber':
  THEN coordinate:
    Priority 1: Medal (onboarding)
    Priority 2: Special Access (deeplink-driven)
    Priority 3: Spin Wheel (gamification)
  ENFORCE: 1 feature at a time + cooldown

IF subscriptionStatus == 'trial_active':
  THEN optimize:
    Select Boost variant (Commitment vs Discovery)
    Based on behavior (exit early vs completion)
  NO orchestration needed (only 1 feature)

IF subscriptionStatus == 'subscription_active':
  NO engagement features show
```

---

## 📝 Changes Made to Roadmap

### FINAL_ROADMAP.html - Initiative #2:

**1. Current Problem Section:**
- ✅ Changed: "Can user see medal prompt + special access + spin wheel simultaneously?"
- ✅ To: "Can non-subscriber see Medal + Special Access + Spin Wheel all at once? YES - All 3 target subscriptionStatus == 'non_subscriber'"

**2. Why Section:**
- ✅ Added: "Medal, Special Access, and Spin Wheel ALL target the SAME users (non-subscribers) causing direct conflicts"
- ✅ Added: "Boost is Isolated: Commitment/Discovery Boost only shows to `trialActive` users"

**3. What We'll Do Section:**
- ✅ Changed: "Create priority system: Medal > Special Access > Spin Wheel > Boost"
- ✅ To: "For Non-Subscribers: Create priority system Medal > Special Access > Spin Wheel (these 3 compete for same users)"
- ✅ Added: "For Trial Users: Optimize Boost variant selection (Commitment vs Discovery based on behavior)"

**4. Expected Impact Section:**
- ✅ Split impact by user segment (Non-Subscribers vs Trial Users)
- ✅ Clarified D0 Consumption is non-subscriber metric
- ✅ Clarified Trial Retention is trial user metric

### README.md:

**1. Initiative Summary Table:**
- ✅ Changed: "Features compete, confuse users"
- ✅ To: "Medal/SA/Spin all target non-subscribers (conflicts!)"

**2. Key Strategic Pieces:**
- ✅ Added discovery details: subscription status checks
- ✅ Restructured solution by user segment
- ✅ Clarified Boost is isolated (no orchestration needed)

**3. Boost Features Coordination (#7):**
- ✅ Changed: "Commitment & Discovery boost compete"
- ✅ To: "Trial users get random boost variant → Smart variant selection"

---

## 🎯 Impact on Implementation

### Month 1 - Orchestrator Implementation:

**High Priority:**
- Coordinate Medal/Special Access/Spin Wheel for `non_subscriber` users
- Prevent simultaneous display
- Enforce Day 0/1/2 sequencing

**Medium Priority:**
- Optimize Boost variant selection for `trial_active` users
- Behavior-based variant selection (not orchestration)

**Not Needed:**
- No orchestration for `subscription_active` (no features show)
- No coordination between non-subscriber features and trial features (different users)

---

## 💡 Key Learnings

### Lesson 1: Always Verify Assumptions with Code
- Initial assumption: Features target different user types
- Reality: 3 features target the same user type
- Method: Searched codebase for `SubscriptionStatusConstant` usage

### Lesson 2: Subscription Status is the Segmentation Key
- Features segment users by subscription status, not by journey stage
- This creates unexpected overlaps when multiple features target same status

### Lesson 3: "User Types" ≠ Journey Stages
- Don't assume Medal (early) → Spin (later) means different users
- Both target `non_subscriber` status regardless of journey position

---

## 📚 Reference

### Subscription Status Constants:
```dart
abstract class SubscriptionStatusConstant {
  static String trialActive = 'trial_active';
  static String subscriptionActive = 'subscription_active';
  static String nonSubscriber = 'non_subscriber';
  static String mandatePauseInApp = 'mandate_pause_in_app';
  static String trialMandateRevokedPsp = 'mandate_revoked_psp';
  static String subscriptionOver = 'subscription_over';
  static String trialOver = 'trial_over';
}
```

### Utility Methods Used:
```dart
// lib/utils/subscription_status_util.dart
static bool isNonTrialUser(BuildContext context) {
  return subscriptionStatus == SubscriptionStatusConstant.nonSubscriber;
}

static bool isTrialUser(BuildContext context) {
  return subscriptionStatus == SubscriptionStatusConstant.trialActive;
}
```

---

## ✅ Validation

Roadmap corrections validated against:
- ✅ Codebase analysis (Grep searches)
- ✅ Direct file reads of eligibility checks
- ✅ Subscription status constant definitions
- ✅ Utility method implementations

**Status:** Roadmap now accurately reflects codebase reality.

---

**Updated:** January 30, 2026
**Files Modified:**
- `FINAL_ROADMAP.html` (Initiative #2 corrections)
- `README.md` (Summary and Key Strategic Pieces)
- `SUBSCRIPTION_STATUS_CORRECTION.md` (This file)
