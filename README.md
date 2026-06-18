# Jomo — about page

Static landing page served at **about.thejomoapp.com** via GitHub Pages.
Linked from QR codes on printed flyers. Contains an embedded intro video,
a call-to-action to try the app (https://thejomoapp.com), and a contact email.

The intro video is the YouTube Short `yGAJxfBpPvQ`
(https://youtube.com/shorts/yGAJxfBpPvQ), embedded in a vertical 9:16 frame.

## Deploy (one-time setup)

This folder is meant to live in its **own public repo**, not the main `jomo`
monorepo (GitHub Pages on a private repo needs a paid plan, and we don't want to
make the monorepo public).

```bash
# From inside this folder:
git init
git add .
git commit -m "Jomo about page"
git branch -M main
# Create a new PUBLIC repo on github.com (e.g. jomo-about), then:
git remote add origin git@github.com:<you>/jomo-about.git
git push -u origin main
```

Then in the new repo on GitHub:

1. **Settings → Pages → Build and deployment → Source: Deploy from a branch**,
   branch `main`, folder `/ (root)`. Save.
2. The `CNAME` file already sets the custom domain to `about.thejomoapp.com`.
   GitHub will pick it up automatically.

## DNS

At your DNS provider for `thejomoapp.com`, add a **CNAME** record:

| Type  | Name (host) | Value                  |
|-------|-------------|------------------------|
| CNAME | `about`     | `<you>.github.io`      |

After DNS propagates, enable **Enforce HTTPS** in Settings → Pages.
