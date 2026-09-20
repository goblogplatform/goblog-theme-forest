# Forest — a goblog theme

Misty greens, a soft serif and a full-bleed forest backdrop. This is the theme that ships compiled into goblog as `forest`, published as a directory theme so it can be installed and updated on its own.

## Install

From your goblog: **Admin → Themes → Browse → Forest → Install**, then **Activate**. Requires goblog 0.5.0 or newer.

## What it overrides

Only the public-facing templates (`header`, `footer`, `home`, `post`, `posts`, the page types, `tag`, `search`, `projects`, `presentations`, `error`, `login`, `research`) and `static/css/goblog.css`. Admin and wizard pages render from goblog's default theme, so they keep up with new goblog releases automatically.

## Developing

Edit the files under `templates/` and `static/`, drop the folder into a goblog checkout as `themes/installed/forest/` (or point `THEMES_INSTALLED_DIR` at its parent) and set the `theme` setting to `forest`. Templates are Go `html/template`; see [docs/THEME_CONTRACT.md](https://github.com/goblogplatform/goblog/blob/main/docs/THEME_CONTRACT.md) for the contract.

## Releasing

Tag `vX.Y.Z` and publish a GitHub release; the directory picks up the tag's archive. `screenshot.png` at the root is shown in the listing.
