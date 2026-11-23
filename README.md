# Chepkungurwet Foundation — Hugo website

A responsive, static Hugo website rebuilt from the supplied Django HTML templates and content. It is designed for GitHub Pages deployment.

## Requirements
- Hugo Extended (the included GitHub Actions workflow installs Hugo automatically)
- A GitHub repository

## Preview locally
1. Install Hugo Extended.
2. From this folder run `hugo server -D`.
3. Open the local URL printed by Hugo (normally http://localhost:1313).

## Publish using GitHub Pages
1. Create or open the GitHub repository that will contain the website.
2. Upload the **contents** of this folder to the repository root (the `.github` folder must also be uploaded).
3. Edit `hugo.toml` and replace `YOUR-USERNAME` and `YOUR-REPOSITORY` in `baseURL` with your GitHub username and repository name. Example: `https://janedoe.github.io/community-site/`.
4. Push/commit the files to the `main` branch.
5. In GitHub, open **Settings → Pages** and set **Build and deployment → Source** to **GitHub Actions**.
6. Open the **Actions** tab and wait for “Deploy Hugo site to GitHub Pages” to complete. Your site URL will be `https://YOUR-USERNAME.github.io/YOUR-REPOSITORY/`.

For a repository named `YOUR-USERNAME.github.io`, set `baseURL = "https://YOUR-USERNAME.github.io/"` (no repository subpath).

## Content editing
- Edit pages in `content/` (`about.md`, `impact.md`, `programs.md`, `gallery.md`, `contact.md`, `donate.md`).
- Edit branding and layout in `layouts/`.
- Edit styles in `static/css/site.css`.
- Keep the existing `Gallery/` folder at the repository root with its `team/`, `program/`, and `partners/` subfolders. Hugo publishes this folder as static assets. The homepage, team section, program pages and gallery already reference these image paths.

## Important scope and functionality notes
The supplied files are Django templates, not a complete standalone static site. Django template tags, URL routing, server-side forms, authentication, admin dashboards, database-backed donations, gallery management and payment callbacks require a Django application and backend services. GitHub Pages serves static files only, so those backend features cannot run in this Hugo build.

This build includes the public-facing pages (Home, About, Impact, Programs, Gallery, Contact and Donate) as a static Hugo site. The admin pages and Django-only payment success/failure flows are not reproduced as functioning features. The Donate page directs visitors to contact the Foundation to confirm official payment details; it does not collect payments. The Contact page uses direct email/phone links rather than a nonfunctional static form.

The original image files were not included in the uploaded HTML batch. The site therefore uses a custom graphic/typographic design rather than referencing missing Django `static/images/...` assets. Add the Foundation's approved logo and photographs before publishing if available.
