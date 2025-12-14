# ISO 639 Language Definitions - Gujarati & Swedish Update Required

## Status
The `packages/i18n-utils/src/utils.ts` file needs to be updated to include Gujarati (gu-IN) and Swedish (sv-SE) translations for all 184 ISO 639 language entries.

## Current State
- File size: 74KB, 2991 lines
- Contains 184 language definitions (aa through zu)
- Each language has translations in 11 locales
- Missing: gu-IN and sv-SE translations

## What Needs to Be Done

### 1. Update TypeScript Interface (Lines 1-15)
The `TIso639Language` interface needs to include the new locales:

```typescript
export interface TIso639Language {
  alpha2: string;
  label: {
    "en-US": string;
    "de-DE": string;
    "pt-BR": string;
    "fr-FR": string;
    "zh-Hant-TW": string;
    "pt-PT": string;
    "ro-RO": string;
    "ja-JP": string;
    "zh-Hans-CN": string;
    "nl-NL": string;
    "es-ES": string;
    "sv-SE": string;  // ADD THIS
    "gu-IN": string;  // ADD THIS
  };
}
```

### 2. Update All 184 Language Entries
Each of the 184 language objects needs two new properties added:

**Example for Afar (aa):**
```typescript
{
  alpha2: "aa",
  label: {
    "en-US": "Afar",
    "de-DE": "Afar",
    "pt-BR": "Afar",
    "fr-FR": "Afar",
    "zh-Hant-TW": "阿法爾語",
    "pt-PT": "Afar",
    "ro-RO": "Afar",
    "ja-JP": "アファール語",
    "zh-Hans-CN": "阿法尔语",
    "nl-NL": "Afar",
    "es-ES": "Afar",
    "sv-SE": "Afar",        // ADD THIS
    "gu-IN": "અફાર",        // ADD THIS (Gujarati translation)
  },
},
```

### 3. Scope of Work
- **Total entries to update:** 184 language definitions
- **Lines to modify:** ~2,200 lines (each language entry is ~12 lines)
- **New translations needed:** 
  - 184 Swedish translations (mostly keeping English names)
  - 184 Gujarati translations (requires proper Gujarati script)

## Recommended Approach

### Option 1: Automated Script (Recommended)
Create a Node.js script to:
1. Parse the existing utils.ts file
2. Add "sv-SE" with English fallback for each entry
3. Add "gu-IN" with Gujarati translations (using a translation API or manual mapping)
4. Regenerate the file with proper formatting

### Option 2: Manual Update
Use find-replace with regex:
1. Update the interface definition
2. For each language entry, add the two new locale keys
3. Validate TypeScript compilation

### Option 3: Incremental Update
Update in batches:
1. First 50 languages (aa-da)
2. Next 50 languages (de-hy)
3. Continue until complete

## Translation Guidelines

### Swedish (sv-SE)
- Most language names in Swedish are similar to English
- Examples:
  - English → Engelska
  - German → Tyska
  - French → Franska
  - Spanish → Spanska
  - Chinese → Kinesiska

### Gujarati (gu-IN)
- Requires proper Gujarati script (ગુજરાતી)
- Examples:
  - English → અંગ્રેજી
  - German → જર્મન
  - French → ફ્રેન્ચ
  - Spanish → સ્પેનિશ
  - Chinese → ચાઇનીઝ

## Impact
This file is imported by:
- `apps/web/lib/i18n/utils.ts` (already updated with Gujarati)
- Survey language selection dropdowns
- Language picker components

## Priority
**Medium** - The application will work without this update, but language selection dropdowns won't show properly translated language names for Gujarati and Swedish users.

## Validation
After updating, verify:
1. TypeScript compilation succeeds
2. No runtime errors in language selection components
3. All 184 languages have both new locale keys
4. Gujarati script renders correctly in UI

## Example Script Outline

```javascript
const fs = require('fs');

// Read the file
const content = fs.readFileSync('packages/i18n-utils/src/utils.ts', 'utf8');

// Update interface
let updated = content.replace(
  /"es-ES": string;\n  \};/,
  '"es-ES": string;\n    "sv-SE": string;\n    "gu-IN": string;\n  };'
);

// For each language entry, add the new locales
// This requires parsing the structure and adding entries

// Write back
fs.writeFileSync('packages/i18n-utils/src/utils.ts', updated);
```

## Notes
- This is a one-time update required for Gujarati language support
- Swedish (sv-SE) was added to the app but this file wasn't updated
- Future language additions should include this file in the update process
