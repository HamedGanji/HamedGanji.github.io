# Hamed F. Ganji — Quarto personal website starter

A small original Quarto website inspired by the structure of Robin Lovelace's professional site: biography, research, software/projects, scientific posts, publications, CV, contact and GitHub-profile crosslinks.

**This is a starter project, not a deployed site.** Please verify and refine the biography, career descriptions and publications before making it public.

## 1. Prerequisites (Windows / VS Code)

- [Git](https://git-scm.com/downloads)
- [Quarto](https://quarto.org/docs/get-started/)
- [VS Code](https://code.visualstudio.com/) and its Quarto extension (optional)
- A GitHub account

## 2. Make the site yours

1. Replace `YOUR_GITHUB_USERNAME` in `_quarto.yml`, `index.qmd`, `software.qmd`, `contact.qmd` and `github-profile/README.md` with your **actual** GitHub username.
2. Replace `assets/portrait-placeholder.svg` with an authorized portrait; update `index.qmd` to point to its filename.
3. Check the bio, employer, years and education on `index.qmd` / `cv.qmd`; these are draft starter texts.
4. Replace the sample post and add your verified journal publications with DOI links.
5. Do not add secret or proprietary content anywhere in the public GitHub repo.

## 3. Preview locally

Open this folder in VS Code and run:

```powershell
quarto preview
```

Or render the static website:

```powershell
quarto render . --to html
```

To generate the PDF CV from the **same** `cv.qmd` source:

```powershell
quarto render cv.qmd --to typst --output cv.pdf
Copy-Item cv.pdf _site/cv.pdf
```

**Note:** We did not execute Quarto in the authoring environment; run a local preview before publishing.

## 4. Create a new GitHub Pages repository

To obtain a clean address like `https://YOUR_GITHUB_USERNAME.github.io/`, create a public GitHub repository named **exactly** `YOUR_GITHUB_USERNAME.github.io`. (Use your actual username.)

From the project directory:

```powershell
git init
git branch -M main
git add .
git commit -m "Initial Quarto website"
git remote add origin https://github.com/YOUR_GITHUB_USERNAME/YOUR_GITHUB_USERNAME.github.io.git
git push -u origin main
```

If the repo already has a README or commits, first clone it or synchronize instead of forcing a push.

In the GitHub repository, choose **Settings → Pages → Build and deployment → Source → GitHub Actions**. The workflow `.github/workflows/deploy.yml` builds the HTML site and CV.pdf and deploys `_site`. On successful deployment the site appears at `https://YOUR_GITHUB_USERNAME.github.io/`.

## 5. Point the custom domain hamedfganji.nl to the site (later)

Only when you own the domain:

1. In GitHub repo **Settings → Pages**, enter the custom domain `hamedfganji.nl` and save.
2. At your DNS registrar, create apex `A` records for GitHub Pages:

   - `185.199.108.153`
   - `185.199.109.153`
   - `185.199.110.153`
   - `185.199.111.153`

3. Optionally add `www` as a `CNAME` pointing to `YOUR_GITHUB_USERNAME.github.io` (not to the apex domain).
4. Verify the domain in GitHub when possible, wait for DNS / certificate provisioning, and enable **Enforce HTTPS**.
5. When the custom domain works, replace temporary github.io links in your profile README with `https://hamedfganji.nl/` paths.

Reference: https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site

## 6. Make your GitHub profile link to your site

Create another public repository whose name **exactly matches your GitHub username**, e.g. if your username is `sample`, create a repository named `sample`. Copy `github-profile/README.md` to that repository's root as `README.md`.

Then in GitHub **Profile → Edit profile**, set the **Website** field to your live website URL. Pin your strongest public repositories.

## 7. Password-protected sections — IMPORTANT

GitHub Pages is static hosting with **no server-side login system**. This starter deliberately does **not** pretend to secure pages using a JavaScript password check. If you use StatiCrypt, encrypt sensitive HTML before publishing and ensure the original `.qmd`, source datasets, searchable indexes and public attachments do not leak the protected material. The better option for truly confidential material is separate hosting with access controls (or an authenticated service). Keep confidential sources outside the public repository. Avoid listing password-protected pages in public Quarto searches.

## 8. Add articles

Duplicate `posts/2026-11-20-sound-pressure/`, rename its folder to a new `YYYY-MM-DD-topic`, and update the article metadata/title/content. The Articles page will list the new post automatically.

## 9. Further improvements

- Populate the publication list from a BibTeX or Zotero export.
- Add a research photo, project diagrams and GitHub repo cards.
- Refine the responsive CSS, accessibility and metadata.
- Integrate secure protected research notes via a separate authenticated service.

## Useful links

- https://quarto.org/docs/websites/
- https://quarto.org/docs/publishing/github-pages.html
- https://github.com/Robinlovelace/robinlovelace.net
