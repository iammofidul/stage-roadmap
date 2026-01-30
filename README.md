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

| Funnel | Current Rate | Chart ID | Problem |
|--------|--------------|----------|---------|
| **Paywall Conversion** | **27.5%** | `six7gquy` | 🚨 BIGGEST BOTTLENECK - 72.5% drop-off |
| **Trial D7 Retention** | **3.3%** | `1y0ta29d` | 💔 CATASTROPHIC - 96.7% churn |
| **D0 Consumption** | **66-84%** | `qfskz34k` | 📉 DECLINING - Dropped from 90% to 66% |
| **90% Video Completion** | **55%** | `q2dd1ib2` | ⚠️ Half abandon videos before completion |
| **Home → Playback** | **64%** | `hux9brmh` | 🏠 36% land but don't watch within 10 min |
| Login Success | 86% | `uscs40hn` | ✅ Strong - no optimization needed |

---

## 🎯 10 Initiatives (3 Months)

### **Month 1: Analytics Foundation (Weeks 1-4)**

| # | Initiative | User Types | Chart IDs | Why | Impact |
|---|------------|------------|-----------|-----|--------|
| **1** | **Cross-Feature Journey Tracking** | `all users` | `1y0ta29d`, `six7gquy` | Can't track users across features | Enables all future optimizations |
| **2** | **Video Completion Optimization** | `trial_active`, `subscription_active` | `q2dd1ib2` | 45% abandon before 90% | 55% → 62% (+7pp) |
| **3** | **Special Access Funnel Tracking** | `non_subscriber` | `six7gquy`, `qfskz34k` | Don't know if SA works | Measure effectiveness for scaling |

**Month 1 Goals:** D0 consumption 66% → 70%, Video completion 55% → 62%

---

### **Month 2: Conversion Optimization (Weeks 5-8)**

| # | Initiative | User Types | Chart IDs | Why | Impact |
|---|------------|------------|-----------|-----|--------|
| **4** | **Spin Wheel → Payment Optimization** | `non_subscriber` | `six7gquy` | Unknown conversion rate | +3pp spin → payment |
| **5** | **Boost Variant Optimization** | `trial_active` | `1y0ta29d`, `qfskz34k` | Random boost variant shown | Smart selection (+4pp engagement) |
| **6** | **Home Discovery Optimization** | `all users` | `hux9brmh` | 36% land but don't watch | 64% → 69% (+5pp) |
| **7** | **Resume Trial Incentives** | `trial_over`, `subscription_over` | `1y0ta29d` | Basic banners not compelling | -3pp trial churn |
| **8** | **Post-Payment Engagement** | `trial_active` (new) | `1y0ta29d` | D1 retention only 27% | 27% → 33% (+6pp) |

**Month 2 Goals:** Home → playback 64% → 69%, Trial D1 retention 27% → 33%

---

### **Month 3: Scale & Personalization (Weeks 9-12)**

| # | Initiative | User Types | Chart IDs | Why | Impact |
|---|------------|------------|-----------|-----|--------|
| **9** | **Internal Monitoring Dashboard** | `all` (team tool) | All charts | Need real-time funnel visibility | Faster issue detection |
| **10** | **Lapsed User Win-Back** | `trial_over`, `subscription_over` | `1y0ta29d` | No re-engagement for lapsed | Win back 10% lapsed users |

**Month 3 Goals:** Paywall 27.5% → 32%, Home → playback 69% → 74%

---

## 🔑 Key Strategic Pieces

### **1. Unified Journey Tracking (#1) - FOUNDATION**
**Problem:** Can't track users from special access → spin wheel → payment

**Solution:** Add `trial_journey_id` to link all events across features

**Why It Matters:** Without this, Month 2-3 optimizations are impossible. This unlocks data-driven decisions.

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
