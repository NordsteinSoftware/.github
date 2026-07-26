# .github

Organisation-level defaults for [SyntaktikEU](https://github.com/SyntaktikEU).

`profile/README.md` is what GitHub renders on the organisation's public page. It is the only file
here with an audience — edit it, and the change is live on the org page as soon as it is pushed to
`main`.

The two SVGs beside it are the Syntaktik mark, derived from `public/favicon.svg` in the website
repo, with the white tile removed and a light/dark pair so the mark stays legible in both GitHub
themes. They are referenced by absolute `raw.githubusercontent.com` URL, because relative image
paths do not resolve reliably when the profile README is rendered on the organisation page.

`profile/avatar.svg` is the organisation profile picture, with `avatar.png` the 512 px render that
GitHub actually accepts (it rejects SVG). Unlike the two logos above it has the navy baked in and
bleeds to the edges, because an avatar gets no `prefers-color-scheme` and GitHub crops it to a
circle in some views and a rounded square in others. To change it, edit the SVG and re-render:

```bash
rsvg-convert -w 512 -h 512 profile/avatar.svg -o profile/avatar.png
```

then upload the PNG at **Organisation settings → Profile → Profile picture**. There is no REST API
for an organisation avatar, so this step cannot be scripted.

Copy is kept in step with the English locale file of the website (`src/i18n/en.ts`); when a service
description or a claim changes there, change it here too.
