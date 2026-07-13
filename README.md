# LBWO - Multilingual Fork

A community-translated fork of **レズ化洗脳手術 (Lesbianization Brainwashing Operation)**, a RimWorld mod originally created by **Udon**.

This fork adds full localization support via RimWorld's native `DefInjected` translation system, allowing the mod to be played in multiple languages instead of Japanese only.

---

## 📌 Original Mod

- **Original Title:** レズ化洗脳手術 (LBWO - Lesbianization BrainWashing Operation)
- **Original Author:** [Udon](https://steamcommunity.com/profiles/76561198044599324)
- **Original Steam Workshop Page:** https://steamcommunity.com/sharedfiles/filedetails/?id=2556298432

All credit for the original concept, design, and implementation belongs to Udon. This fork exists solely to extend accessibility through translation and does not claim ownership over the original work. If the original author would like this fork taken down, merged, credited differently, or handled another way, please open an issue and it will be respected.

---

## 🌍 Translation Status

| Language | Folder Name | Status | Contributor(s) | Reviewer(s) |
|---|---|---|---|---|
| Japanese (original) | `Japanese` | ✅ Complete (source) | Udon | (source) |
| English | `English` | ✅ Complete | Puddle | Puddle |
| Simplified Chinese | `ChineseSimplified` | ⚠️ Complete, unreviewed | Puddle | ~ |
| French | `French` | ⚠️ Complete, unreviewed | Puddle | ~ |
| German | `German` | ⚠️ Complete, unreviewed | Puddle | ~ |
| Korean | `Korean` | ⚠️ Complete, unreviewed | Puddle | ~ |
| Polish | `Polish` | ⚠️ Complete, unreviewed | Puddle | ~ |
| Portuguese (Brazil) | `PortugueseBrazilian` | ⚠️ Complete, unreviewed | Puddle | ~ |
| Russian | `Russian` | ⚠️ Complete, unreviewed | Puddle | ~ |
| Spanish (Spain) | `Spanish` | ⚠️ Complete, unreviewed | Puddle | ~ |
| Spanish (Latin America) | `SpanishLatin` | ⚠️ Complete, unreviewed | Puddle | ~ |
| Traditional Chinese | `ChineseTraditional` | ⬜ Not started | ~ | ~ |
| Italian | `Italian` | ⬜ Not started | ~ | ~ |
| Turkish | `Turkish` | ⬜ Not started | ~ | ~ |
| Ukrainian | `Ukrainian` | ⬜ Not started | ~ | ~ |

> ⚠️ **Confidence note:** Only the **English** and **Japanese (original)** translations are confirmed accurate by the maintainers. All other languages marked "Complete, unreviewed" were produced with DeepL assistance and have **not** been verified by a fluent speaker. They may contain awkward phrasing or outright errors — please treat them as a draft, not a finished translation. If you're fluent in one of these languages, review/corrections are very welcome via a push request.

Want to add a language not listed here? Open a push request — the list will grow with contributions.

> **Note:** Some translations in this fork were produced with the assistance of [DeepL](https://www.deepl.com/) and may not have been fully human-reviewed yet. See the status table above and individual push requests for details on which languages have been reviewed by a fluent speaker versus machine-assisted only.

---

## 🗂️ Mod Structure

```
.
├── 1.1 … 1.6/            # Per-RimWorld-version compiled Assemblies
├── About/                # Mod metadata, preview image
├── Common/                # Shared Defs and Textures across all versions
│   └── Defs/
│       ├── HediffDefs/
│       └── RecipeDefs/
├── Languages/              # Localization (this fork's main addition)
│   ├── English/
│   │   └── DefInjected/
│   │       ├── HediffDef/
│   │       └── RecipeDef/
│   └── Japanese/
│       └── DefInjected/
└── LoadFolders.xml
```

Translations are added using RimWorld's **DefInjected** system, which overrides `label`/`description`/etc. fields per language without modifying the original Defs. This means the base mod's Japanese defaults are always preserved as a fallback.

---

## 🤝 Contributing a Translation

1. **Fork this repo** and clone it locally.
2. Create a new folder under `Languages/` using RimWorld's expected folder name for your language (see the table above, or check RimWorld's own `Data/Core/Languages/` folder for the exact name if unsure).
3. Mirror the `DefInjected` structure:
   ```
   Languages/<YourLanguage>/DefInjected/HediffDef/LBW_Hediffs_Lesbianization.xml
   Languages/<YourLanguage>/DefInjected/RecipeDef/LBW_Recipes_Surgery_Lesbianization.xml
   ```
4. Use the `defName.field` key format inside a `<LanguageData>` block, matching the keys found in `Common/Defs/`.
5. Test in-game by switching RimWorld's language setting to yours and confirming the new text displays correctly (health tab, operations menu, trait tooltip, etc).
6. Open a pull request. Please note in the PR description whether the translation is human-reviewed or machine-translated (MT is welcome as a starting draft, but should be flagged so it can be improved later).

### Translation Notes
- Keep `labelNoun` fields grammatically correct as a noun phrase — some sentence templates insert them directly into English sentences (e.g. "has developed a `labelNoun`").
- `labelShort` fields (if present) should stay concise to avoid overflowing narrow UI elements like the health tab list.
- Try to preserve the tone/intent of the source material rather than a literal word-for-word translation where phrasing would be awkward.

---

## 🐛 Issues & Discussion

Found a mistranslation, a missing string, or a version that doesn't load correctly? Open an issue with:
- The RimWorld version you're running
- The language affected
- What you expected vs. what you saw

---

## 📜 License / Attribution

This is a derivative/translation fork of Udon's original mod. No original assets, code, or content have been altered beyond localization support. Please retain the original attribution above in any redistribution of this fork.

Translation assistance for some languages was provided by [DeepL](https://www.deepl.com/), with community review where noted in the status table.
