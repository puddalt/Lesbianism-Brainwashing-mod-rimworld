# LBWO - Multilingual + Gameplay Fork

A community fork of **レズ化洗脳手術 (Lesbianization Brainwashing Operation)**, a RimWorld mod originally created by **Udon**.

This started as a translation-only fork, but now also includes a gameplay adjustment: the operation is restricted to female pawns only, implemented via a bundled Harmony patch. It's no longer just a language patch — treat this as a maintained fork with both localization and behavior changes.

---

## 📌 Original Mod

- **Original Title:** レズ化洗脳手術 (LBWO - Lesbianization BrainWashing Operation)
- **Original Author:** [Udon](https://steamcommunity.com/profiles/76561198044599324)
- **Original Steam Workshop Page:** https://steamcommunity.com/sharedfiles/filedetails/?id=2556298432

All credit for the original concept, design, and implementation belongs to Udon. This fork exists to extend accessibility through translation and to adjust one piece of gameplay logic; it does not claim ownership over the original work. If the original author would like this fork taken down, merged, credited differently, or handled another way, please open an issue and it will be respected.

---

## ✨ What This Fork Changes

- **Localization:** Full multi-language support via RimWorld's native `DefInjected` system (see table below), instead of Japanese-only.
- **Gameplay:** The Lesbian Brainwashing Program surgery is now restricted to female pawns. This is enforced via a Harmony patch on `RecipeDef.AvailableOnNow`, so the operation simply won't appear as selectable for male pawns rather than being a cosmetic-only restriction.
- **Dependency:** Requires the [Harmony](https://steamcommunity.com/sharedfiles/filedetails/?id=2009463077) mod to be installed and enabled, since Harmony is not bundled with this fork.

If you're looking for the original, translation-only, or vanilla-eligibility version of this mod, that's Udon's original linked above.

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

> ⚠️ **Confidence note:** Only the **English** and **Japanese (original)** translations are confirmed accurate by the maintainers. All other languages marked "Complete, unreviewed" were produced with DeepL assistance and have **not** been verified by a fluent speaker. They may contain awkward phrasing or outright errors — please treat them as a draft, not a finished translation. If you're fluent in one of these languages, review/corrections are very welcome via a pull request.

Want to add a language not listed here? Open a pull request — the list will grow with contributions.

> **Note:** Some translations in this fork were produced with the assistance of [DeepL](https://www.deepl.com/) and may not have been fully human-reviewed yet. See the status table above and individual pull requests for details on which languages have been reviewed by a fluent speaker versus machine-assisted only.

---

## 🗂️ Mod Structure

```
.
├── 1.1 … 1.6/              # Per-RimWorld-version compiled Assemblies (gameplay patch; requires Harmony mod)
├── About/                  # Mod metadata, preview image
├── Common/                 # Shared Defs and Textures across all versions
│   └── Defs/
│       ├── HediffDefs/
│       └── RecipeDefs/
├── Languages/              # Localization
│   ├── English/
│   │   └── DefInjected/
│   │       ├── HediffDef/
│   │       └── RecipeDef/
│   └── Japanese/
│       └── DefInjected/
└── LoadFolders.xml
```

Translations are added using RimWorld's **DefInjected** system, which overrides `label`/`description`/etc. fields per language without modifying the original Defs. The base mod's Japanese defaults are always preserved as a fallback.

The gameplay restriction lives in each version's compiled assembly (source maintained separately, not included in this repo's Defs) and uses Harmony to patch `RecipeDef.AvailableOnNow` for this mod's specific recipe.

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
6. Open a pull request. Please note whether the translation is human-reviewed or machine-translated (MT is welcome as a starting draft, but should be flagged so it can be improved later).

### Translation Notes
- Keep `labelNoun` fields grammatically correct as a noun phrase — some sentence templates insert them directly into English sentences (e.g. "has developed a `labelNoun`").
- `labelShort` fields (if present) should stay concise to avoid overflowing narrow UI elements like the health tab list.
- Try to preserve the tone/intent of the source material rather than a literal word-for-word translation where phrasing would be awkward.

---

## 🛠️ Contributing to the Gameplay/Code Side

This fork also maintains a small Harmony-based C# patch (targeting `net472`) alongside the original mod's HediffComp logic. If you want to contribute code changes:

- Bug reports/feature requests for the gameplay restriction are welcome via Issues.
- Please test any code change against RimWorld 1.6 at minimum before submitting a PR, and note which other versions (1.1–1.5) you were able to verify.
- Keep gameplay changes scoped and documented — this fork aims to stay close to the original mod's intent while making the eligibility restriction reliable, not to expand scope further without discussion first.

---

## 🐛 Issues & Discussion

Found a mistranslation, a missing string, unexpected surgery eligibility behavior, or a version that doesn't load correctly? Open an issue with:
- The RimWorld version you're running
- The language and/or feature affected
- What you expected vs. what you saw
- Any relevant errors from your `Player.log`

---

## 📜 License / Attribution

This is a derivative fork of Udon's original mod, extended with localization and a gameplay adjustment. No original assets have been altered beyond what's described above. Please retain the original attribution above in any redistribution of this fork.

Translation assistance for some languages was provided by [DeepL](https://www.deepl.com/), with community review where noted in the status table.
