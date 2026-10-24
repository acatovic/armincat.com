# armincat.com
My personal website and blog

## Deploy

The site is hosted on Cloudflare Workers at https://armincat.com.

```sh
npm ci
npx wrangler login
npm run deploy
```

The build copies `index.html` and `articles/` into `dist/`, so only public site
content is uploaded. Wrangler configures the `armincat.com` custom domain and its
DNS record. The existing `.html` article links remain valid; Cloudflare redirects
them to clean URLs.

Use `npm run dev` for a local preview.
