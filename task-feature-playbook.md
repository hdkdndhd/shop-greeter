# Task → Feature Playbook

**Kaam kaise karta hai ye document:** Har row ek "task" hai (jo kaam karna hai), uske saamne likha hai kaunsa Claude feature/skill/tool use hoga, kitne feature combine karna padenge, aur kyun. Jab bhi naya kaam poocha jaye jo yaha list nahi hai, Claude yahi tarah se jawab dega aur neeche ek nayi row add kar dega — ye ek growing reference manual hai.

**Last updated:** 2026-10-03 (entry 1 added)

**Format:** Task | Feature(s) zaroori | Kitne feature chahiye | Kyun (reasoning)

---

## 1. YouTube pe trending keywords pata karna

**Feature(s) zaroori:** WebSearch + WebFetch (built-in tools). Optional: Claude in Chrome (logged-in YouTube Trending / YouTube Studio Research tab / Google Trends dekhne ke liye), aur Bash (agar YouTube Data API key ho to `videos?chart=mostPopular` call karne ke liye).

**Kitne feature chahiye:** Minimum ONE-TWO: WebSearch + WebFetch kaafi hai. Chrome tab sirf tab jab login-gated page (YouTube Studio) dekhna ho.

**Kyun:** WebSearch se current trending topics/keyword articles milte hain, WebFetch se specific page (Google Trends, YouTube trending page, keyword-tool pages) padh sakte hain. Exact search volume ke liye YouTube Studio Research ya Google Trends (YouTube Search filter) best source hain, jo browser se access honge. Koi dedicated installed skill ya connector confirm nahi hua, isliye wo list nahi kiya.

---
