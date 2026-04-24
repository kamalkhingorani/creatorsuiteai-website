# Internal reference: launch, IP, and monetization strategy (2026)

**Purpose:** Durable notes for future work. **Not legal advice.** Confirm fees, classes, and policies with official sources before acting.

**Cursor rule:** `.cursor/rules/LAUNCH-IP-STRATEGY-REFERENCE.mdc` — agents should read this file for context and **amend this Markdown** when launch/IP/monetization decisions change (unless you say not to for a specific change).

**Constraint:** Do **not** change live code, footers, or store listings without **express user consent**. **Real** copyright diary numbers may appear in production UI only when confirmed from official Copyright Office receipts (see §2).

---

## 1. Trademark (India)

- **Intent:** File **TM application** (e.g. TM-A) **early** relative to large-scale public marketing, to secure an early **filing/priority date** where applicable.
- **Classes:** Often **42** (SaaS/services); **9** may apply for downloadable software — confirm with TM counsel / IP India for exact marks and goods/services description.
- **Fees / startup rebate:** Treat any ₹ figure as **indicative** — verify on **IP India** and Startup India / DPIIT rules for **eligibility**.
- **Symbols:** **™** for unregistered / applied-for marks (practice per Indian TM norms); **®** only when **registered**. Verify with counsel.
- **Reality check:** “First to file tomorrow beats you” is **oversimplified** — **prior use** and **opposition** can still matter.

---

## 2. Copyright (India)

- **Literary + artistic:** Two strands (source code + UI) as discussed for **CreatorSuite AI** marketing site / app deposits.
- **Public notices:** © line in footers is fine when **owner name** and **year** are accurate.
- **Diary / application numbers in About / app:** Only use **real** numbers from **official** Copyright Office correspondence — **never** placeholder examples in production.
- **On file (Apr 2026):** Applications filed with Copyright Office — **SW-15649/2026-CO** (*CreatorSuite AI — Source Code*); **AT-15643/2026-CO** (*CreatorSuite AI — User Interface and Design*), filed **6 April 2026**. UI copy describes **applications filed**; certificates follow examination.

---

## 3. Monetization and distribution (hybrid / phased)

- **Direct website:** **Razorpay** (India domestic). **FCY / international:** **Dodo Payments** (MoR) preferred for hosted checkout vs Lemon Squeezy/Paddle — verify **current** fees, settlement (e.g. UPI payouts to India), and KYC. Marketing HTML uses `DODO_CHECKOUT_FCY` URLs when set; until then, Buy buttons fall back to **app** checkout (today: Razorpay USD for international users in-app).
- **Web billing UX (user decision, Feb 2026):** Do **not** add an “Inside India / Outside India” **manual toggle** for checkout or displayed subscription currency. Use **automatic geo-detection** (same idea as `setGlobalPricing` on creatorsuiteai.org: INR only when country resolves to **IN**, otherwise FCY such as USD). **Rationale:** reduces incentive to self-select “India” for lower INR prices when international pricing differs.
- **Indus Appstore / Paytm Mini:** Optional channels — verify **each platform’s** billing rules and revenue share.
- **Google Play:** **Policy-sensitive:** Avoid assuming “subscribe on website only, app is read-only” is always compliant for **digital** features — **Google Play Billing** and **Developer Policy** apply; review **current** terms for your app category before routing payments off-Play.
- **Phasing:** Rough sequence acceptable: web revenue → TM filing → additional stores → Play when policy/tech ready. Timelines (e.g. “Day 15”) are **flexible** — use **milestones**, not fixed days unless agreed.

---

## 4. Copyright deposit artifact (repo)

- **`COPYRIGHT_DEPOSIT_LITERARY_CreatorSuite_AI.md`** — literary excerpt for **static** site (`index.html`, `creatorsuite.html`, `legal.html`); operational address in PART B may be redacted in deposit only; **live `legal.html` unchanged** unless user requests.

---

## 5. Implementation policy (Cursor / collaborators)

- **No** unsolicited edits to working code, billing flows, or legal copy.
- **Any** footer / About / TM / copyright text changes require **explicit user approval** and **exact** final strings (and **real** government numbers only).

---

## 6. When to revisit

- After **real** TM application number and **copyright** diary/certificate details are received.
- Before **Google Play** submission: billing model vs **current** Play policy.
- Before changing **public** legal pages (Privacy, Terms, contact address).

---

## 7. CreatorCanvas website / product (status)

- **Copyright diary numbers:** Reflected in `legal.html`, marketing footers, app Legal (Licenses) + Settings footer — **real** diary nos. from Copyright Office receipts (Apr 2026).
- **Dodo vs app for FCY:** Static sites point international visitors to **Dodo checkout URLs** when `DODO_CHECKOUT_FCY` is populated in page script; otherwise **https://app.creatorsuiteai.org/membership** (Razorpay USD order path today). **Webhooks:** `POST /api/webhooks/dodo` handles **`payment.succeeded`**, **`subscription.created`**, and **`subscription.active`** (verify `DODO_PAYMENTS_WEBHOOK_SECRET`; metadata / `DODO_PRODUCT_*_ID` for plan resolution).
- **Review Guardian “stealth”:** Optional future change (hide card) — not part of this update.
- **Footer legal name:** Confirm **Creator Canvas** vs GST/Udyam spelling on storefronts when GSTIN is live.
- **GST timeline:** Treat external date predictions as aspirational until confirmed.
- **™ in product:** Marketing `index.html` / `creatorsuite.html`, parent `creatorcanvas.org` pages, static `legal.html` (#trademarks), and app **Legal** (Licenses → Trademarks) + **Settings** footer + login / checkout display name use **Creator Canvas™**, **CreatorSuite™**, **CreatorSuite AI™** as claimed marks (applications may be pending — confirm with counsel before changing wording).
- **Payment routing (intent):** **India:** Razorpay (test → live when bank/GST ready). **International FCY:** Dodo (hosted checkout + webhooks) when wired; **in-app** `/api/payments` still uses **Razorpay orders for USD** until optionally replaced with Dodo session creation for non-IN users.
- **Distribution idea (user):** After website subscription is stable, **may** remove in-app purchase CTAs and sell membership **only on the website** to reduce store commission — **must** validate **Google Play / App Store** policies for digital goods in your category before relying on web-only billing.
