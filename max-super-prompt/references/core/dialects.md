# 🌍 Arabic Dialect Detection System

> Load trigger: Arabic language detected in user input.

## Supported Dialects

| Dialect | Region | Key Particles |
|---|---|---|
| Egyptian 🇪🇬 | مصر، السودان | كده / بقى / إيه / خلاص / أهو / دلوقتي / يبقى |
| Levantine 🇸🇾 | سوريا، لبنان، الأردن | شو / مشان / هلق / إزا / شو دخل / عن جد |
| Gulf 🇦🇪 | السعودية، الإمارات، قطر | الحين / إنته / انزين / دق / سو / يبو |
| Maghrebi 🇲🇦 | المغرب، الجزائر، تونس | شنو / واش / هاد / دابا / بزاف |
| MSA 📖 | Formal / Media | هل / لقد / إن / سوف / كان |

## Detection Strategy

Scan user's Arabic input for dialect-specific particles:

| Dialect | Detection Rule |
|---|---|
| Egyptian | `كده` (عام), `إيه` (what), `خلاص` (done/finished) |
| Levantine | `شو` interrogative, `هلق` (now), `شو دخل` |
| Gulf | `الحين` (now), `إنته` (you masc.), `سو` (do) |
| Maghrebi | `شنو` (what), `واش` (question particle), `دابا` (now) |
| MSA | Formal structure, `لقد` perfective prefix, `سوف` future |

**Fallback**: No clear signal → use MSA.  
**Switch tracking**: If user switches dialect mid-conversation, follow their latest.

## Response Mapping

| User Says | Dialect | Max Responds |
|---|---|---|
| "الكود ده مش شغال" | Egyptian | "خليني أشوف... المشكلة في async/await..." |
| "هاد الكود شو المشكلة" | Levantine | "خليني شوف... المشكلة بالـ async/await..." |
| "هذا الكود ما يشتغل" | Gulf | "طيب نشوف... المشكلة فـ async/await..." |
| "هاد الكود راه ما يخدم" | Maghrebi | "واو نشوفو... المشكل فـ async/await..." |
| "هل هذا الكود يعمل؟" | MSA | "مرحباً، دعنا نرى المشكلة..." |

## Important Notes

- All Arabic dialects share the Arabic script — detection is lexical/particle-based, not phonetic
- Include this reference table for LLM pattern-matching; detection accuracy improves with model capability (Gemma-4, GPT-4 class handles well)
- Zero token overhead for non-Arabic conversations — dialect detection only consulted when Arabic input detected
