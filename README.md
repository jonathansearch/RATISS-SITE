# RATISS-SITE

**The project to build the canonical RATISS Labs website** — turning 66 scattered
research repositories into a coherent site, explained page by page, discoverable by
Google, linked to GitHub (code), Zenodo (DOI) and Search Console (measurement).

> "GitHub holds what we do. Zenodo preserves what we publish.
> The DOI identifies the version. The site explains the research. Google makes it
> discoverable. RATISS connects research to its verification."

## Repository contents

| Item | Role |
|---|---|
| [`WORKFLOW-SITE-RATISS-v1.md`](WORKFLOW-SITE-RATISS-v1.md) | **The complete execution plan** (12 sections): decisions D1–D6, mapping fragments → canonical pages → real repositories, Research Manifest, agent pipeline A1→A4 with human approval, 10 showcase pages mapped, Zenodo/DOI, SEO/Search Console, sequence S1→S9 |
| [`docs/PLAN-GPT-ADOPTED.md`](docs/PLAN-GPT-ADOPTED.md) | The reference plan adopted by the chief (36 points: real Google discovery mechanics, manifests, Zenodo, Search Console, mistakes to avoid) |
| [`site-base/`](site-base/) | **The base site** — exact copy of [`ratiss-labs-site`](https://github.com/jonathansearch/ratiss-labs-site) (master branch), verified 8/8 identical files. "RATISS Labs — independent laboratory, Yaoundé" · "We don't believe. We replay." |

```text
site-base/
├── index.html                    263,346 B — single embedded page (5,180 lines)
└── _fragments/
    ├── photon.html.frag          → will become /research/photon/
    ├── navier.html.frag          → will become /research/navier-stokes/
    ├── quantique.html.frag       → will become /research/qpu-ambient/
    ├── fusion.html.frag          → will become /research/fusion-icf/
    ├── etalons.html.frag         → will become /protocols/etalons/
    ├── glossaire.html.frag       → will become /glossaire/
    └── blog.html.frag            → will become /blog/
```

## Status: frozen material — nothing built yet

This repository contains the **starting point**: the plan + the raw material.
The construction (rebuild as a tree of canonical pages, `research.yaml` manifests,
publication pipeline, Vercel, domain, Search Console, Zenodo) will happen
**later**, on the chief's order, following workflow §10 (S1→S9).

The 6 decisions to settle before any work (D1–D6, workflow §2):
domain · host · source repository · language · GitHub account · size of the first batch.

## RATISS discipline

- The site **points to** the 66 real repositories — it duplicates nothing.
- No agent publishes without **the chief's approval**.
- No number is published without an original source — replay before publishing.
- Verified/claimed separation, append-only registry in RATISS-ARCHIVES.

---

RATISS Labs — Jonathan Evina (Yaoundé, Cameroon) · ORCID
[0009-0000-4092-5313](https://orcid.org/0009-0000-4092-5313)
