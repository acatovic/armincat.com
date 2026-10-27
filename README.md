# armincat.com
My personal website and blog

## Article styling

The homepage and articles share `style.css`: `.site-title`, `.page-header`,
`.page-title`, `.subtitle`, `.article-date`, and `.site-footer` keep typography,
colours, and spacing consistent. Use the existing articles as templates for new posts.

An article header uses `class="page-header post-header"`, with a date, an `h1`
with `class="page-title"`, and an optional `<p class="subtitle">…</p>` beneath it.
Wrap the article body in `<div class="prose">`. Within it, use ordinary `h2`
elements for sections, `h3` for subsections, and `h4` for further subdivisions;
paragraphs, lists, links, and blockquotes are styled automatically.

## Deploy

The site is hosted on Cloudflare Workers at https://armincat.com.

```sh
npm ci
npx wrangler login
npm run deploy
```

The build copies `index.html`, `style.css`, and `articles/` into `dist/`, so only public site
content is uploaded. Wrangler configures the `armincat.com` custom domain and its
DNS record. The existing `.html` article links remain valid; Cloudflare redirects
them to clean URLs.

Use `npm run dev` for a local preview.
