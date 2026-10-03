# Task → Feature Playbook (Har Kaam ke liye — KDP ho ya na ho)

**Kaam kaise karta hai ye document:** Har row ek "task" hai (jo kaam karna hai — kisi bhi domain mein, KDP ho ya bilkul alag), uske saamne likha hai kaunsa Claude feature/skill/tool use hoga, kitne feature combine karna padenge, aur kyun. Jab bhi naya kaam poocha jaye jo yaha list nahi hai, Claude yahi tarah se jawab dega aur neeche ek nayi row add kar dega — ye ek growing, general-purpose reference manual hai, sirf KDP tak limited nahi.

**Last updated:** 2026-10-03

**Format:** Task | Feature(s) zaroori | Kitne feature chahiye | Kyun (reasoning)

---

## SECTION A — KDP Business tasks

## 1. Amazon Keyword / Niche Research ("Amazon pe konse keyword trending hai")

**Feature(s) zaroori:**
1. **Web Search** (chat/Research mode) — base layer. Amazon khud public "trending keyword" API nahi deta, isliye web se third-party blogs, "Movers & Shakers" discussions, seller-forum trends scan karne padte hain.
2. **Claude in Chrome / Computer use / Browser use** — Amazon.com ko directly khol kar live search-bar autocomplete, "Customers also search for", category Best Sellers page dekhne ke liye. Pure text-search se Amazon ka live suggestion-data nahi milta — browser kholna zaroori hai.
3. **`kdp-niche-scorer` skill** (custom skill) — Titans/Amazon competitor data se demand, competition, opportunity, price ka score nikalta hai. Ye sabse directly relevant hai kyunki ye exactly isi kaam ke liye bana hai.
4. *(Optional, broader trend ke liye)* **`google-trends` skill** — agar sirf Amazon nahi, overall search-interest pattern bhi dekhna ho.

**Kitne feature chahiye:** Minimum **2** (Web Search + kdp-niche-scorer), poora/best result ke liye **3** (+ Claude in Chrome).

**Kyun:** Ek akela feature poora kaam nahi karta — Web Search sirf "baatein" deta hai (blogs/forums), browser dekhna "live Amazon data" deta hai, aur niche-scorer un dono ko ek structured score mein convert karta hai jo directly decision lene layak hota hai. Teeno mil kar "trending keyword → actual go/no-go niche decision" tak le jaate hain.

---

## 2. Cover Design banana

**Feature(s) zaroori:** `kdp-cover-builder` skill (exact spine-width formula, trim-size templates, bleed check) + Claude Design/Artifact (agar visual mockup bhi dekhna ho) ya existing Canva/ChatGPT design ko is skill ke through size-verify karna.

**Kitne feature chahiye:** 1 skill (`kdp-cover-builder`) — zyadatar kaam ye akela kar deta hai. Agar naye design se shuru karna ho to +1 (Claude Design/image tool).

**Kyun:** Cover ka size/spine-formula KDP-specific exact math hai — ye ek dedicated skill ka kaam hai, generic design tool galat size de sakta hai.

---

## 3. Listing likhna (title, subtitle, keywords, description, categories)

**Feature(s) zaroori:** `kdp-listing-writer` skill.

**Kitne feature chahiye:** 1 — ye skill already poora listing (title/subtitle/7 backend keywords/description/categories/publish-checklist) KDP rules ke andar bana deta hai.

**Kyun:** Single dedicated skill hi sufficient hai jab tak koi fresh niche-research data input chahiye ho (tab #1 wala combo pehले chalayenge, uska output ismein feed karenge).

---

## 4. Interior (coloring pages) ko print-ready banana

**Feature(s) zaroori:** `kdp-interior-builder` skill (ChatGPT designs → vector SVG + 300 DPI, paperback/hardcover PDF, shading/duplicate/page-count check).

**Kitne feature chahiye:** 1.

---

## 5. Amazon Ads set up/optimize karna

**Feature(s) zaroori:** `kdp-ads-guru` skill (campaign basics, search-term/placement report se negatives/bids/budget decide karna).

**Kitne feature chahiye:** 1, lekin agar live report file (CSV) hai to Files/Read tool bhi saath mein (skill khud wo use kar leta hai).

---

## 6. Publish se pehle final check

**Feature(s) zaroori:** `kdp-prepublish-guard` skill (files, size, listing rules, AI disclosure, trademark, price, weekly 2-title slot limit).

**Kitne feature chahiye:** 1.

---

## 7. Weekly business review

**Feature(s) zaroori:** `kdp-weekly-review` skill (KDP sales report + Ads report padh ke decisions, budget sheet update, next week plan).

**Kitne feature chahiye:** 1, input ke liye Files/Read tool (reports upload karne ke liye) saath mein.

---

## 8. Account-safety / suspension-risk check (naya — pichli KDP links research se)

**Feature(s) zaroori:** Koi dedicated skill abhi nahi hai is exact kaam ke liye — closest hai `kdp-prepublish-guard` (AI disclosure, trademark checks) + manual review via Web Search (official KDP policy pages) jaisa pehle is session mein kiya gaya tha (47-link research).

**Kitne feature chahiye:** 2 (`kdp-prepublish-guard` + Web Search for policy verification). Agar account already flag ho chuka ho to Web Search + Research mode (case studies/appeals ke liye).

**Kyun:** Ye naya identified gap hai — agar yeh kaam baar-baar aata hai, isके liye ek dedicated `kdp-account-safety` skill banana faydemand rahega (skill-creator se).

---

## SECTION B — General / Non-KDP tasks

*(Abhi khaali hai. Jaise hi koi non-KDP kaam poocha jayega — coding, writing, research, design, kuch bhi — uska entry yahan is section mein add hoga, Section A jaisi hi format mein.)*

---

*(Naye tasks (KDP ya non-KDP, kisi bhi domain ke) yahan automatically add honge jaise jaise naye kaam poochhe jaayenge, ya jab hourly release-notes watch naya relevant Claude feature detect kare.)*
