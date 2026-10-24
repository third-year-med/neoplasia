# CLAUDE.md — a module of the Interactive Pathology Teaching Platform

This repository is one module (a single `index.html`): **Neoplasia** (module key `neoplasm`, storage prefix `nm_`,
Chapter 4 on the front page, after Inflammation & Healing). Built 2026-10-19 from scratch, condensed (high-yield) from the
start (HANDBOOK §4.2), with the app code of `cell-injury-condensed`. It has nothing to do with the deleted old Neoplasia test
(`Neoplasia-platform`, key `neoplasia`) — never reuse that key.

The platform's decisions, the checklist for modules, the deployment steps, the testing workflow and the lessons learned are
in the platform repository: `third-year-med/Interactive-pathology-platform` → `CLAUDE.md` and `docs/HANDBOOK.md`
(rebuilds: `docs/REBUILD.md`).

- The course data in `index.html` is encrypted with this module's OWN content key, which lives only in the user's Code.gs
  (`CONTENT_KEYS.neoplasm`). Never commit a key or an unencrypted copy of the course.
- The `<script id="platform-nav">` block is maintained in the platform repo (`modules/platform-nav.js`) and written here
  with `tools/module-release.js refresh` — do not edit it by hand.
- Stable IDs: topics t01–t16 (t15 = Practical, t16 = Integration), sections sNNMM, questions q001–q301 (q001–q147 source MCQs,
  q148–q191 source vignettes, q192–q301 written for the module), cases c01–c16. A new build keeps them (`docs/REBUILD.md`).
- The Robbins picture-import files (`neo-picture-import`; Basic Robbins Ch. 6: keys `nm-robbins6-01…39`; Big Robbins / Pathologic Basis
  of Disease Ch. 7, 2026-10-24: keys `nm-robbins-pbd-01…16` — 5 repeats of the first set left out, 2 cropped to their new panel) and the Official Exams question bank
  (`xq_nm001…088`) are delivered to the user directly and are never committed (textbook figures / exam answers).
- The drafted Practicals for Exercises 19–20 (8 records `Ex. 19.1…20.4`, from Topic 15; 2026-10-24) are delivered to the user as a
  JSON reply + source .txt for Apply → Practical → ✨ Create from PDF → 📋 Claude.ai — copy & paste; never committed (unencrypted course text).
- Test changes on the real page with the platform repo's e2e test "Neoplasia module (neoplasm)" (`NM_CONTENT_KEY` in the
  environment) and `node test/module-smoke/smoke.js` before pushing.
