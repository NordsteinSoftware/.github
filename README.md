# .github

Organisation-level defaults for [NordsteinSoftware](https://github.com/NordsteinSoftware).

`profile/README.md` is what GitHub renders on the organisation's public page. It is the only file
here with an audience — edit it, and the change is live on the org page as soon as it is pushed to
`main`.

## Brand assets

The corporate identity lives in
[NordsteinSoftware/CorporateIdentity](https://github.com/NordsteinSoftware/CorporateIdentity). The
files under `profile/` are copies of assets generated there, never hand-drawn here. When the
identity changes, copy the assets across again rather than editing them in place.

| File | Source in CorporateIdentity |
| --- | --- |
| `profile/logo-light.svg` | `assets/logo/svg/nordstein-lockup-horizontal.svg` |
| `profile/logo-dark.svg` | `assets/logo/svg/nordstein-lockup-horizontal-reversed.svg` |
| `profile/avatar.svg` | `assets/favicon/nordstein-appicon.svg`, corner radius dropped |

The two lockups are a light/dark pair, selected with `prefers-color-scheme` so the mark stays
legible in both GitHub themes. They are referenced by absolute `raw.githubusercontent.com` URL,
because relative image paths do not resolve reliably when the profile README is rendered on the
organisation page. The horizontal lockup is the default logo per the brand guidelines — do not put
the mark next to a text heading instead, that rebuilds the lockup by hand.

`profile/avatar.svg` is the organisation profile picture, with `avatar.png` the 512 px render that
GitHub actually accepts (it rejects SVG). Unlike the two lockups it has `slate-800` (`#16283C`)
baked in and bleeds to the edges, because an avatar gets no `prefers-color-scheme` and GitHub crops
it to a circle in some views and a rounded square in others. The app icon's 22 % corner radius is
dropped for the same reason: GitHub supplies its own mask. To change it, copy the current app icon
across and re-render:

```bash
python3 -c "import cairosvg; cairosvg.svg2png(url='profile/avatar.svg', write_to='profile/avatar.png', output_width=512, output_height=512)"
```

`rsvg-convert -w 512 -h 512 profile/avatar.svg -o profile/avatar.png` produces the same file if
`librsvg` is installed. Then upload the PNG at **Organisation settings → Profile → Profile
picture**. There is no REST API for an organisation avatar, so this step cannot be scripted.

## Copy

Copy is kept in step with the English locale file of the website (`src/i18n/en.ts`); when a service
description or a claim changes there, change it here too. Tone follows the voice section of
[`docs/brand-guidelines.md`](https://github.com/NordsteinSoftware/CorporateIdentity/blob/main/docs/brand-guidelines.md)
— first person plural, sentence case, no hype words, no emoji, and no slogan.
