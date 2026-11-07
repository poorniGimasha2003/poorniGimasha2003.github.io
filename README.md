# Poorni Pathirage — Portfolio

Personal portfolio website. Plain HTML, CSS and JavaScript in one file (`index.html`) — no build step.

## Folder structure

```
portfolio/
├── index.html          ← the whole website
├── cv.pdf              ← linked from "Download CV"
├── .nojekyll           ← tells GitHub Pages to serve files as-is
├── README.md
└── images/
    ├── profile.jpg
    ├── projects/       ← pruning, bedsense, smartpaw, ecom photos
    └── awards/         ← hult, brainstorm, sliot, biofusion, vertex photos
```

## Editing content

Open `index.html` and scroll to the block marked **EDIT YOUR DETAILS HERE** near the top of the `<script>`:

- `ME` — email, LinkedIn, GitHub links
- `PROJECTS` — project text, photos, tech tags and GitHub `link`
- `AWARDS` — award text and photos
- `SKILLS` — skill groups (also used by the skill sphere)

A photo can be written as `"images/x.jpg"` or with a caption: `["images/x.jpg", "Caption text"]`.
Photos whose file does not exist yet are hidden automatically.

## Before you deploy: add your CV and GitHub links

**CV** — `cv.pdf` in this folder is your October 2026 CV. To use a newer one, replace it with your new PDF
and keep the exact name `cv.pdf` (lowercase).

**GitHub repo links** — open `index.html` in VS Code and search (Ctrl/Cmd + F) for `link:`. There are 4 lines,
one per project. Each one currently points to your GitHub profile. Replace each with that project's repo link:

```js
link:"https://github.com/poorniGimasha2003/your-repo-name"
```

| Project | Line to edit |
|---|---|
| Structural Pruning | the `link:` with comment "pruning repo" |
| BedSense | the `link:` with comment "BedSense repo" |
| Smart Paw | the `link:` with comment "Smart Paw repo" |
| E-Commerce ML Pipeline | the `link:` with comment "e-commerce repo" |

If a repo is **private**, write `link:null` instead. The GitHub button then disappears for that project.

Check your work: double-click `index.html` to open it in your browser, click each GitHub button, then deploy.

## Deploy on GitHub Pages

1. Go to github.com → **New repository** → name it exactly `poorniGimasha2003.github.io` → Public → Create.
   (If you already have this repo, open it and delete the old files first.)
2. Click **Add file → Upload files**, drag in everything inside this folder
   (`index.html`, `cv.pdf`, `README.md`, `.nojekyll` and the `images` folder) → **Commit changes**.
3. Open **Settings → Pages** → Source: **Deploy from a branch** → Branch: `main`, folder `/ (root)` → Save.
4. Wait 1–2 minutes, then visit **https://poorniGimasha2003.github.io**

To update later: upload the changed files again to the same repo; the site refreshes in about a minute.

## Free custom domain (optional)

**Option A — `poorni.is-a.dev` (free forever)**
1. Fork https://github.com/is-a-dev/register
2. Add `domains/poorni.json`:
   ```json
   { "owner": { "username": "poorniGimasha2003" },
     "records": { "CNAME": "poorniGimasha2003.github.io" } }
   ```
3. Open a pull request and wait for it to be merged.
4. In your portfolio repo: **Settings → Pages → Custom domain** → `poorni.is-a.dev` → Save → tick **Enforce HTTPS**.

**Option B — `.me` domain free for 1 year (GitHub Student Developer Pack)**
1. Verify at https://education.github.com/pack with your sjp.ac.lk email.
2. Claim the Namecheap `.me` offer (e.g. `poornipathirage.me`).
3. In Namecheap DNS add four **A** records for `@`:
   `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   and one **CNAME** for `www` → `poorniGimasha2003.github.io`
4. In your repo: **Settings → Pages → Custom domain** → your domain → Save → tick **Enforce HTTPS**.

You no longer need CloudFront — GitHub Pages already provides hosting and HTTPS.
