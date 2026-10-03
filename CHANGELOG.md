## 1.5.0

- The login page offers goblog's password form (the shared `_password_login` partial) when the site has a password account, under the GitHub button. Until now a site with both GitHub login and a password admin showed only GitHub on this theme (goblog #666).
- **Requires goblog 0.14.0**, the first release with password login and the partial.

## 1.4.1

- On a post page, the admin-only link sections (Backlinks, Linked Posts, External Links, External Backlinks) and the comments sit on cards like the post body. They were drawn straight onto the background photo, where the text was hard to read.

## 1.4.0

- The footer's "Powered by goblog" line comes from goblog's shared `_powered_by` partial instead of being written out in the theme. It now links to [goblog.live](https://www.goblog.live) rather than the GitHub repository, and a site can hide it with the **Show "Powered by goblog"** setting under Admin → Settings → Appearance (goblog #644).
- **Requires goblog 0.13.0**, the first release with the partial; on anything older the theme's `footer.html` references a template that does not exist.

## 1.3.0

- Signing in with GitHub is goblog's job now. The button is a plain link to `/login/github`; the theme no longer assembles the authorize URL in an inline script, where `window.location` went into `redirect_uri` unescaped, nor handles the `?code=` that came back. goblog completes the exchange server-side against a `state` it minted, so a code obtained for one account can no longer be replayed into another visitor's browser (goblog #631, #637).
- The button's own URL comes from the server too, as `.github_login_url`, instead of being built with a template conditional in every theme (goblog #639).
- **Requires goblog 0.12.0**, and the manifest now says so, so the installer refuses the combination rather than installing a theme whose sign-in button has no URL to point at. Upgrade goblog first. An older version of this theme still signs in on 0.12.0 — goblog restarts the flow when a callback arrives with no state (goblog #640) — but it gets there via a second round trip to GitHub, so update the theme rather than relying on that.

## 1.2.1

- Inline scripts that call jQuery and highlight.js wait for `DOMContentLoaded`, so the theme keeps working when goblog defers its CDN scripts (goblog 0.11.0, goblogplatform/goblog#624). Without this, posts lose syntax highlighting and the GitHub login button does nothing.
- The GitHub login button's `href` is set during parse with `document.getElementById(...).href` instead of jQuery, so the link is never briefly inert.
- Backward compatible: still works on goblog 0.10.0.

## 1.2.0

- Post, page and comment bodies are rendered by goblog on the server; the theme no longer ships showdown or DOMPurify. Embeds that DOMPurify used to strip (YouTube, Instagram) work again, and the body reaches crawlers and link-preview bots.
- The comment Preview button shows the draft as plain text, since no markdown library is loaded on the page.
- Requires goblog 0.10.0.

## 1.1.0

- The search page includes goblog's shared `_search_results` partial instead of rendering the post list itself, so plugin, theme and docs hits appear in the site search. The result colours the template used to set inline now come from `goblog.css`.
- Requires goblog 0.8.0.

## 1.0.0

- First release as a directory theme: the built-in forest theme's public templates and CSS, layered on goblog's default theme.
