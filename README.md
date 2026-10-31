# Endla Vishnu Vardhan — Portfolio

Personal portfolio for an AI/ML-focused software engineer: selected projects, current experience, technical skills, education, and contact links.

- Live site: https://vishnuendla.github.io/Portfolio/
- Stack: hand-written HTML, CSS, and a small SVG icon — no framework, no build step
- Deployed with GitHub Actions to GitHub Pages

## Repository structure

```text
.
├── index.html                  # The whole page: hero, work, experience, about, education, contact
├── assets/
│   ├── css/portfolio.css       # Design tokens, layout, components, responsive rules
│   ├── img/favicon.svg         # Person mark used as favicon and page ornament
│   └── resume/endla-vishnu-vardhan-resume.pdf
├── .github/
│   ├── workflows/pages.yml     # CI validation and GitHub Pages deployment
│   └── pull_request_template.md
└── README.md
```

Anything referenced from `index.html` uses a path relative to the repository root (`assets/...`). CI fails if a local link or asset does not resolve.

## Featured projects

| Project        | What it is                                                                                                                                       | Stack                                                                                                    | Link                                                                |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| **Odyssey**    | Full-stack travel journal for documenting trips with photos and places, exploring public journals, and replaying routes on a map and timeline.   | React 18, TypeScript, Vite, Tailwind CSS, Leaflet, Java 17, Spring Boot 3.2, Spring Security, JWT, MySQL | [vishnuendla/odyssey](https://github.com/vishnuendla/odyssey)       |
| **Voice Lab**  | Browser voice lab: speak in the tab and hear a spoken reply through a Pipecat speech → LLM → speech pipeline, with optional conversation memory. | Python, Pipecat, Sarvam, Groq, OpenRouter, FastAPI, WebSockets, PostgreSQL                               | [vishnuendla/voice-lab](https://github.com/vishnuendla/voice-lab)   |
| **Calculator** | Four-function calculator with chained operations and a single reset, written as one static page.                                                 | HTML, CSS, JavaScript                                                                                    | [vishnuendla/Calculator](https://github.com/vishnuendla/Calculator) |

Project copy on the page is based on each repository's README and source. Keep it factual: describe what exists, not what is planned.

## Editing the site

- **Sections and copy** live in `index.html`. Each section has an `id` used by the header navigation: `home`, `work`, `experience`, `about`, `contact`.
- **Colors, spacing, and typography** are defined once at the top of `assets/css/portfolio.css`; components come after the tokens.
- **Adding a project**: add an `<article class="project-card">` inside `.project-grid`, give it an art block, meta stack line, description, `.project-points` highlights, and a repository link. Then add a row to the table above.
- **Resume**: the two résumé links both point to `assets/resume/endla-vishnu-vardhan-resume.pdf`. Keep that single PDF in the folder and replace it to update the download; CI fails if the file is missing or if extra PDFs are added.
- **Contact details**: the email appears in the header CTA and the contact section; LinkedIn and GitHub appear in the about and contact sections.

## Run locally

Open `index.html` directly, or serve the folder so relative paths behave exactly like production:

```bash
python3 -m http.server 8000
```

Then visit http://localhost:8000/.

## CI and deployment

`.github/workflows/pages.yml` runs on every push and pull request targeting `dev` or `main`:

1. **Validate static site** — HTML validation and required-asset checks, plus verification that every local `href`/`src` and in-page anchor resolves.
2. **Deploy GitHub Pages** — only on a push to `main`, after validation passes. The workflow uses the Pages actions artifact, so no `gh-pages` branch is needed.

The deployed URL is configured as the canonical link and Open Graph URL in `index.html`. If the site moves to a custom domain, update those tags.

## Branching and pull requests

| Branch | Purpose                                  |
| ------ | ---------------------------------------- |
| `main` | Production. Every push deploys the site. |
| `dev`  | Integration branch for completed work.   |

Flow:

1. Branch from `dev` using a `feat/`, `fix/`, `docs/`, `ci/`, or `refactor/` prefix.
2. Commit with a conventional, imperative subject: `feat: add project filters`, `fix: repair mobile navigation`, `docs: document deployment`.
3. Open a pull request into `dev` and use the PR template. Wait for the validation check to pass, then squash-merge and delete the branch.
4. Open a release pull request from `dev` into `main` once `dev` is stable. Merge only after its checks pass; the merge triggers deployment.
5. After a release, fast-forward `dev` back onto `main` so the two branches do not drift.

Current work: the portfolio page, project descriptions, and this README.

## Accessibility notes

The page ships a skip link, semantic landmarks, labelled navigation, visible focus styles, `prefers-reduced-motion` handling, and descriptive link text. Keep those when editing; describe images with `alt` text and mark purely decorative artwork `aria-hidden="true"`.

## Contact

- Email: vishnuendla12@gmail.com
- LinkedIn: https://www.linkedin.com/in/vishnu-vardhan-564372283/
- GitHub: https://github.com/vishnuendla
