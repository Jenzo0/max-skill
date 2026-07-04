# 🌍 Arabic Dialects

Max automatically detects the user's Arabic dialect and responds in the same dialect. No configuration required.

## Supported Dialects

| Dialect | Region | Keywords | Example |
|---|---|---|---|
| 🇪🇬 **Egyptian** | Egypt, Sudan | كده / بقى / إيه / خلاص / أهو | "الكود ده مش شغال" |
| 🇸🇾 **Levantine** | Syria, Lebanon, Jordan, Palestine | شو / مشان / هلق / إزا | "هاد الكود شو المشكلة" |
| 🇦🇪 **Gulf** | Saudi Arabia, UAE, Qatar, Kuwait | يبو / إنته / الحين / انزين | "هذا الكود ما يشتغل" |
| 🇲🇦 **Maghrebi** | Morocco, Algeria, Tunisia, Libya | شنو / واش / هاد / دابا / بزاف | "هاد الكود راه ما يخدم" |
| 📖 **MSA (Fusha)** | Formal / Media | هل / لقد / إن / سوف | "هل هذا الكود يعمل؟" |

## How Detection Works

1. **Keyword scanning** — Max scans the user's message for dialect-specific keywords
2. **Grammar pattern matching** — Sentence structure gives additional clues
3. **Auto-selection** — The matching dialect module is loaded
4. **Consistent response** — Max continues in that dialect for the full conversation
5. **Mid-conversation switching** — If user switches dialect, Max follows

## Technical Implementation

Dialect detection is built entirely into the system prompt instructions — no external API or library needed. The LLM's native language understanding handles the detection.

## Example Conversations

### Egyptian 🇪🇬
> **User:** "الكود ده مش شغال، أيه المشكلة؟"  
> **Max:** "خليني أشوف... المشكلة في async/await بتاعك. انت بتستخدم await من غير async في الـ function..."

### Levantine 🇸🇾
> **User:** "هاد الكود لسا شغال، شو المشكلة؟"  
> **Max:** "خليني شوف... المشكلة بالـ async/await. نسيت تحط async قبل الـ function..."

### Gulf 🇦🇪
> **User:** "هذا الكود ما يشتغل، شنو المشكلة؟"  
> **Max:** "طيب نشوف... المشكلة فـ async/await. لازم تحط async قبل الـ function..."
