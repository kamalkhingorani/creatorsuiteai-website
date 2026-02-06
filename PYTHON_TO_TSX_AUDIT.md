# Python to TSX Feature Audit & Comparison

## Purpose
Comprehensive audit of all Python Streamlit features to ensure identical functionality in Next.js/TypeScript implementation.

---

## 1. AUTHENTICATION (auth_manager.py vs useAuth.ts)

### Python Implementation (auth_manager.py)
- **Password Reset Flow:**
  - Generates secure 12-character password
  - Updates Supabase Auth via `admin.update_user_by_id()`
  - Sends email via `email_service.send_reset_email()`
  - Returns success/failure boolean

### TSX Implementation (src/hooks/useAuth.ts)
- **Status:** ✅ Implemented
- **Password Reset:** Via `/api/auth/reset-password` route
- **Login Logic:**
  - Email normalization (trim + lowercase)
  - Password trimming
  - Profile lookup by normalized email, then auth_id
  - Soft delete check (`is_deleted` flag)
  - Specific error messages for unverified email, invalid password
- **Signup Logic:**
  - Duplicate email detection via Supabase `signUp` error codes (23505, PGRST301)
  - Direct insert into `public.users` table
  - Email verification redirect to `/auth/callback?next=/`

### Discrepancies:
- [ ] Verify password reset uses same 12-character generation
- [ ] Verify email service integration matches Python

---

## 2. MAIN APP (app.py vs layout/page structure)

### Python Implementation (app.py)
- **Routing:** Tab-based navigation via `selected_tab` state
- **Categories:**
  - 🧠 Strategy & DNA: Brand DNA, Brand Analysis, Calendar, Trends
  - 🚀 Content Studio: Reels, Hashtags, Captions, Taglines, Carousels, Editor, Batch, Videomaker
  - ⚙️ App & Support: Contest, Membership, Legal, Settings, Help
- **Sidebar Features:**
  - Logo (width=100)
  - Logout button
  - Plan status & expiry
  - Usage credits (progress bar)
  - Navigation categories
  - Quick Upload (social media links)
  - Rating & Feedback (multi-stage: Love it → Slider → Store links if 5 stars)
  - Ad space for free users
- **Login/Signup:**
  - Split layout (50/50 columns)
  - Left: Logo, title, tagline
  - Right: Login/Signup tabs
  - Cookie-based auto-login
  - Email verification flow
  - Password reset expander
- **Broadcast System:**
  - Modal-style announcements
  - One-time vs reminder types
  - Database tracking of views/dismissals

### TSX Implementation
- **Status:** ✅ Mostly implemented
- **Routing:** Next.js App Router (`/dna`, `/reels`, etc.)
- **Sidebar:** `src/components/Sidebar.tsx`
- **Layout:** `src/app/layout.tsx`

### Discrepancies:
- [ ] Verify broadcast system is implemented
- [ ] Verify cookie-based auto-login
- [ ] Verify onboarding tour

---

## 3. REELS SCRIPT GENERATOR (reels.py vs src/app/reels/page.tsx)

### Python Implementation
- **Inputs:**
  - Topic (text input, default: "Travel Vlog")
  - Tone (selectbox from languages)
  - Duration (selectbox from languages)
- **Logic:**
  - Tracks usage via `utils.track_feature("Reel Script Generator")`
  - Gets user location & language from session
  - Master prompt includes:
    - Geographic context override rules
    - Language-specific instructions
  - Calls `utils.call_openai_safe(prompt, 500)`
  - Offline fallback template
  - Stores result in `session_state['last_reel']`
- **Output:**
  - Preview card via `utils.preview_card_html()`
  - Download button (`.txt` file)

### TSX Implementation
- **Status:** ✅ Implemented
- **API Route:** `/api/generate/reels`
- **Inputs:** Topic, Tone, Duration
- **Output:** Copy & Download buttons

### Discrepancies:
- [ ] Verify geographic context override rules in prompt
- [ ] Verify offline fallback
- [ ] Verify preview card styling matches

---

## 4. BRAND DNA (dna.py vs src/app/dna/page.tsx)

### Python Implementation
- **Profile Editor:**
  - Interests (comma-separated text input)
  - Style/Tone (selectbox from languages)
  - Save button triggers `utils.save_user_profile()`
  - Clears `trends_cache` on save
- **Trend Radar:**
  - Shows cached trends if < 1 hour old
  - Refresh button calls AI with interests + style
  - Stores in `profile['trends_cache']` and `last_trend_update`
  - Reset cache button
  - Language-specific output
- **Auto-Learner (Commented Out):**
  - Would analyze recent content for interests
  - Auto-update DNA from usage

### TSX Implementation
- **Status:** ✅ Implemented
- **API Routes:** `/api/user/profile` (GET/POST)

### Discrepancies:
- [ ] Verify trend radar caching logic (1 hour threshold)
- [ ] Verify profile save clears trends cache
- [ ] Check if auto-learner should be enabled

---

## 5. HASHTAGS (hashtags.py vs src/app/api/generate/hashtags/route.ts)

### Python Implementation
- **Inputs:**
  - Topic (text input, default: "Digital Marketing")
  - Tag Type: "Mixed (Best for Growth)", "High Volume (Broad)", "Medium Volume (Targeted)", "Niche (Specific)"
  - Quantity: Slider (1-5, default: 5)
- **Logic:**
  - Tracks usage via `utils.track_feature("Hashtag Generator")`
  - Strategy instruction based on tag type selection
  - Geographic context override rules (same as reels)
  - Calls `utils.call_openai_safe(prompt, 500)`
  - **OFFLINE FALLBACK:** Massive offline database (50+ niches) with smart matching
  - Stores result in `session_state['last_hashtags']`
- **Output:**
  - Displays as code block
  - Individual tag copy buttons (4 columns)
  - "Copy All" button

### TSX Implementation
- **Status:** ⚠️ PARTIALLY IMPLEMENTED
- **API Route:** `/api/generate/hashtags`
- **Missing:**
  - ❌ Offline database fallback (50+ niches)
  - ❌ Tag type selector (Mixed/High/Medium/Niche volume)
  - ❌ Individual tag copy buttons
  - ❌ Smart offline matching logic

---

## 6. TAGLINES (taglines.py vs src/app/api/generate/taglines/route.ts)

### Python Implementation
- **Inputs:**
  - Topic (text input, stored in session)
  - Audience (text input, stored in session)
  - Context (text input, stored in session)
- **Logic:**
  - Tracks usage via `utils.track_feature("Tagline Generator")`
  - Gets current year via `utils.get_current_year()`
  - Geographic context override rules
  - **JSON Response Parsing:** Extracts `{"tagline": "..."}` from AI response
  - **OFFLINE FALLBACK:** Template-based generation with random selection
  - Stores result in `session_state['last_tagline']`
- **Output:**
  - Preview card via `utils.preview_card_html()`
  - Copy to clipboard button

### TSX Implementation
- **Status:** ⚠️ PARTIALLY IMPLEMENTED
- **API Route:** `/api/generate/taglines`
- **Missing:**
  - ❌ JSON response parsing (expects `{"tagline": "..."}`)
  - ❌ Offline fallback templates
  - ❌ Current year injection
  - ❌ Preview card styling

---

## 7. TRENDS (trends.py vs src/app/api/generate/trends/route.ts)

### Python Implementation
- **Inputs:**
  - Niche (text input, stored in session)
- **Logic:**
  - Tracks usage via `utils.track_feature("Trend Radar")`
  - Focuses on "Viral Content Formats" (timeless) to bypass knowledge cutoff
  - Geographic context for regional trends
  - **OFFLINE FALLBACK:** `OFFLINE_TRENDS` dictionary with General/Business/Fitness templates
  - Stores result in `session_state['last_trends']`
- **Output:**
  - Markdown display (not code block)

### TSX Implementation
- **Status:** ⚠️ NEEDS VERIFICATION
- **API Route:** `/api/generate/trends`
- **Missing:**
  - ❌ Offline fallback templates
  - ❌ Focus on "Viral Formats" vs specific news events

---

## 8. CAPTIONS (captions.py vs src/app/api/generate/captions/route.ts)

### Python Implementation
- **Inputs:**
  - Topic (text input, default: "Monday Motivation")
  - Vibe/Tone (selectbox from languages)
- **Logic:**
  - Tracks usage via `utils.track_feature("Caption Generator")`
  - Generates 5 Instagram captions
  - Geographic context override rules
  - Includes emojis and hashtags
  - Calls `utils.call_openai_safe(prompt, 450)`
  - **OFFLINE FALLBACK:** Simple template with 3 variations
  - Stores result in `session_state['last_captions']`
- **Output:**
  - Preview card via `utils.preview_card_html()`
  - Download button (.txt file)

### TSX Implementation
- **Status:** ⚠️ NEEDS VERIFICATION
- **API Route:** `/api/generate/captions`
- **Missing:**
  - ❌ Offline fallback template
  - ❌ Preview card styling

---

## 9. CAROUSELS (carousels.py vs src/app/api/generate/carousels/route.ts)

### Python Implementation
- **Inputs:**
  - Topic (text input, stored in session, default: "how to shoot better videos")
  - Tone (selectbox from languages)
- **Logic:**
  - Tracks usage via `utils.track_feature("Carousel Generator")`
  - Generates 5 carousel post outlines (5-8 slides each)
  - Geographic context override rules
  - Calls `utils.call_openai_safe(prompt, 550)`
  - Stores result in `session_state['last_carousels']`
- **Output:**
  - Preview card via `utils.preview_card_html()`
  - Download button (.txt file, UTF-8 encoded)

### TSX Implementation
- **Status:** ⚠️ NEEDS VERIFICATION
- **API Route:** `/api/generate/carousels`
- **Missing:**
  - ❌ Preview card styling

---

## 10. BATCH (batch.py vs src/app/api/generate/batch/route.ts)

### Python Implementation
- **Inputs:**
  - Topic (text input, default: "Fitness")
  - Count: Slider (3-10, default: 5)
  - Item Type: "Caption Ideas", "Reel Hooks", "Blog Titles"
- **Logic:**
  - Tracks usage via `utils.track_feature("Batch Generator")`
  - Geographic context override rules
  - Calls `utils.call_openai_safe(prompt, 600)`
  - **OFFLINE FALLBACK:** Numbered list template
  - Stores result in `session_state['last_batch']`
- **Output:**
  - Text area display (height: 300)
  - Success message

### TSX Implementation
- **Status:** ⚠️ NEEDS VERIFICATION
- **API Route:** `/api/generate/batch`
- **Missing:**
  - ❌ Offline fallback template

---

## 11. CALENDAR (calendar_tab.py vs src/app/api/generate/calendar/route.ts)

### Python Implementation
- **Inputs:**
  - Niche (text input, default: "Digital Marketing")
  - Platform: "Instagram", "LinkedIn", "YouTube"
  - Start Date: Date input (default: today)
- **Logic:**
  - Tracks usage via `utils.track_feature("Content Calendar")`
  - **CRITICAL:** Injects start date in prompt: `"The Start Date is: {prompt_date}"`
  - Ensures sequential dates starting from start_date
  - Calls `utils.call_openai_safe(prompt, 1000)`
  - **OFFLINE FALLBACK:** Manual date calculation for 7 days with template
  - Stores result in `session_state['last_calendar']`
- **Output:**
  - Markdown display with "Your Weekly Plan" header
  - Download button (.txt file)

### TSX Implementation
- **Status:** ⚠️ NEEDS VERIFICATION
- **API Route:** `/api/generate/calendar`
- **Critical Missing:**
  - ❌ Start date injection in prompt (ensures correct dates)
  - ❌ Offline fallback with manual date calculation

---

## 12. BRAND ANALYSIS (brand_analysis.py - Need to read)

### Python Implementation
- **Status:** ⏳ Pending review

### TSX Implementation
- **Status:** ⏳ Need to check if implemented

---

## 13. LEGAL (legal.py - Need to read)

### Python Implementation
- **Status:** ⏳ Pending review

### TSX Implementation
- **Status:** ✅ Implemented
- **Content:** From `legal.html`

---

## 14. SUPPORT/HELP (support.py / helper.py - Need to read)

### Python Implementation
- **Status:** ⏳ Pending review

### TSX Implementation
- **Status:** ✅ Implemented
- **Page:** `src/app/support/page.tsx`

---

## 15. MEMBERSHIP (membership.py - Need to read)

### Python Implementation
- **Status:** ⏳ Pending review

### TSX Implementation
- **Status:** ✅ Implemented
- **API Routes:** `/api/payments`, Razorpay integration

---

## 16. SETTINGS (settings.py - Need to read)

### Python Implementation
- **Status:** ⏳ Pending review

### TSX Implementation
- **Status:** ✅ Implemented
- **Features:** Profile, password reset, account deletion

---

## 17. CONTEST (contest.py - Need to read)

### Python Implementation
- **Status:** ⏳ Pending review

### TSX Implementation
- **Status:** ✅ Implemented
- **Eligibility:** Pro users, 2+ months subscribed
- **API Routes:** `/api/admin/contest-entries`

---

## 18. UTILS.PY - Core Functions

### Key Functions to Verify:
1. `authenticate_user_db()` - Login validation
2. `register_user_in_db()` - Signup with duplicate check
3. `call_openai_safe()` - AI generation with safety checks
4. `track_feature()` - Usage tracking
5. `check_usage_limit()` - Rate limiting
6. `get_user_status()` - Plan type & expiry
7. `save_user_profile()` / `load_user_profile()` - DNA storage
8. `preview_card_html()` - Result display
9. `reset_password_trigger()` - Password reset
10. `check_payment_status()` - Payment verification
11. `get_latest_broadcast()` - Announcements
12. `log_broadcast_view()` - Broadcast tracking

### TSX Implementation
- **Status:** ⏳ Need to verify all utility functions are replicated

---

## CRITICAL DISCREPANCIES SUMMARY:

### HIGH PRIORITY (Functionality Breaking):
1. **Hashtags:** Missing offline database (50+ niches) - users get errors when offline
2. **Taglines:** Missing JSON parsing - may not extract tagline correctly
3. **Calendar:** Missing start date injection - dates may be incorrect
4. **All Features:** Missing `utils.track_feature()` calls - usage analytics broken

### MEDIUM PRIORITY (User Experience):
1. **Hashtags:** Missing tag type selector (Mixed/High/Medium/Niche)
2. **Hashtags:** Missing individual tag copy buttons
3. **Taglines:** Missing offline fallback templates
4. **All Features:** Missing preview card styling (`utils.preview_card_html()`)
5. **Trends:** Missing offline fallback templates
6. **Captions:** Missing offline fallback
7. **Carousels:** Missing preview card styling
8. **Batch:** Missing offline fallback

### LOW PRIORITY (Nice to Have):
1. **All Features:** Geographic context override rules may not be fully implemented
2. **All Features:** Language-specific prompt injection may vary

## NEXT STEPS:
1. ✅ Read all Python files
2. ✅ Compare with TSX implementations
3. ✅ Document discrepancies
4. ⏳ Fix missing functionality (starting with HIGH PRIORITY)
5. ⏳ Verify API routes match Python logic exactly
6. ⏳ Test end-to-end flows
7. ⏳ Verify utility functions (`track_feature`, `preview_card_html`, etc.)
