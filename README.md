# .github

Organisation-level defaults for [SyntaktikEU](https://github.com/SyntaktikEU).

`profile/README.md` is what GitHub renders on the organisation's public page. It is the only file
here with an audience — edit it, and the change is live on the org page as soon as it is pushed to
`main`.

The two SVGs beside it are the Syntaktik mark, derived from `public/favicon.svg` in the website
repo, with the white tile removed and a light/dark pair so the mark stays legible in both GitHub
themes. They are referenced by absolute `raw.githubusercontent.com` URL, because relative image
paths do not resolve reliably when the profile README is rendered on the organisation page.

Copy is kept in step with the English locale file of the website (`src/i18n/en.ts`); when a service
description or a claim changes there, change it here too.
