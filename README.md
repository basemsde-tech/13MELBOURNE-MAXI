# 13melbourne maxi — booking website

Single-page, mobile-first booking site for **13 Melbourne Maxi** (maxi taxis, wheelchair-accessible
transport, airport transfers and parcel runs across Melbourne).

Live domain: **https://13melbournemaxi.com.au**

It is a static site — pure HTML, CSS and JavaScript in one file (`index.html`), no build step,
no server, no database. Bookings are handled entirely on the device: the form compiles the trip
details and opens the customer's phone dialer (Call) or messaging app (SMS) pre-filled to
`0466 999 048`. There is no email or backend.

---

## Files in this repository

| File | Purpose |
|------|---------|
| `index.html` | The entire website (HTML + CSS + JS, self-contained). |
| `404.html` | Branded "page not found" fallback. |
| `CNAME` | Tells GitHub Pages to serve the site on `13melbournemaxi.com.au`. |
| `robots.txt` | Allows search engines and points to the sitemap. |
| `sitemap.xml` | Helps Google index the site. |
| `.gitignore` | Keeps OS/editor junk out of the repo. |

---

## How to publish it (GitHub Pages)

### 1. Create the repository
1. On GitHub, click **New repository**.
2. Name it anything (e.g. `13melbournemaxi`), set it **Public**, and create it.
3. On the new repo page choose **uploading an existing file** (or **Add file → Upload files**).
4. Drag in **all** the files from this folder (`index.html`, `404.html`, `CNAME`,
   `robots.txt`, `sitemap.xml`, `.gitignore`) and **Commit changes**.

### 2. Turn on GitHub Pages
1. Go to **Settings → Pages**.
2. Under **Build and deployment**, set **Source = Deploy from a branch**.
3. Choose branch **`main`** and folder **`/ (root)`**, then **Save**.
4. After a minute your site is live at `https://<your-username>.github.io/<repo>/`.

### 3. Connect the custom domain `13melbournemaxi.com.au`
The `CNAME` file already contains the domain, so GitHub will pick it up automatically.
You just need to point the domain's DNS at GitHub (do this with your domain registrar):

**Apex domain (`13melbournemaxi.com.au`)** — add four **A** records:

```
A   @   185.199.108.153
A   @   185.199.109.153
A   @   185.199.110.153
A   @   185.199.111.153
```

**(Optional) `www` subdomain** — add one **CNAME** record:

```
CNAME   www   <your-username>.github.io
```

Then in **Settings → Pages → Custom domain**, confirm `13melbournemaxi.com.au` is shown,
and once DNS has propagated tick **Enforce HTTPS**.

> DNS changes can take anywhere from a few minutes to 24 hours to take effect.

---

## Editing the site later

Everything is in `index.html`. Common edits:

- **Phone number** — search the file for `0466999048` (the dial/SMS links) and
  `0466&nbsp;999&nbsp;048` (the on-screen text) and replace both.
- **Copy / headings** — edit the text inside the `<h1>`, `<h2>`, `<h3>` and `<p>` tags.
- **Service suburbs** — the address auto-complete list is the `<datalist id="melb">` block.
- **Colours** — change the CSS variables at the top of the `<style>` block
  (`--gold`, `--obsidian`, etc.).

Commit the change and GitHub Pages redeploys automatically within a minute.

---

© 13 Melbourne Maxi. All rights reserved.
