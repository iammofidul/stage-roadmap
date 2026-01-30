# Stage App: 3-Month Product Roadmap

**Status:** ✅ FINAL VERSION (Streamlined - Medal Removed, User Types Added)
**Date:** January 30, 2026
**Last Update:** January 30, 2026 (Removed non_subscriber orchestration + medal features, added user types)
**Team:** 7 Flutter Developers

---

## 📂 **USE THIS FILE**: FINAL_ROADMAP.html

This is the **final, streamlined roadmap** with:
- ✅ No medal feature (removed per user request)
- ✅ No non_subscriber orchestration (you're handling mutual exclusivity)
- ✅ **User Types (Subscription Status)** for each initiative
- ✅ **Amplitude Chart Links** for each initiative
- ✅ Clear WHY for each initiative (business rationale)
- ✅ HOW it improves funnels (expected impact)

---

## 📊 Current Funnel State (Amplitude - Last 30 Days)

| Funnel | Current Rate | Chart ID | Amplitude URL | Problem |
|--------|--------------|----------|---------------|---------|
| **Paywall Conversion** | **27.5%** | `lidh9clj` | https://app.amplitude.com/analytics/STAGEAPP/chart/lidh9clj/edit/g5xiauf9 | 🚨 BIGGEST BOTTLENECK - 72.5% drop-off |
| **Trial D7 Retention** | **3.3%** | `0fdjwdly` | https://app.amplitude.com/analytics/STAGEAPP/chart/0fdjwdly/edit/fvk09nv2 | 💔 CATASTROPHIC - 96.7% churn |
| **D0 Consumption** | **66-84%** | `p9n3yedy` | https://app.amplitude.com/analytics/STAGEAPP/chart/p9n3yedy/edit/dfwca13u | 📉 DECLINING - Dropped from 90% to 66% |
| **90% Video Completion** | **55%** | `olmj7eh1` | https://app.amplitude.com/analytics/STAGEAPP/chart/olmj7eh1/edit/ns7sqp1f | ⚠️ Half abandon videos before completion |
| **Home → Playback** | **64%** | `qxatpaww` | https://app.amplitude.com/analytics/STAGEAPP/chart/qxatpaww/edit/ngf90r69 | 🏠 36% land but don't watch within 10 min |
| Login Success | 86% | `kj3fgru8` | https://app.amplitude.com/analytics/STAGEAPP/chart/kj3fgru8/edit/yn2i822k | ✅ Strong - no optimization needed |

---

## 🎯 10 Initiatives (3 Months)

### **Month 1: Analytics Foundation (Weeks 1-4)**

| # | Initiative | User Types | Chart IDs | Why | Impact |
|---|------------|------------|-----------|-----|--------|
| **1** | **Journey Tracking Enhancements** (2-3 days, 1 dev) | `all users` | `lidh9clj`, `0fdjwdly` | ✅ 90% complete (user_id, amplitude_id, campaign data in ALL events). Add 3 properties: feature_source, trial_start_date, session_id | Enable conversion attribution + cohort analysis |
| **2** | **Video Completion Optimization** (8-11 days, 2 devs) | `trial_active`, `subscription_active` | `olmj7eh1` | ✅ Resume/Auto-play/Skip Intro exist. Add: Buffering optimization (24s→3s) + Progress badges on thumbnails | 55% → 62% (+7pp) |
| **3** | **Special Access Analytics Enhancements** (4 days, 1 dev) | `non_subscriber` | Dashboard: `2t19oz3v` + Charts: `pizolrn2`, `bokepue2` | ✅ Feature complete. Add 4 missing analytics: completion events, trial day, claim speed, payment correlation | Understand why SA has +4pp activation BUT +1.67pp cancellation |

**Month 1 Goals:** D0 consumption 66% → 70%, Video completion 55% → 62%

---

### **Month 2: Conversion Optimization (Weeks 5-8)**

| # | Initiative | User Types | Chart IDs | Why | Impact |
|---|------------|------------|-----------|-----|--------|
| **4** | **Spin Wheel → Payment Optimization** | `non_subscriber` | `lidh9clj` | Unknown conversion rate | +3pp spin → payment |
| **5** | **Boost Variant Optimization** | `trial_active` | `0fdjwdly`, `p9n3yedy` | Random boost variant shown | Smart selection (+4pp engagement) |
| **6** | **Home Discovery Optimization** | `all users` | `qxatpaww` | 36% land but don't watch | 64% → 69% (+5pp) |
| **7** | **Resume Trial Incentives** | `trial_over`, `subscription_over` | `0fdjwdly` | Basic banners not compelling | -3pp trial churn |
| **8** | **Post-Payment Engagement** | `trial_active` (new) | `gy3b4s96` | D1 retention only 27% | 27% → 33% (+6pp) |

**Month 2 Goals:** Home → playback 64% → 69%, Trial D1 retention 27% → 33%

---

### **Month 3: Scale & Personalization (Weeks 9-12)**

| # | Initiative | User Types | Chart IDs | Why | Impact |
|---|------------|------------|-----------|-----|--------|
| **9** | **Internal Monitoring Dashboard** | `all` (team tool) | All charts (`kj3fgru8`, `0fdjwdly`, `p9n3yedy`, `olmj7eh1`, `gy3b4s96`, `qxatpaww`, `lidh9clj`) | Need real-time funnel visibility | Faster issue detection |
| **10** | **Lapsed User Win-Back** | `trial_over`, `subscription_over` | `0fdjwdly`, `gy3b4s96` | No re-engagement for lapsed | Win back 10% lapsed users |

**Month 3 Goals:** Paywall 27.5% → 32%, Home → playback 69% → 74%

---

## 🔑 Key Strategic Pieces

### **1. Journey Tracking Enhancements (#1) - MINIMAL ADDITIONS**
**Status:** ✅ 90% Complete - Infrastructure already exists

**What Already Exists (No Build Needed):**
- ✅ user_id in ALL events (automatic via getUserCommonPropertyNewInfra)
- ✅ amplitude_id tracking (Amplitude SDK automatic)
- ✅ device_id in ALL events
- ✅ event_id (unique per event)
- ✅ campaign_data (campaign_name, af_channel, ad_set_name, ad_group_name) in ALL events
- ✅ deeplink + deeplink_channel in ALL events
- ✅ subscription_status in ALL events
- ✅ Session tracking (Amplitude SDK trackingSessionEvents enabled)

**What's Missing (3 Properties - 2-3 days, 1 developer):**
1. ❌ feature_source property (which feature drove conversion: special_access, spin_wheel, direct)
2. ❌ trial_start_date property (for cohort analysis: D0, D1, D7 retention by trial start date)
3. ❌ session_id property (explicit session ID for custom analysis - low priority)

**Why It Matters:** These 3 properties unlock conversion attribution ("Does SA increase retention?") and cohort analysis ("D7 retention by trial start date"). Without them, we can't prove which features work. With them, Month 2-3 optimizations are data-driven.

**Implementation:** Add 3 properties to /lib/utils/events/events_util.dart (getUserCommonPropertyNewInfra method). No new infrastructure needed.

### **2. Boost Variant Optimization (#5) - TRIAL USER ENGAGEMENT**
**Problem:** Trial users get random boost variant (Commitment vs Discovery)

**Solution:** Behavior-based selection:
- Early dropoff (exit <50% through) → Commitment Boost
- Completion (finish 90%+) → Discovery Boost

**Why It Matters:** Right boost at right time → better trial engagement → reduced D7 churn

### **3. Resume Trial Incentives (#7) - WIN BACK LAPSED**
**Problem:** 96.7% of trial users churn by D7, no compelling re-engagement

**Solution:**
- Personalized discount offers
- "What's New" content highlighting
- Watch history reminders

**Why It Matters:** Even winning back 10% of lapsed = +9.1K retained users

### **4. Special Access Deep-Dive (#3) - UNDERSTAND THE PARADOX**
**Status:** ✅ Feature is COMPLETE with comprehensive implementation

**What Already Exists (No Rebuild Needed):**
- ✅ 6+ analytics events (offer_view, offer_click, content_view, widget_view, start_watching, etc.)
- ✅ Content ID, slug, and type tracking
- ✅ Comprehensive state machine (initial → claimed → consumption → terminal)
- ✅ Full repository/API integration (GET, POST claim, PATCH state update)
- ✅ Source tracking (deeplink, banner, home_platter, exit_sheet, etc.)
- ✅ All UI components (floating banner, expandable banner, offer screen, exit sheet, etc.)

**What's Missing (4 Analytics Dimensions - 4 days, 1 developer):**
1. ❌ Video completion events (special_access_video_watched, special_access_video_completed)
2. ❌ Trial day tracking (trial_day_claimed, account_age_days properties)
3. ❌ Claim speed metrics (interaction_session_id, time_to_claim_seconds)
4. ❌ Payment correlation (claim_id, link to payment events within 7 days)

**Current Data (Jan 25-30, 2026):**
- ✅ SA users activate trials at **9.15%** vs Non-SA at **5.15%** (+4pp, +77.7% relative)
- ⚠️ SA users cancel at **3.84%** vs Non-SA at **2.17%** (+1.67pp, +77% relative)
- ❓ Net effect unclear: More activations but also more cancellations

**Critical Questions (Answerable After Analytics Enhancements):**
1. WHY do SA users cancel more? (Low intent? Poor content? Bad timing?)
2. Which SA content types retain users best?
3. When in trial journey is SA most effective? (Day 0, 1, 3?)
4. What's the net impact on D7 retention and LTV?

**Why It Matters:** Before scaling SA to more users, we must understand if it's a leaky bucket. The +4pp activation is meaningless if users churn faster. This investigation prevents scaling a feature that hurts unit economics.

**Effort:** Only 4 days of analytics enhancements (not a 2-week rebuild). Feature already works in production.

**Data Sources:**
- Dashboard: [TR - SA MahaPunaraJanam (2t19oz3v)](https://app.amplitude.com/analytics/STAGEAPP/dashboard/2t19oz3v)
- Charts: `pizolrn2` (Trial Rate), `bokepue2` (Trial Cancellation Rate)

---

## 🎯 User Type Definitions

| Subscription Status | Description | Target Features |
|-------------------|-------------|-----------------|
| `non_subscriber` | No payment, no trial | Special Access, Spin Wheel |
| `trial_active` | In trial period (D0-D7) | Boost variants, Video optimization |
| `subscription_active` | Paying subscriber | Video optimization, Home discovery |
| `trial_over` | Trial ended, didn't convert | Resume Trial incentives, Win-back |
| `subscription_over` | Subscription expired | Resume Sub incentives, Win-back |

---

## 📈 Expected Results (3 Months)

| Metric | Baseline | Target | Improvement |
|--------|----------|--------|-------------|
| **Paywall Conversion** | 27.5% | 32% | +4.5pp (+16% relative) |
| **D0 Consumption** | 66% | 75% | +9pp (+14% relative) |
| **Trial D7 Retention** | 3.3% | 6% | +2.7pp (+82% relative) |
| **90% Video Completion** | 55% | 62% | +7pp (+13% relative) |
| **Home → Playback** | 64% | 74% | +10pp (+16% relative) |

---

## 💰 Business Impact (Conservative Estimate)

**Current State** (900K monthly paywall views):
- Trial activations: 248K
- D7 retained: 8.2K

**After 3 Months:**
- Trial activations: 288K (+40K)
- D7 retained: 17.3K (+9.1K)

**Revenue Impact:**
- +1,820 paid subscribers/month (20% of retained users convert)
- +₹910K MRR (~$11K MRR)
- **~₹10.9M ARR (~$131K ARR)**

---

## 🔧 Recent Changes (Jan 30, 2026)

### What Was Removed:
- ❌ **Initiative #2:** Engagement Orchestrator (non_subscriber mutual exclusivity already being handled)
- ❌ **Initiative #4:** Medal System Deep Analytics (medal feature removed per user request)
- ❌ **Initiatives #12, #13, #15:** All medal-related Month 3 initiatives

### What Was Added:
- ✅ **User Types:** Every initiative now shows target subscription statuses
- ✅ **Amplitude Links:** Direct links to relevant funnels for each initiative
- ✅ **Streamlined:** 10 focused initiatives (down from 15)

### Why This Matters:
- Roadmap is leaner and more focused
- Clear user segmentation for each feature
- Direct data access via Amplitude links
- No duplicate work (orchestration already handled, medal removed)

---

## 🚀 Start Week 1 (Monday)

**Immediate Actions:**
1. ✅ Review **FINAL_ROADMAP.html** with stakeholders
2. ⏳ Assign 2 devs to Initiative #1 (Journey Tracking) - Week 1-2
3. ⏳ Assign 2 devs to Initiative #2 (Video Completion) - starts Week 2
4. ⏳ Assign 2 devs to Initiative #3 (Special Access) - starts Week 3

**Week 1 Goal:** Complete journey tracking foundation

---

## 📂 Files in This Directory

| File | Status | Description |
|------|--------|-------------|
| **FINAL_ROADMAP.html** | ✅ **USE THIS** | Streamlined roadmap with user types + Amplitude links |
| README.md | ✅ Current | This file - quick reference |
| SUBSCRIPTION_STATUS_CORRECTION.md | ℹ️ Reference | Subscription status mapping from codebase analysis |
| CHANGES_SUMMARY.md | ℹ️ Reference | History of initial corrections |
| ~~ACTIONABLE_ROADMAP.html~~ | ❌ Deprecated | Too technical |
| ~~REVISED_ROADMAP.html~~ | ❌ Deprecated | Before final corrections |
| ~~index.html~~ | ❌ Deprecated | Original roadmap |

---

## 📞 Questions?

**"Which initiative targets which users?"**
- Check the "User Types" column - every initiative clearly shows subscription statuses

**"Where's the Amplitude data?"**
- Chart IDs are shown in tables - access Amplitude dashboard directly to view charts

**"Why remove medal features?"**
- Per user request - medal feature removed from roadmap

**"Why remove orchestrator?"**
- Per user request - non_subscriber mutual exclusivity already being handled

**"How do we measure success?"**
- Every initiative has before → after metrics + direct Amplitude chart access

---

**Generated by:** Claude Code + Amplitude MCP Integration
**Version:** Streamlined (10 initiatives, medal removed, user types added)
**Last Updated:** January 30, 2026
**Status:** Ready for stakeholder review & execution
