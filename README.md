# Trinity Fuels (Pty) Ltd — Website

One self-contained file: `index.html`. Everything — layout, styling, fonts reference, images and behaviour — lives inside this single file. Nothing else to install, no build step, no other files required.

7 pages, all inside the one file, switched with the address bar's `#` (no reloads):

- `#home` — Home
- `#about` — About Us
- `#products` — Products & Services
- `#coverage` — Coverage
- `#compliance` — Compliance & Governance
- `#resources` — Resources
- `#contact` — Contact / Quote

---

## Why this file didn't show up correctly last time

Last time the site was several files (`index.html`, `about.html`, a `css` folder, a `js` folder, an `assets` folder). If even one of those folders doesn't upload, or GitHub renames a file's case (`t2.JPG` vs `t2.jpg` — GitHub Pages is case-sensitive), the whole thing breaks silently.

This version has **one file**. If that one file is uploaded, the site is complete. There is nothing else that can go missing.

---

## Step-by-step: upload to GitHub and publish

### 1. Create the repository
1. Go to [github.com](https://github.com) and log in.
2. Click the **+** in the top-right corner → **New repository**.
3. Name it something like `trinity-fuels-website`.
4. Set it to **Public** (required for free GitHub Pages).
5. Do **not** tick "Add a README" (we already have one) — or if you do, that's fine too, just don't let it conflict.
6. Click **Create repository**.

### 2. Upload the file
1. On your new repository's page, click **Add file → Upload files**.
2. Drag in `index.html` (and this `README.md` if you'd like it in the repo too).
3. Scroll down and click **Commit changes**.

That's it for uploading — just one file to drag in.

### 3. Turn on GitHub Pages
1. In your repository, click **Settings** (top menu).
2. In the left sidebar, click **Pages**.
3. Under **Build and deployment → Source**, choose **Deploy from a branch**.
4. Under **Branch**, choose `main` and `/ (root)`, then click **Save**.
5. Wait about 30–60 seconds. Refresh the Pages settings screen — a banner will appear saying **"Your site is live at..."** with a link.

### 4. View your site
Your site will be at:
```
https://<your-github-username>.github.io/trinity-fuels-website/
```
Open that link in any browser. Click through Home, About, Products & Services, Coverage, Compliance, Resources and Contact / Quote to confirm everything works.

> If the page looks unstyled or blank, hard-refresh with `Ctrl+Shift+R` (Windows) or `Cmd+Shift+R` (Mac) — this clears a stale cached copy, which is the most common cause of a "broken-looking" GitHub Pages site right after publishing.

### 5. Using a custom domain (optional)
If you'd like the site to appear at **www.TrinityFuels.co.za** instead of the github.io address:
1. In **Settings → Pages → Custom domain**, enter `www.TrinityFuels.co.za` and save.
2. At your domain registrar (wherever TrinityFuels.co.za is registered), add a **CNAME record** pointing `www` to `<your-github-username>.github.io`.
3. Wait for DNS to propagate (can take a few hours), then re-check the Pages settings — GitHub will confirm the domain and issue free HTTPS automatically.

---

## Editing the content later

Everything is in `index.html`:
- **Colours** — search for `:root {` near the top of the `<style>` section; every colour used site-wide is defined there.
- **Text** — each page is a `<section class="page" id="page-home">`, `id="page-about"`, etc. — search for the page name to jump straight to its content.
- **Email addresses / phone numbers** — search for `TrinityFuels.co.za` to find every instance.
- **Logo / photos** — these are embedded directly as long `data:image/...;base64,...` strings, so there's no separate image file to replace. To swap an image, it's easiest to ask for an updated `index.html` with the new picture embedded, rather than hand-editing the base64 text.

## Quote request form

GitHub Pages only serves static files — it can't run server code to email form submissions automatically. Right now, clicking **Submit Request** on the Contact / Quote page opens the visitor's own email app, pre-addressed to `Orders@TrinityFuels.co.za` with their details filled in.

If you'd rather have submissions land directly in your inbox with no email-app popup, connect the form to a free service like **Formspree** or **Web3Forms** — a small, one-time change to the form's code. Happy to make that change if you'd like to go that route.

## Running it locally before uploading

Just double-click `index.html` — it opens in your default browser and works immediately, no server required. (If you use VS Code, the **Live Server** extension also works: right-click `index.html` → *Open with Live Server*.)
