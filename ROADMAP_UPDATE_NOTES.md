# Roadmap Update - Based on Codebase Exploration

**Date:** January 30, 2026
**Exploration Results:** Trial Cancellation, Auto-Play, Microdrama Filter, Dynamic Home Screen

---

## 🔍 Key Findings from Codebase

### 1. Trial/Subscription Cancellation Flow **ALREADY EXISTS**

**What Exists:**
- ✅ Full cancellation flow with reason selection (`TrialCancelReasonSelectionScreen`, `SubCancelReasonSelectionScreen`)
- ✅ Exit survey with feedback options (`TrialFeedbackOptions` - id, reason, sourceUrl, mediaType)
- ✅ Retention dialogs: `PauseTrialBenefitDialog`, `PauseTrialBenefit2Dialog`, `PauseTrialPrideDialog` (with media)
- ✅ Pause/Resume mandate API: `pausePlan()`, `resumePlan()` in `PaymentRepository`
- ✅ Analytics tracking: `trial_cancellation_initiated`, `save_attempt` events
- ✅ A/B testing: `trialCancellationCopiesId`, `subCancellationCopiesId` from Remote Config
- ✅ Mandate status constants: `mandate_revoked_psp`, `mandate_pause_in_app`

**What's MISSING (The Real Problem):**
- ❌ **PSP-Initiated Cancellation Tracking:** Most users cancel mandate from PhonePe/Paytm apps directly
- ❌ **PSP-Specific API Integration:** `pausePlanPaytm()`, `pausePlanPhonePe()` are empty placeholders
- ❌ **Deep Linking from PSP:** No way to intercept PSP cancellations and redirect to Stage app
- ❌ **PSP Cancellation Detection:** No backend webhook/polling to detect external mandate revocation
- ❌ **Save Mechanism for PSP Cancellations:** Users who cancel via PSP never see retention dialogs

**Updated Focus for Initiative #1:**
- Track when users cancel mandate from PhonePe/Paytm (not Stage app)
- Implement PhonePe/Paytm API integration for mandate pause/resume detection
- Add deep links from PSP apps back to Stage app when cancellation initiated
- Push notification when PSP cancellation detected: "Wait! Before you go..."
- Show retention dialog when user returns from PSP cancellation

---

### 2. Auto-Start Next Video Feature **ALREADY EXISTS**

**What Exists:**
- ✅ `WatchNextNudge` widget: Shows 60 seconds before video ends
- ✅ Auto-redirect with 5-second countdown timer
- ✅ Similar content horizontal list with auto-play
- ✅ `onVideoEnd()` method: Automatically plays next episode/season
- ✅ Offline auto-play support for downloaded content
- ✅ Watch Next configuration: `isWatchNextInLineEnabled`, `nudgeStartTime`
- ✅ Analytics: `logWatchNextWidgetView()`, `logWatchNextWidgetClicked()`

**Impact:**
- This feature is LIVE and working to reduce trial cancellation
- No changes needed

---

### 3. Microdrama Filter **ALREADY EXISTS**

**What Exists:**
- ✅ `FilterType.microdrama` enum in content filter
- ✅ Microdrama filter chip in `DynamicHomeContentFilter`
- ✅ Top 10 Microdramas section (`top10Microdramas`)
- ✅ Trending Microdramas section (`trendingMicrodramas`)
- ✅ Genre-wise microdramas (`GenreWiseContents.microdramas`)
- ✅ Filter toggle logic in `ContentFilterCubit`
- ✅ Integration tests: `micro_drama_content_filter_test.dart`
- ✅ UI keys: `ContentFilterKeys.microDramaFilter`

**What's MISSING:**
- ❌ Better visibility/promotion (filter exists but users don't find it)
- ❌ Onboarding tooltip for first-time users
- ❌ Dedicated microdrama home section (currently buried in filters)
- ❌ "New Badge" on microdrama filter is configurable but not prominent

**Updated Focus for Initiative #2:**
- Improve microdrama filter visibility (move higher in UI)
- Add first-time user onboarding tooltip
- Promote microdrama filter with "New Badge" and animation
- Add "Drama Shorts" label with icon (already defined, just needs better placement)

---

### 4. Genre-Based Discovery Rows **ALREADY EXIST - REMOVE THIS TASK**

**What Exists:**
- ✅ Dynamic home screen with layout API (`/v25/home/getHomeLayout`)
- ✅ Genre-based rows: "Trending in Action", "Popular Dramas", "Comedy Picks", "Thriller Highlights"
- ✅ Personalized ordering: `layoutMap` with variant support
- ✅ "Quick Picks" row: `TrendingContentHome` widget
- ✅ Mood-based rows: `GenreWiseContents` with preferredType
- ✅ Dynamic row generation: `DynamicRowsBloc` fetches from unique URLs
- ✅ Content categorization: By genre ID, genre name, content type, trending status

**All mentioned features are LIVE:**
- Genre rows: ✅ Exist
- Personalized order: ✅ Exists
- Quick Picks: ✅ Exists
- Mood-based: ✅ Exists

**Action:**
- **REMOVE Initiative #4 completely**
- OR replace with a different consumption/discovery task

---

## 📝 Updated Roadmap Structure

### P0 - Critical (3 Initiatives)

**Initiative #1: PSP Mandate Cancellation Prevention**
- Week 1-3 (12 days)
- Focus: Track and prevent cancellations initiated from PhonePe/Paytm apps
- Phase 1: PSP cancellation detection (backend webhook + polling)
- Phase 2: Deep link + retention dialog when PSP cancellation detected
- Phase 3: PhonePe/Paytm API integration for pause/resume
- Expected Impact: -40% of PSP cancellations (majority of total cancellations)

**Initiative #2: Microdrama Discovery Promotion**
- Week 2-4 (6 days, reduced from 8)
- Focus: Improve visibility of existing microdrama filter
- Add onboarding tooltip, better placement, prominent "New Badge"
- Expected Impact: 22% → 30% (+8pp)

**Initiative #3: Watchlist Expansion**
- Week 3-5 (10 days)
- No changes needed (this one is correct)

**Initiative #4: REMOVED**
- Genre rows already exist, replace with new task

---

## 🎯 Recommended New Initiative #4

**Option A: Content Completion Nudges (New)**
- Encourage users to finish started content
- Push notifications for 10-80% watched content
- Expected Impact: +5pp video completion rate

**Option B: D0 Engagement Boost (New)**
- Target users who activate trial but don't watch
- Curated content recommendations within 6 hours
- Expected Impact: D0 consumption 66% → 72% (+6pp)

**Option C: Payment Success Celebration Enhancement**
- Already exists but could be optimized
- Add content recommendations immediately after payment
- Expected Impact: D1 retention +4pp

---

## 🔄 Files to Update

1. **FINAL_ROADMAP.html** - Update Initiative #1, #2, remove #4, add new #4
2. **README.md** - Update initiative descriptions to match
3. **Create:** `PSP_CANCELLATION_ANALYSIS.md` - Technical details for Initiative #1

---

**Next Steps:**
1. User approval on updated Initiative #1 focus (PSP cancellations)
2. User approval on removing Initiative #4 (genre rows exist)
3. User selects replacement for Initiative #4 from options above
4. Update HTML + README with corrections
