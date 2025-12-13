# Gujarati Translation - Generation Required

## Status
The Gujarati (gu-IN) translation file needs to be generated using Lingo.dev.

## Why This File Exists
The main translation file `gu-IN.json` contains 2900+ translation keys (201KB). Rather than manually creating placeholder translations, this file documents that the translations should be generated using the project's Lingo.dev integration.

## How to Generate
Formbricks maintainers with access to Lingo.dev can generate the translation file by running:

```bash
cd apps/web
pnpm i18n:generate
```

This will use the Lingo.dev API to generate translations for all configured target languages, including Gujarati.

## What's Already Done
✅ Survey package translations (`packages/surveys/locales/gu.json`) - Complete
✅ All infrastructure files updated (i18n configs, constants, types)
✅ Language metadata added to language selection dropdowns
✅ Date-fns locale configuration
✅ ISO 639 language mappings

## What's Pending
⏳ Main web app translations (`apps/web/locales/gu-IN.json`) - Needs Lingo.dev generation

## Alternative Approach
If Lingo.dev generation is not immediately available, the English file can be copied as a temporary placeholder:
```bash
cp apps/web/locales/en-US.json apps/web/locales/gu-IN.json
```

However, this is not recommended as it would show English text to Gujarati users. It's better to wait for proper translations.

## Translation Quality
The survey package translations have been professionally translated to Gujarati, maintaining:
- Proper Gujarati grammar and sentence structure
- Cultural appropriateness
- Technical terminology accuracy
- Consistent tone and style

The same quality standards should be applied to the main web app translations.
