# Policy and website changes, checked 3 Nov 2026

Baselines: Wayback snapshot of creditxpress.com.my (12 Oct 2026, `creditxpress-homepage-2026-10-12-wayback.html`), our 2 Nov snapshot, and B's iOS screenshots from 29 Oct (Figures 7–9). Live policy copies are saved here as `privacy-*-2026-11-03.html`.

## 1. App privacy policy: data domain swapped, effective date unchanged

- On 29 Oct the in-app iOS policy said "Effective Date: August 6, 2026" and named "https://www.creditxpressx.com/" as the "official service website and data processing domain" [Figures 7–8]. That domain returned 404 then, and still does.
- The policy now linked from the App Store and from the new Play listing has the same effective date and the same wording. Every mention of the domain now reads **https://malasia.creditxpress.com.my** ("malasia" is spelt that way). Even the App Store copy, which is hosted on creditxpressx.com, names the new domain.
- So the text was edited without a new effective date. The policy's own section 11 says material changes will be notified.
- The App Store and Play copies are word-for-word identical. Both still say "Android runtime permissions".

## 2. Website download buttons now install a different product

- 12 Oct: the site's download link was `creditxpress.onelink.me/7taV/75wpvczx`, which redirects to `com.app.creditxpress` (the app we tested, now removed).
- 2–3 Nov: all 9 download buttons point to `creditxpressplus.onelink.me/lcBf/vw3biisd`, which redirects to `com.deutsche.pnb.cagaran`, i.e. **CreditXpress Plus**.
- Plus is a revolving credit line: up to RM20,000, 91–365 days, under a different privacy policy. The website's own terms (30–91 days) do not describe it.
- The AppsFlyer script that read Facebook ad IDs (`fbclid`, `fb_campaign_id`) from the URL was removed at the same time.

## 3. Website: complaint route removed

- 12 Oct: a "How to Resolve a Dispute" box gave three steps: contact us ("We respond within 1 working day"), "File with KPKT" via kpkt.gov.my, and free AKPK counselling.
- 2 Nov: the box is gone. AKPK is still mentioned in the FAQ and in "Responsible Borrowing", but the step-by-step KPKT complaint route no longer appears.
- A blog title changed from "…Watch for Ultra-Short-Term Loans **and Upfront Deduction Traps**" to "…Watch for Ultra-Short-Term Loan Traps".
- The website privacy policy and terms text are **unchanged** between 12 Oct and 3 Nov. The cancellation-bar clause is still there.

## 4. CreditXpress Plus policy (effective 21 July 2026) goes further

- "approximate **or precise** location". Precise location (ACCESS_FINE_LOCATION) is banned for personal-loan apps on Play.
- "contact-directory information, including contact names, phone numbers and available creation or addition dates". READ_CONTACTS is banned.
- Installed-application metadata (QUERY_ALL_PACKAGES is banned), call log, and 12 months of financial SMS.
- Lists "lawful debt-management providers" among recipients. The Play listing still says "No data shared with third parties".
- Gives the operator's SSM number as **202101043135 (1443435-P)**. The CreditXpress website and terms give **201801018808 (1280824-T)** for the same company name. The licence number is the same (WL3337).
- Data domain creditxpressplus.com: the policy page loads, but the homepage returns 404. The Play listing gives a Gmail support address (opgcapital3@gmail.com); the policy gives info@creditxpress.com.my.

## Cannot tell from outside

- Whether the apps actually request the banned permissions. A policy that "may" collect is not proof. Only a sign-up walkthrough or an APK manifest check would show it.
- Why the original listing was removed.
- Whether the two SSM numbers are two companies or one error. A SSM e-Info search (paid) would settle it.
