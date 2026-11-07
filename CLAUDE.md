# peter.sitati — Hugo portfolio at https://sitati.github.io/ ; its job: a visitor emails Peter about work

## Routing
| When the task is… | Load / do |
|---|---|
| any edit to `static/resume*.html` | change the gitignored master `peter_sitati_cv.md` first, then all seven; run `.claude/skills/cv-render/` (renders PDFs, 2pp, no dashes, hugo build) |
| a CV claim, date, employer or credit | application-writing rules in memory: no em/en dashes, verify authorship in git before crediting Peter, no claims about the employer's process |
| naming a product, client or stack anywhere public (site, CVs, Botpool, outreach, prototypes) | memory `feedback_naming_rule` (decided 2026-11-07): own products named with link and stack; client work described by domain and outcome, never named, no stack badges, one proof number per project; "Plopped" → "Gut Trainer" only once the App Store listing is live |
| adding or changing an image | memory `feedback_image_asset_pipeline`: original to `image-originals/` first, ship WebP via `magick … -strip … -quality 82 -define webp:method=6` or SVG, cards 1024x559 |
| site copy, hero, about, contact | `hugo.yaml` `params:` only; theme is the `themes/hugo-profile` submodule, override in `layouts/`, never edit the submodule |
| positioning, who the site is for | `agent-ops/positioning.md` + memory `feedback_base_not_market` (Kenya is base, not market) |
| Done line (stage 0) | park anchors in `~/.claude/projects/-Users-matrix-Downloads-src-peter-sitati/memory/parked_*.md`, each Next item ends `verify with:` |
| direction (stage 1) | that memory dir + `agent-ops/positioning.md`; metric = work enquiries in Gmail, counted by hand (no analytics on the site) |
| find what to build (stage 2) | `all-roads-to-rome` + `open-doors` on https://sitati.github.io/ and `/resume*.html`; Rome = an email sent (decided 2026-11-07); no login, no test account |
| design (stage 3) | global `clickable-prototype` + `impeccable:impeccable`, nothing repo-specific |
| state-coverage (stage 4) | pages: `/` sections per `hugo.yaml` (hero, about, experience, education, projects, contact) + 7 `/resume*.html`; boot `hugo server` → http://localhost:1313 ; viewports desktop + 375x667; no pages.json |
| artifact-waves (stage 5) | skipped 2026-11-07: 0 issues in sitati/sitati.github.io; reopen when a prototype or audit yields 3+ issues |
| accept (stage 6) | skipped 2026-11-07: no issue tracker in use, no hand-recorded prod checks; reopen with the first filed issue |
| behaviour-rubric (stage 7) | skipped 2026-11-07: 0 recorded enquiries; reopen at the first 10 enquiry emails |
| promote to infra (stage 8) | bound: dash sweep (rule set 2026-09-12, swept once) now fails `cv-render`; the twice-run claims audit (2026-08-29, 2026-09-14) stays manual |

## Ground truth
- Deploy: `git push origin main` → `.github/workflows/hugo.yml` → GitHub Pages, Hugo 0.157 extended, `TZ=Africa/Nairobi`. Every path deploys; there is no `paths:` filter.
- Test gate: `.claude/skills/cv-render/render.sh --check` must exit 0 before any commit (local hugo is 0.169, CI is 0.157).
- Pre-push: `reviewer` agent on `origin/main..main`; push itself is the user's call.
- `jobs/`, `peter_sitati_cv.md`, `image-originals/`, `.claude/` are gitignored on purpose (public repo). `jobs/botpool_*` must stay in step with the CVs by hand.
- Public address is `peter.sitati@narstechnical.co.ke` everywhere (site, CVs, Botpool, outreach); no other address goes public (decided 2026-11-07).
- `hugo --quiet | tail` hides failures; `hugo -d <dir> > log 2>&1; echo $?` and grep `^ERROR`.

## Never
- Hand-edit a PDF, commit a `review-*.png`, or edit `themes/hugo-profile`.
- Push without the user saying so.
- Name a client, or put a stack list on a client project, without that client's written consent.
