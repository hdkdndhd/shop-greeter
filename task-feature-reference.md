# Task → Feature Reference

**Kaise use karo:** Yeh file kisi bhi naye chat mein upload karo, uske saath apna task/question poochho (jaise "yeh kaam kaise hoga"). Claude is file ko padh ke batayega kaunsa feature/tool use hoga — agar yahan already listed hai to seedha, nahi to naya reasoning karke.

**Zaroori niyam (Claude ke liye):** Koi bhi tool/feature "available hai" ya "yeh kaam karega" bolne se pehle, agar uncertainty ho to pehle verify karo (jaise ToolSearch se, ya seedha try karke) — guess karke confidently mat bolo, phir baad mein correct mat karo. Agar koi feature is specific session mein available nahi hai (jaise browser tool), toh honestly bolo, overclaim mat karo.

---

## Confirmed mappings

| Task | Feature(s) | Note |
|---|---|---|
| Web se current info/trends dhundna | WebSearch | Sirf public web pages ke snippets deta hai — kisi platform ka internal/live data (jaise Amazon ka search-suggest) nahi deta |
| Kisi specific webpage ka content padhna/summarize karna | WebFetch | URL dena zaroori hai |
| Website par live interact karna (click, scroll, form fill, live page dekhna) | Browser tool (Claude in Chrome / built-in browser) — **check availability har session mein alag ho sakti hai, ToolSearch se verify karo** | Agar available nahi hai, WebSearch/WebFetch hi fallback hai, jo weak hai is kaam ke liye |
| Code likhna/edit karna is repo mein | Read, Write, Edit, Bash | Standard coding tools |
| Lambi research jisme multiple sources compare karne hain | deep-research skill (agar available ho) ya khud WebSearch multiple queries | |
| PDF padhna/banana/edit karna | `pdf` skill | |
| Word doc (.docx) banana/edit karna | `docx` skill | |
| Excel/spreadsheet (.xlsx) kaam | `xlsx` skill | |
| PowerPoint (.pptx) deck banana | `pptx` skill | |
| Chart/graph/dashboard banana | `dataviz` skill | |
| Interactive web page / artifact banana jo user dekh sake | Artifact tool | |
| Kisi recurring/scheduled kaam ko automate karna | `/loop`, Claude Routines (ScheduleWakeup/CronCreate), ya headless mode | Interval limits hote hain (usually min 1 hour for Routines) |
| GitHub PR/issue se kaam | mcp__github__* tools (jab connected ho) | |
| Google Docs/Sheets/Slides banana/edit karna | Google Workspace skill/connector | |
| Kisi specific platform (jaise Runway, HeyGen) ko Claude mein use karna | `feature-dhundhne-wala` skill | |
| Business task ke liye sahi connector/MCP dhundna | `platform-dhundhne-wala` skill | |
| Naya skill banana | `skill-creator` skill | |

## Honest limitations (baar-baar yaad rakhne wali baatein)

- **Amazon/Flipkart jaisa live marketplace data** (live search-suggest, real-time trending) — WebSearch isko directly nahi de sakta, sirf third-party blogs milte hain jo outdated/unreliable ho sakte hain. Sirf live browser access se asli data milta hai.
- Har session mein tools alag available ho sakte hain (jaise browser tool kabhi hota hai, kabhi nahi) — **pehle verify karo, phir bolo**.
- Yeh file static hai — Claude ke naye features automatically add nahi hote isme (woh automation hataya gaya tha kyunki usse real value nahi mil rahi thi).

---

*Naye task-feature mappings yahan manually add kar sakte ho jab koi naya pattern confirm ho jaye.*
