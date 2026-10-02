# RATISS-SITE

**Le chantier du site web canonique de RATISS Labs** — transformer 66 dépôts de
recherche dispersés en un site cohérent, expliqué page par page, découvrable par
Google, relié à GitHub (code), Zenodo (DOI) et Search Console (mesure).

> « GitHub contient ce que nous faisons. Zenodo conserve ce que nous publions.
> Le DOI identifie la version. Le site explique la recherche. Google la rend
> découvrable. RATISS relie la recherche à sa vérification. »

## Contenu du dépôt

| Élément | Rôle |
|---|---|
| [`WORKFLOW-SITE-RATISS-v1.md`](WORKFLOW-SITE-RATISS-v1.md) | **Le plan d'exécution complet** (12 sections) : décisions D1–D6, cartographie fragments → pages canoniques → dépôts réels, Research Manifest, pipeline agents A1→A4 avec approbation humaine, 10 pages vitrines mappées, Zenodo/DOI, SEO/Search Console, séquence S1→S9 |
| [`docs/PLAN-GPT-ADOPTED.md`](docs/PLAN-GPT-ADOPTED.md) | Le plan de référence adopté par le chef (36 points : mécanisme réel de découverte Google, manifests, Zenodo, Search Console, erreurs à éviter) |
| [`site-base/`](site-base/) | **Le site de base** — copie conforme de [`ratiss-labs-site`](https://github.com/jonathansearch/ratiss-labs-site) (branche master), vérifiée 8/8 fichiers identiques. « RATISS Labs — laboratoire indépendant, Yaoundé » · « On ne croit pas. On rejoue. » |

```text
site-base/
├── index.html                    263 346 o — page unique intégrée (5 180 lignes)
└── _fragments/
    ├── photon.html.frag          → deviendra /research/photon/
    ├── navier.html.frag          → deviendra /research/navier-stokes/
    ├── quantique.html.frag       → deviendra /research/qpu-ambient/
    ├── fusion.html.frag          → deviendra /research/fusion-icf/
    ├── etalons.html.frag         → deviendra /protocols/etalons/
    ├── glossaire.html.frag       → deviendra /glossaire/
    └── blog.html.frag            → deviendra /blog/
```

## État : matériel gelé — rien construit

Ce dépôt contient le **point de départ** : le plan + la matière première.
La construction (refonte en arbre de pages canoniques, manifests `research.yaml`,
pipeline de publication, Vercel, domaine, Search Console, Zenodo) se fera
**après**, sur ordre du chef, en suivant le workflow §10 (S1→S9).

Les 6 décisions à trancher avant tout travail (D1–D6, workflow §2) :
domaine · hébergeur · dépôt source · langue · compte GitHub · taille du premier lot.

## Discipline RATISS

- Le site **pointe** vers les 66 dépôts réels — il ne duplique rien.
- Aucun agent ne publie sans **approbation du chef**.
- Aucun chiffre publié sans source d'origine — replay avant publication.
- Coupure vérifié/affirmé, registre append-only dans RATISS-ARCHIVES.

---

RATISS Labs — Jonathan Evina (Yaoundé, Cameroun) · ORCID
[0009-0000-4092-5313](https://orcid.org/0009-0000-4092-5313)
