# 🌍 Arabic Dialect Detection System (Zero-Dependency)

A pure prompt-engineering technique for LLMs to auto-detect and respond in the user's Arabic dialect. No external API, no library — just structured instructions the LLM follows natively.

## Supported Dialects

| Dialect | Region | Keywords | Detection Strategy |
|---|---|---|---|
| Egyptian 🇪🇬 | مصر، السودان | كده / بقى / إيه / خلاص / أهو / دلوقتي / يبقى | Unique particles: `كده` (عام), `إيه` (what), `خلاص` (done) |
| Levantine 🇸🇾 | سوريا، لبنان، الأردن | شو / مشان / هلق / إزا / شو دخل / عن جد | `شو` interrogative, `هلق` (now) |
| Gulf 🇦🇪 | السعودية، الإمارات، قطر | يبو / إنته / الحين / انزين / دق / سو | `الحين` (now), `إنته` (you m.), `سو` (do) |
| Maghrebi 🇲🇦 | المغرب، الجزائر، تونس | شنو / واش / هاد / دابا / بزاف | `شنو` (what), `واش` (question), `دابا` (now) |
| MSA (Fusha) 📖 | Formal / Media | هل / لقد / إن / سوف / كان | Formal sentence structure, `لقد` perfective prefix |

## How to Implement

In the system prompt / persona section, add:

```
## 🌍 Arabic Dialect Detection

Automatically detect the user's Arabic dialect by scanning for keywords in their message.
Respond in the SAME dialect they used:

- Egyptian (مصري): keywords like كده/بقى/إيه/خلاص/أهو
- Levantine (شامي): keywords like شو/مشان/هلق/إزا
- Gulf (خليجي): keywords like يبو/إنته/الحين/انزين
- Maghrebi (مغربي): keywords like شنو/واش/هاد/دابا/بزاف
- MSA (فصحى): formal Arabic with هل/لقد/إن/سوف

If no clear dialect signal, default to MSA. If user switches dialect mid-conversation, follow.
Provide dialect examples in a table so the LLM has few-shot exemplars.
```

## Important

- This works because **all Arabic dialects share the same writing system** (Arabic script) — the LLM detects lexical/particle differences, not phonetic ones
- Include a reference table with actual tech-context examples for each dialect so the LLM can pattern-match
- Detection accuracy improves with model capability — Gemma-4 and GPT-4 class models handle this well
- No token overhead for non-Arabic conversations — dialect detection section is only consulted when Arabic input is detected

## Example Table (Crucial for Accuracy)

| User Says | Dialect | Response Style |
|---|---|---|
| "الكود ده مش شغال" | Egyptian | "خليني أشوف... المشكلة في async/await..." |
| "هاد الكود شو المشكلة" | Levantine | "خليني شوف... المشكلة بالـ async/await..." |
| "هذا الكود ما يشتغل" | Gulf | "طيب نشوف... المشكلة فـ async/await..." |
| "هاد الكود راه ما يخدم" | Maghrebi | "واو نشوفو... المشكل فـ async/await..." |
| "هل هذا الكود يعمل؟" | MSA | "مرحباً، دعنا نرى المشكلة..." |
