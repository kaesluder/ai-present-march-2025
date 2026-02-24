# I18next configuration and setup. 

## Introduction

We want to set up i18next for this repository in /frontend.

- Currently, English is the only language that is supported. But we want to set it up now so that we can add other languages later.
- All React code should be in `/frontend`.
- Use **JSON** for translation files.

## Behavior

When the user opens a page, 
given translation tags for ui text,
then the user should see localized strings

# Rules

- All code changes should be in `/frontend`.
- Do not translate mock strings used for demo purposes.

# Steps

1. Review/finalize `src/i18n.ts` configuration.
2. Create `public/locales/en/translation.json` with initial English strings.
3. Translate the `HomePage` function in `App.tsx` as a proof of concept using `useTranslation`.
4. Wait for review.
5. Translate remaining strings across all components.
