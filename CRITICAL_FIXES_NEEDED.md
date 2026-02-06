# Critical Fixes Required - Python to TSX Parity

## ✅ VERIFIED WORKING:
1. **Hashtags Offline Database** - ✅ Implemented in `hashtags/page.tsx` (full OFFLINE_DB)
2. **Usage Limits** - ✅ Implemented in `usageHelper.ts` (matches Python logic)
3. **Payment Webhook** - ✅ Implemented with HMAC verification
4. **Authentication** - ✅ Implemented with duplicate detection

## ❌ CRITICAL MISSING FUNCTIONALITY:

### 1. FEATURE TRACKING (HIGH PRIORITY)
**Python:** `utils.track_feature(feature_name)` logs to `feature_logs` table
**TSX:** ❌ NOT IMPLEMENTED - No tracking in any API route
**Impact:** Analytics broken, admin dashboard incomplete
**Fix:** Add tracking to all generation API routes

### 2. CALENDAR START DATE INJECTION (HIGH PRIORITY)
**Python:** Injects `"The Start Date is: {prompt_date}"` in prompt
**TSX:** ❌ MISSING - Dates may be incorrect
**Fix:** Add start date to prompt in `/api/generate/calendar/route.ts`

### 3. TAGLINES JSON PARSING (HIGH PRIORITY)
**Python:** Parses `{"tagline": "..."}` from AI response
**TSX:** ❌ MISSING - May not extract tagline correctly
**Fix:** Add JSON parsing in `/api/generate/taglines/route.ts`

### 4. PREVIEW CARD HTML (MEDIUM PRIORITY)
**Python:** `utils.preview_card_html()` with watermark logic
**TSX:** ❌ MISSING - No preview card styling
**Fix:** Create utility function or component

### 5. PROMO CODE REDEMPTION (HIGH PRIORITY)
**Python:** Complex logic in `promo.py` and `utils.redeem_code()`
**TSX:** ⚠️ NEEDS VERIFICATION
**Fix:** Verify redemption logic matches Python exactly

### 6. WATERMARK REMOVAL LOGIC (MEDIUM PRIORITY)
**Python:** `can_remove_watermark(email)` - checks paid plans only
**TSX:** ⚠️ NEEDS VERIFICATION
**Fix:** Verify watermark logic in editor/videomaker pages

### 7. GEOGRAPHIC CONTEXT OVERRIDE RULES (MEDIUM PRIORITY)
**Python:** RULE 1 & RULE 2 in all generation prompts
**TSX:** ⚠️ PARTIALLY IMPLEMENTED - Need to verify all routes
**Fix:** Ensure all generation routes have override rules

### 8. OFFLINE FALLBACKS (MEDIUM PRIORITY)
**Python:** Offline templates for trends, captions, taglines, batch, calendar
**TSX:** ❌ MISSING for most features
**Fix:** Add offline fallbacks to all generation routes

### 9. BRAND ANALYSIS (LOW PRIORITY)
**Python:** `brand_analysis.py` exists
**TSX:** ⚠️ NEEDS VERIFICATION - Check if implemented

### 10. EDITOR & VIDEOMAKER (HIGH PRIORITY)
**Python:** Full image editing and video compilation
**TSX:** ⚠️ NEEDS VERIFICATION - May not be implemented
**Fix:** Verify if these features exist in TSX

---

## IMPLEMENTATION PLAN:

### Phase 1: Critical Functionality (Do First)
1. Add `track_feature()` to all API routes
2. Fix calendar start date injection
3. Fix taglines JSON parsing
4. Verify promo code redemption
5. Verify watermark removal logic

### Phase 2: User Experience (Do Second)
1. Add preview card HTML utility
2. Add offline fallbacks to all routes
3. Verify geographic context rules
4. Add missing offline templates

### Phase 3: Feature Completeness (Do Third)
1. Verify Brand Analysis implementation
2. Verify Editor implementation
3. Verify Videomaker implementation
4. Final end-to-end testing

---

## EXTERNAL PLATFORM CONNECTIONS:

### Supabase:
- ✅ Auth (signup, login, verification)
- ✅ Database (users, feature_logs, payment_audit, etc.)
- ✅ Storage (if used)
- ⚠️ RLS Policies - Need verification

### Razorpay:
- ✅ Payment order creation
- ✅ Payment verification (HMAC)
- ✅ Webhook handling
- ⚠️ Subscription creation - Need verification

### Brevo (Email):
- ✅ Password reset emails
- ✅ Verification emails
- ⚠️ Subscription success emails - Need verification

### Groq (AI):
- ✅ API calls with fallback
- ✅ Model rotation
- ⚠️ Safety checks - Need verification

---

## NEXT: Start implementing fixes in order of priority.
