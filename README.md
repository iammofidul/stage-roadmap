# Stage App: Priority-Based Product Roadmap

**Status:** ✅ OPTIMIZED V2 - Priority Levels + New Consumption Tasks
**Date:** January 30, 2026
**Last Update:** January 30, 2026 (Trial Cancellation as #1 P0 + Corrected existing features)
**Team:** 7 Flutter Developers

---

## 📂 **USE THIS FILE**: index.html (https://iammofidul.github.io/stage-roadmap/)

This is the **priority-based roadmap** with:
- ✅ **P0 (Critical): Trial Retention & Consumption** - Weeks 1-5 (Highest priority)
- ✅ **P1 (Important): Retention & Analytics** - Weeks 1-8 (Foundation)
- ✅ **P2 (Strategic): Growth & Scale** - Weeks 9-12 (Future optimization)
- ✅ **#1 P0 Task: Trial Cancellation Reduction** (3.0% → 1.5%, -50% reduction)
- ✅ **Optimized for Existing Features**: Improve Micro Drama row, Genre rows (not rebuild)
- ✅ **User Types** for every initiative
- ✅ **Amplitude Links** (No redundant chart IDs)
- ✅ **60-70% Effort Reduction** from original plan

---

## 🎯 Priority Breakdown

### **P0 - Critical: Trial Retention & Consumption (4 Initiatives)**

Focus: Reduce trial cancellation and drive content consumption

| # | Initiative | Users | Timeline | Impact | Amplitude Link |
|---|------------|-------|----------|--------|----------------|
| **1** | 🔥 **Trial Cancellation Reduction** | `trial_active` | Week 1-3 (10 days) | 3.0% → 1.5% (-50%) | [View Dashboard](https://app.amplitude.com/analytics/STAGEAPP/dashboard/2t19oz3v) |
| **2** | Micro Drama Discovery (Improve Existing) | `subscription_active` | Week 2-4 (8 days) | 22% → 30% (+8pp) | [View Funnel](https://app.amplitude.com/analytics/STAGEAPP/chart/7njdmw9s/edit/o0bzlcag) |
| **3** | Watchlist Expansion (My List + Notifications) | `subscription_active` | Week 3-5 (10 days) | 3.8x conversion lift | [View Funnel](https://app.amplitude.com/analytics/STAGEAPP/chart/7njdmw9s) |
| **4** | Genre-Based Discovery Rows (Improve Existing) | `all users` | Week 4-5 (5 days) | 64% → 69% (+5pp) | [View Funnel](https://app.amplitude.com/analytics/STAGEAPP/chart/qxatpaww/edit/ngf90r69) |

**P0 Goals:** Trial cancellation 3.0% → 1.5% (-50%), Micro drama starts 22% → 30%, Watchlist adds 2.91% → 8%, Home → playback 64% → 69%

---

### **P1 - Important: Retention & Analytics Foundation (4 Initiatives)**

Focus: Fix analytics gaps and understand retention patterns

| # | Initiative | Users | Timeline | Impact | Amplitude Link |
|---|------------|-------|----------|--------|----------------|
| **5** | Journey Tracking Enhancements (3 properties) | `all users` | Week 1 (2-3 days) | Enable attribution | [Paywall Funnel](https://app.amplitude.com/analytics/STAGEAPP/chart/lidh9clj/edit/g5xiauf9) |
| **6** | Special Access Analytics Enhancements | `non_subscriber` | Week 3 (4 days) | Understand paradox | [SA Dashboard](https://app.amplitude.com/analytics/STAGEAPP/dashboard/2t19oz3v) |
| **7** | Resume Trial Incentives (Optimization) | `trial_over`, `subscription_over` | Week 7-8 (3-5 days) | -3pp trial churn | [Trial Retention](https://app.amplitude.com/analytics/STAGEAPP/chart/0fdjwdly/edit/fvk09nv2) |
| **8** | Post-Payment Engagement (Enhancement) | `trial_active (new)` | Week 8 (2-3 days) | +6pp D1 retention | [D1 Retention](https://app.amplitude.com/analytics/STAGEAPP/chart/gy3b4s96) |

**P1 Goals:** Enable data-driven decisions, Understand Special Access paradox, Optimize existing retention features

---

### **P2 - Strategic: Growth & Personalization (2 Initiatives)**

Focus: Scale what works and win back lapsed users

| # | Initiative | Users | Timeline | Impact | Amplitude Link |
|---|------------|-------|----------|--------|----------------|
| **9** | Spin Wheel → Payment Optimization | `non_subscriber` | Week 9-10 (8 days) | +3pp conversion | [Paywall Funnel](https://app.amplitude.com/analytics/STAGEAPP/chart/lidh9clj/edit/g5xiauf9) |
| **10** | Lapsed User Win-Back | `trial_over`, `subscription_over` | Week 11-12 (10 days) | Win back 10% lapsed | [Trial Retention](https://app.amplitude.com/analytics/STAGEAPP/chart/0fdjwdly/edit/fvk09nv2) |

**P2 Goals:** Paywall 27.5% → 30.5%, Win back 10% of lapsed users

---

## 💡 Key Focus: Trial Cancellation Reduction (#1 P0 Priority)

### 🔥 Initiative #1: Trial Cancellation Reduction
**Why This is #1 Priority:** Trial cancellation is the biggest retention leak - fixing this directly saves revenue

**Current Data (Amplitude):**
- Trial cancellation rate: 3.0-3.84%
- Special Access users: 3.84% cancel (HIGHER than non-SA: 2.17%)
- ~3,000 trials cancelled per month
- Lost revenue: ₹1.5M/month (~$18K/month)

**The Problem:**
- We don't track WHEN users cancel (D0? D3? D7?)
- We don't know WHY they cancel
- No save mechanisms when they try to cancel

**What We'll Build (2 Phases):**

**Phase 1 - Analytics (Week 1, 3 days):**
- Track cancellation day (trial_day_cancelled)
- Track cancellation source (settings vs profile)
- Track content consumed before cancel
- Exit survey: "Why are you canceling?" (4 options)

**Phase 2 - Save Mechanisms (Week 2-3, 7 days):**
- Cancellation confirmation dialog with benefits reminder
- Pause trial option (pause for 3-7 days instead of cancel)
- D0-D2 engagement nudges (if low content consumption)
- Pre-cancellation offer (Special Access for 2 more days)

**Impact:**
- Trial cancellation: 3.0% → 1.5% (-50% reduction)
- Saved trials: +483/month
- Additional paid subscribers: +96/month (20% conversion)
- Revenue impact: **+₹48K MRR (~$576/month)**

**Amplitude Link:** https://app.amplitude.com/analytics/STAGEAPP/dashboard/2t19oz3v

---

### 📺 Initiative #2: Micro Drama Discovery (Improve Existing Row)
**Current Data (Amplitude):** 22.32% conversion (land_on_home → playback_started for micro drama)
- 243,768 users landed → 54,402 started micro drama
- Declining trend: 16% (early Jan) → 12-15% (mid Jan)

**What Exists:** Micro Drama row already exists on home screen

**What We'll Improve:**
- Better positioning (move closer to top, after hero banner)
- "⚡ Quick Watch" badges on thumbnails
- Auto-play trailers on hover (2-3 seconds)
- Curated subcategories: "Trending", "Romance", "Action"
- Push notifications for micro drama fans (behavioral trigger)

**Impact:** 22% → 30% (+8pp, +6,500 users/month)

**Amplitude Link:** https://app.amplitude.com/analytics/STAGEAPP/chart/7njdmw9s/edit/o0bzlcag

---

### 🔖 Initiative #3: Watchlist Expansion (My List + Notifications)
**Current Data (Amplitude):** Exit intent popup shows **3.8x lift** in watchlist conversion
- Users who saw popup: **10.61%** add to watchlist (2,159 users → 229 added)
- Users without popup: **2.91%** add to watchlist (65,006 users → 1,891 added)

**The Problem:** Watchlist is hidden - only 2,159 users saw popup in 30 days

**What We'll Build:**
- "My List" row on home (like Netflix)
- Quick "+My List" button on all content cards
- Watchlist reminder notifications (48h after adding)
- Badge counter "🔖 My List (5)"
- Weekly digest notifications

**Impact:** Watchlist adds 2.91% → 8% (+5pp), Watchlist → playback 40% → 60% (+20pp)

**Amplitude Link:** https://app.amplitude.com/analytics/STAGEAPP/chart/7njdmw9s

---

### 🎭 Initiative #4: Genre-Based Discovery Rows (Improve Existing Filters)
**What Exists:** Genre filters for Shows, Movies, Genre already exist

**The Problem:** Filters require user action - most users don't explore

**What We'll Improve:**
- Convert filters into discoverable rows on home screen
- "Popular in Action", "Trending Romance", "Top Drama Series"
- Genre-specific hero banners (rotate by genre)
- Smart genre recommendations based on watch history

**Impact:** Home → playback 64% → 69% (+5pp)

---

## 📊 Current Funnel State (Amplitude - Last 30 Days)

| Funnel | Current Rate | Amplitude Link | Priority |
|--------|--------------|----------------|----------|
| **🔥 Trial Cancellation** | **3.0-3.84%** | [View Dashboard](https://app.amplitude.com/analytics/STAGEAPP/dashboard/2t19oz3v) | **P0 - Critical** |
| **Micro Drama Starts** | **22%** | [View](https://app.amplitude.com/analytics/STAGEAPP/chart/7njdmw9s/edit/o0bzlcag) | P0 - Consumption |
| **Watchlist (with popup)** | **10.6%** | [View](https://app.amplitude.com/analytics/STAGEAPP/chart/7njdmw9s) | P0 - Consumption |
| **Home → Playback** | **64%** | [View](https://app.amplitude.com/analytics/STAGEAPP/chart/qxatpaww/edit/ngf90r69) | P0/P2 |
| **Trial D7 Retention** | **3.3%** | [View](https://app.amplitude.com/analytics/STAGEAPP/chart/0fdjwdly/edit/fvk09nv2) | P1 - Retention |
| **Paywall Conversion** | **27.5%** | [View](https://app.amplitude.com/analytics/STAGEAPP/chart/lidh9clj/edit/g5xiauf9) | P2 - Growth |
| **D0 Consumption** | **66-84%** | [View](https://app.amplitude.com/analytics/STAGEAPP/chart/p9n3yedy/edit/dfwca13u) | Baseline |
| **90% Video Completion** | **55%** | [View](https://app.amplitude.com/analytics/STAGEAPP/chart/olmj7eh1/edit/ns7sqp1f) | Baseline |

---

## 💰 Effort Optimization Summary

| Priority | Tasks | Optimized Estimate | Impact |
|----------|-------|-------------------|--------|
| **P0** Critical | 4 tasks | **33 days** (10 + 8 + 10 + 5) | Trial retention + Consumption boost |
| **P1** Important | 4 tasks | **14-18 days** | Analytics foundation + Retention |
| **P2** Strategic | 2 tasks | **18 days** (8 + 10) | Growth & Win-back |

**Total Estimate:** ~65-69 developer-days for 10 initiatives

**Key Optimizations:**
- **Micro Drama**: Improve existing row (not rebuild) - saves 5 days
- **Genre Rows**: Convert existing filters (not new feature) - saves 3 days
- **Resume watching notifications**: Already exists for video lock screen - REMOVED
- **Video buffering**: REMOVED (not priority)
- **Internal dashboard**: REMOVED (not priority)

**Focus:** Fix trial cancellation first (biggest revenue leak), then optimize existing features for engagement.

---

## 🎯 User Type Definitions

| Subscription Status | Description | Target Features |
|-------------------|-------------|-----------------|
| `non_subscriber` | No payment, no trial | Special Access, Spin Wheel |
| `trial_active` | In trial period (D0-D7) | Video optimization, Resume watching notifications, Post-payment |
| `subscription_active` | Paying subscriber | Video optimization, Micro drama, Watchlist, Resume watching notifications |
| `trial_over` | Trial ended, didn't convert | Resume Trial incentives, Win-back |
| `subscription_over` | Subscription expired | Resume Sub incentives, Win-back |

---

## 📈 Expected Results (3 Months)

| Metric | Baseline | Target | Improvement |
|--------|----------|--------|-------------|
| **🔥 Trial Cancellation** | 3.0-3.84% | 1.5% | **-1.5pp (-50% relative)** |
| **Micro Drama Starts** | 22% | 30% | **+8pp (+36% relative)** |
| **Watchlist Adds** | 2.91% | 8% | **+5pp (+175% relative)** |
| **Home → Playback** | 64% | 69% | +5pp (+8% relative) |
| **Trial D7 Retention** | 3.3% | 6% | +2.7pp (+82% relative) |
| **Paywall Conversion** | 27.5% | 30.5% | +3pp (+11% relative) |

---

## 💰 Business Impact (Conservative Estimate)

**Current State** (900K monthly paywall views):
- Trial activations: 248K/month
- Trial cancellations: 7,440/month (3.0%)
- D7 retained: 8.2K/month

**After 3 Months:**

**P0 Impact - Trial Retention:**
- Trial cancellations: 3.0% → 1.5% (-50%)
- Saved trials: +483/month
- Additional paid subscribers from saved trials: +96/month
- Revenue from saved trials: **+₹48K MRR (~$576/month)**

**P0 Impact - Consumption:**
- Micro drama viewers: +6,500/month
- Active watchlist users: +3,900/month
- Improved home → playback: +5pp

**P1 + P2 Impact:**
- Trial activations: 288K (+40K from better conversion)
- D7 retained: 17.3K (+9.1K from better engagement)
- Additional paid subscribers: +1,820/month

**Total Revenue Impact:**
- New paid subscribers: +1,916/month (1,820 + 96)
- Total MRR increase: **+₹958K MRR (~$11.5K MRR)**
- **Annual Revenue: ~₹11.5M ARR (~$138K ARR)**

**Key Insight:** Trial Cancellation Reduction alone contributes ₹48K/month (5% of total impact) with just 10 days of effort.

---

## 🔧 What Changed in Final Version?

### ✅ Added (High Priority)
1. **Trial Cancellation Reduction as #1 P0 Task:**
   - 3.0% → 1.5% (-50% reduction)
   - 2-phase approach: Analytics tracking + Save mechanisms
   - Expected impact: +₹48K MRR/month
   - Amplitude data: SA users cancel 77% more (3.84% vs 2.17%)

2. **Priority Levels:** P0 (Critical), P1 (Important), P2 (Strategic)

3. **User Types:** Every initiative shows target subscription statuses

### ❌ Removed (Already Exist or Not Priority)
1. **Resume Watching Notifications:** Already exists for video player lock screen
2. **Video Buffering & Progress UI:** Not priority, removed completely
3. **Internal Monitoring Dashboard:** Not priority, removed completely
4. **Chart IDs:** Removed from display (kept Amplitude links only)

### 🔄 Changed to "Improve Existing" (Not Rebuild)
1. **Micro Drama Row:** Already exists on home - just improve positioning and badges
2. **Genre Filters:** Already exist - convert to discoverable rows on home
3. **Watchlist:** API exists - add My List row + notifications

### 📊 Corrected Structure
- **P0:** 4 tasks (Trial Cancellation, Micro Drama, Watchlist, Genre Rows)
- **P1:** 4 tasks (Journey Tracking, SA Analytics, Resume Trial, Post-Payment)
- **P2:** 2 tasks (Spin Wheel, Lapsed Users) - reduced from 4

---

## 📂 Files in This Directory

| File | Status | Description |
|------|--------|-------------|
| **index.html** | ✅ **USE THIS** | Priority-based roadmap (P0/P1/P2) - Live at https://iammofidul.github.io/stage-roadmap/ |
| **psp-cancellation-prevention-wireframe.html** | ✅ Active | PSP Cancellation Prevention wireframe with WhatsApp templates |
| README.md | ✅ Current | This file - quick reference |
| SUBSCRIPTION_STATUS_CORRECTION.md | ℹ️ Reference | Subscription status mapping |
| CHANGES_SUMMARY.md | ℹ️ Reference | History of initial corrections |

---

## 🚀 Start Week 1 (Immediate Actions)

**P0 - CRITICAL (Parallel Execution):**
1. 🔥 **Assign 2 devs to Initiative #1 (Trial Cancellation Reduction)** - Week 1-3 (HIGHEST PRIORITY)
   - Week 1: Analytics tracking (3 days)
   - Week 2-3: Save mechanisms (7 days)
2. ⏳ Assign 2 devs to Initiative #2 (Micro Drama Discovery) - starts Week 2
3. ⏳ Assign 2 devs to Initiative #3 (Watchlist Expansion) - starts Week 3

**P1 - Foundation (Quick Win):**
4. ⏳ Assign 1 dev to Initiative #5 (Journey Tracking) - Week 1 (2-3 days)

**Week 1 Goals:**
- ✅ Complete Journey Tracking (2-3 days, 1 dev)
- ✅ Complete Trial Cancellation Analytics (3 days, 2 devs)
- ✅ Begin Trial Cancellation Save Mechanisms (Week 2)

**Why Trial Cancellation First?**
- Biggest revenue leak (3,000 cancellations/month = ₹1.5M lost)
- Quick wins in Week 1 (analytics)
- Immediate impact in Week 2-3 (save mechanisms)
- Foundation for all retention improvements

---

## 📞 Questions?

**"Why is Trial Cancellation #1 priority?"**
- Biggest revenue leak: 3,000 cancellations/month = ₹1.5M lost revenue
- Immediate impact: -50% reduction = +₹48K MRR with just 10 days effort
- Foundation for retention: Understanding why users cancel informs all future retention work

**"Why improve existing features instead of building new?"**
- Micro Drama row already exists - just needs better positioning
- Genre filters already exist - convert to discoverable rows
- Resume watching notifications already exist for video lock screen
- 60% faster execution by optimizing what works

**"Where's the Amplitude data?"**
- Every initiative has direct Amplitude link (no redundant chart IDs)
- Trial cancellation: SA users cancel 77% more (3.84% vs 2.17%)
- Micro drama: 22% start rate (declining trend)
- Watchlist: 3.8x lift from exit popup (10.6% vs 2.91%)

**"How do we measure success?"**
- Every initiative has before → after metrics + Amplitude link
- P0 metrics tracked weekly (trial cancellation, micro drama starts, watchlist adds)
- P1 metrics enable data-driven decisions
- P2 metrics tracked monthly

---

**Generated by:** Claude Code + Amplitude MCP Integration
**Version:** FINAL (Trial Cancellation #1 P0 + Corrected existing features)
**Last Updated:** January 30, 2026
**Status:** ✅ Ready for execution - Trial Cancellation starts Week 1
