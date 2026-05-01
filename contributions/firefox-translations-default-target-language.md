# Firefox Translations - Default Target Language After Source Language Change

## Links

- **Repository:** [mozilla-firefox/firefox](https://github.com/mozilla-firefox/firefox)
- **Bug:** [Bug 2031015](https://bugzilla.mozilla.org/show_bug.cgi?id=2031015)
- **Commit:** [242c60757e03](https://github.com/mozilla-firefox/firefox/commit/242c60757e03)
- **Mozilla Central Revision:** [af4c655f9915](https://hg.mozilla.org/mozilla-central/rev/af4c655f9915)
- **Phabricator Revision:** [D295637](https://phabricator.services.mozilla.com/D295637)
- **Status:** Merged / RESOLVED FIXED

## Summary

This was my first open source contribution. I improved the Firefox full-page Translations panel so that when a user manually changes the detected source language, Firefox can automatically suggest the user's preferred supported target language if the target language is still unset.

The change landed in Firefox and was marked fixed for Firefox 152.

## Problem

Firefox already knows the user's preferred target language in many translation flows. However, there was a frustrating case where a page was detected as English, or mostly English, while the user wanted to translate foreign-language content on that page.

In that flow, the user could manually change the "Translate from" language, but the "Translate to" language stayed on "Choose a language." This forced the user to repeatedly select their usual target language, even when Firefox could infer a better default.

## Solution

I updated the source-language change handler in the full-page Translations panel. When the user changes the source language, the panel now checks whether the target language is still empty. If it is, Firefox asks for the top preferred supported target language while excluding the newly selected source language to avoid same-language translation.

The implementation also re-checks the target language after the async lookup completes, so it does not overwrite a target language that the user selected while the lookup was in progress.

## Technical Details

- **Languages / Frameworks:** JavaScript, Firefox browser UI, Mozilla browser tests
- **Files changed:**
  - `browser/components/translations/content/fullPageTranslationsPanel.js`
  - `browser/components/translations/tests/browser/browser_translations_full_page_panel_switch_languages.js`
- **Tests added:** Added browser test coverage for the case where an English page starts with no target language, the user changes the source language to Spanish, and Firefox updates the target language to English.
- **Edge cases handled:** Avoided same-language translation and avoided overwriting a user-selected target language after an async preference lookup.

## Impact

This improved the user experience for Firefox Translations by saving users from a repeated manual selection step. It also added regression coverage for the behavior so future changes to the translations panel are less likely to break it.

## Skills Demonstrated

- Reading and modifying a large production browser codebase
- Working with Mozilla's Bugzilla and Phabricator contribution workflow
- Implementing async UI behavior safely
- Preserving user intent during async state updates
- Writing browser-level regression tests
- Communicating with maintainers and responding to review guidance

## Notes

This contribution was mentored as a good-first-bug in Firefox Translations and was pushed by a Mozilla maintainer after review.
