# PackSource LA

Product sales website for [packsourcela.com](https://packsourcela.com) — moving boxes and packing supplies, LA local.

## Stack

- Pure HTML/CSS/JS — single `index.html` file, zero dependencies
- Deployed via Netlify (git push → auto deploy)

## Project Structure

```
packsourcela/
├── index.html       # Everything — inline CSS + JS
├── netlify.toml     # Netlify headers, redirects, cache config
├── .gitignore
└── README.md
```

## Adding Products

Open `index.html` and find the `PRODUCTS` array near the bottom. Add an object:

```js
{
  id:    'my-box',           // unique slug
  name:  'My New Box',
  size:  '20 × 20 × 20 in  ·  X.X cu ft',
  emoji: '📦',
  desc:  'Short description of the product.',
  price: 'From $X.XX',
  badge: null,               // or 'Popular', '🔥 Hot', etc.
  cta:   'Get Quote',
},
```

Save → commit → push. Done.

## Deploy to Netlify

### First time

1. Push this repo to GitHub
2. Go to [app.netlify.com](https://app.netlify.com) → **Add new site → Import an existing project**
3. Connect GitHub → select this repo
4. Build settings: **publish directory = `.`** (already set in `netlify.toml`)
5. Click **Deploy**
6. In Netlify → Domain management → add `packsourcela.com` and point DNS

### Subsequent deploys

```bash
git add -A
git commit -m "update products"
git push
```

Netlify auto-deploys on push to `main`.

## Contact Form

Currently the form shows a success state (no actual backend). Options to wire it up:

- **Netlify Forms** (easiest — free, add `netlify` attribute to `<form>`)
- **Formspree** — free tier, forward to email
- **Custom backend** — POST to an API endpoint

See the `// TODO` comment in the JS for where to hook in.

## TODO

- [ ] Wire up contact form (Netlify Forms or Formspree)
- [ ] Add real product photos / images
- [ ] Add Google Analytics / Plausible
- [ ] Add real pricing once confirmed
- [ ] Set up domain DNS in Netlify
- [ ] Add sitemap.xml + robots.txt for SEO
