## 1.2.0

- Post, page and comment bodies are rendered by goblog on the server; the theme no longer ships showdown or DOMPurify. Embeds that DOMPurify used to strip (YouTube, Instagram) work again, and the body reaches crawlers and link-preview bots.
- The comment Preview button shows the draft as plain text, since no markdown library is loaded on the page.
- Requires goblog 0.10.0.

## 1.1.0

- The search page includes goblog's shared `_search_results` partial instead of rendering the post list itself, so plugin, theme and docs hits appear in the site search. The result colours the template used to set inline now come from `goblog.css`.
- Requires goblog 0.8.0.

## 1.0.0

- First release as a directory theme: the built-in forest theme's public templates and CSS, layered on goblog's default theme.
