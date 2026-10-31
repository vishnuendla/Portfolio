# Vishnu Vardhan Endla — Portfolio

A responsive, static portfolio site for selected software projects and contact details.

## Projects featured

- [Odyssey](https://github.com/vishnuendla/odyssey) — React and Spring Boot travel journal with maps and timelines.
- [Voice Lab](https://github.com/vishnuendla/voice-lab) — browser voice assistant using Pipecat, Sarvam, and Groq.
- [Calculator](https://github.com/vishnuendla/Calculator) — responsive calculator built with HTML, CSS, and JavaScript.

The page also links to [all public repositories](https://github.com/vishnuendla?tab=repositories). Keep project links and descriptions current as new work ships.

## Run locally

Open `index.html` in a browser or run a static server from this folder, for example `python -m http.server 8000`.

## Branch and pull request flow

- `main` is the production branch and GitHub Pages deployment source.
- `dev` is the integration branch for completed feature work.
- Create work branches from `dev` using `feat/`, `fix/`, `docs/`, `ci/`, or `refactor/` prefixes.
- Open a pull request into `dev`; use a conventional title such as `feat: add project filters` or `fix: repair mobile navigation`.
- After CI passes on `dev`, open a pull request from `dev` to `main`. Merge only after its checks pass.
- CI runs on pushes and pull requests targeting `dev` and `main`. A successful push to `main` deploys the static site with GitHub Pages.

## Improvement backlog

These are good follow-up tasks for Cursor or OpenCode:

1. Add real screenshots and live demos for each project; confirm image rights and deployment URLs first.
2. Add any other verified social profiles.
3. Add project filters, richer case studies, and links to architecture or source documentation.
4. Add an accessible mobile navigation menu and keyboard focus styles, then test with a screen reader.
5. Add social preview metadata, a favicon, and a sitemap if a permanent domain is configured.
6. Configure GitHub branch protection so `dev` and `main` require the CI workflow and changes reach `main` through a pull request.
7. Confirm GitHub Pages is enabled for this repository; deployment uses the GitHub Actions Pages source.

## Content accuracy

Profile and education details are based on the current portfolio. Confirm dates, internship information, contact details, and social URLs before adding more biography content.
