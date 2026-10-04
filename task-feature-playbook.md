# Task → Feature Playbook

**Kaam kaise karta hai ye document:** Har row ek "task" hai (jo kaam karna hai), uske saamne likha hai kaunsa Claude feature/skill/tool use hoga, kitne feature combine karna padenge, aur kyun. Jab bhi naya kaam poocha jaye jo yaha list nahi hai, Claude yahi tarah se jawab dega aur neeche ek nayi row add kar dega — ye ek growing reference manual hai.

**Last updated:** 2026-10-04

**Format:** Task | Feature(s) zaroori | Kitne feature chahiye | Kyun (reasoning)

---

## 1. Custom plugin ke andar multiple teammate-agents ko spawn/coordinate karna (naya — Claude Code 2.1.289, Oct 3 2026)

**Feature(s) zaroori:** Plugin/mod authoring API ka naya `agent.spawn` call (teammates ke liye), plus plugin hook events mein ab ek consistent `agent id` milta hai, aur `$.agent.list()` mein naye `idle`/`waiting` states bhi dikhte hain.

**Kitne feature chahiye:** 1 (ye sab ek hi plugin-authoring API surface ka hissa hai) — lekin isko use karne ke liye already ek custom plugin/mod likhne ki knowledge chahiye (`plugin-authoring` skill dekho).

**Kyun:** Agar koi apna khud ka plugin bana raha hai jisme multiple "teammate" agents ko spawn karke coordinate karna ho (jaise ek dashboard plugin jo background mein kai agents ka status track kare), to ye naya API exactly isi kaam ke liye hai — pehle plugin authors ko khud se agent-tracking state banana padta tha, ab engine khud consistent id aur status (idle/waiting) deta hai.

**Note:** 2.1.289 ka baaki poora release sirf internal bugfixes tha (sandbox rule matching, terminal rendering, plugin pane crashes, VSCode auth) — wo kisi specific "task" se map nahi hote, isliye unke liye alag entries nahi banayi gayi.

---

*(Naye tasks yahan automatically add honge jaise jaise naye kaam poochhe jaayenge.)*
