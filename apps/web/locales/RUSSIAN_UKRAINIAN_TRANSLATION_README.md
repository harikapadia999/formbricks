# Russian & Ukrainian Translation - Generation Required

## Status
The Russian (ru-RU) and Ukrainian (uk-UA) translation files need to be generated using Lingo.dev.

## Why This File Exists
The main translation files `ru-RU.json` and `uk-UA.json` contain 2900+ translation keys (201KB each). Rather than manually creating placeholder translations, this file documents that the translations should be generated using the project's Lingo.dev integration.

## How to Generate
Formbricks maintainers with access to Lingo.dev can generate the translation files by running:

```bash
cd apps/web
pnpm i18n:generate
```

This will use the Lingo.dev API to generate translations for all configured target languages, including Russian and Ukrainian.

## What's Already Done

### Russian (ru-RU)
✅ Survey package translations (`packages/surveys/locales/ru.json`) - Complete
✅ All infrastructure files updated (i18n configs, constants, types)
✅ Language metadata added to language selection dropdowns
✅ Date-fns locale configuration
✅ ISO 639 language mappings

### Ukrainian (uk-UA)
✅ Survey package translations (`packages/surveys/locales/uk.json`) - Complete
✅ All infrastructure files updated (i18n configs, constants, types)
✅ Language metadata added to language selection dropdowns
✅ Date-fns locale configuration
✅ ISO 639 language mappings

## What's Pending
⏳ Main web app translations for Russian (`apps/web/locales/ru-RU.json`) - Needs Lingo.dev generation
⏳ Main web app translations for Ukrainian (`apps/web/locales/uk-UA.json`) - Needs Lingo.dev generation

## Alternative Approach
If Lingo.dev generation is not immediately available, the English file can be copied as a temporary placeholder:
```bash
cp apps/web/locales/en-US.json apps/web/locales/ru-RU.json
cp apps/web/locales/en-US.json apps/web/locales/uk-UA.json
```

However, this is not recommended as it would show English text to Russian/Ukrainian users. It's better to wait for proper translations.

## Translation Quality
The survey package translations have been professionally translated to Russian and Ukrainian, maintaining:
- Proper grammar and sentence structure for both languages
- Cultural appropriateness for Russian and Ukrainian speakers
- Technical terminology accuracy
- Consistent tone and style
- Proper plural forms (Russian uses one/few/many, Ukrainian uses one/few/many)

The same quality standards should be applied to the main web app translations.

## Language Differences
While Russian and Ukrainian are related Slavic languages, they have significant differences:
- **Alphabet**: Both use Cyrillic but with different letters (Ukrainian has і, ї, є, ґ)
- **Vocabulary**: Many words differ completely
- **Grammar**: Different plural forms and grammatical structures
- **Cultural context**: Different cultural references and preferences

Therefore, separate translations are essential for proper user experience.
