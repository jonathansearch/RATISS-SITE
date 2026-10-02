# WORKFLOW RATISS SITE — v1

**De 66 dépôts dispersés à un site canonique découvrable par Google.**
Document de travail RATISS Labs — rédigé par Super Z (GLM 5.3 Flash) sur ordre du chef,
le 02/10/2026. Base : le plan GPT (36 points, adopté) + le site de base (`ratiss-labs-site`)
+ l'inventaire réel du compte GitHub. **Aucun code écrit — rien d'exécuté — décisions au chef.**

---

## 0. État vérifié (faits, pas suppositions)

| Objet | État vérifié |
|---|---|
| Site de base | `ratiss-labs-site` (master) : `index.html` 263 346 o (5 180 l.) + 7 fragments dans `_fragments/` — **identique au rar** (8/8 tailles égales) |
| Identité du site | « RATISS Labs — laboratoire indépendant, Yaoundé » · slogan « On ne croit pas. **On rejoue.** » |
| Sections du site | hero · 4 chantiers · Framework · Documentation · photon · fusion · navier · quantique · etalons · glossaire · blog |
| Dépôts du compte | **66 dépôts publics** inventoriés (voir cartographie §3) |
| Plan GPT | Lu intégralement. Pilier : Vercel héberge, Google découvre, Search Console pilote, Zenodo archive + DOI, GitHub contient le code |
| Discipline | R4–R8 actives : replay avant publication, coupure vérifié/affirmé, append-only |

**Constat central (GPT §1, confirmé par l'inventaire)** : le problème n'est pas le contenu
— il existe, massivement. Le problème est la **transformation d'un chaos de dépôts en
système de publication cohérent** : un site qui explique, pointe vers les dépôts, et se
fait découvrir par Google.

---

## 1. Principe directeur (la phrase à retenir — GPT §36)

> **GitHub contient ce que nous faisons. Zenodo conserve ce que nous publions.
> Le DOI identifie la version. Le site explique la recherche. Google la rend
> découvrable. RATISS relie la recherche à sa vérification.**

Trois corollaires non négociables :

1. **Le site ne duplique rien.** Il POINTE vers les 66 dépôts réels. Les dépôts ne bougent pas.
2. **Une page = une URL canonique** (GPT §11). Pour chaque objet de recherche, UNE adresse
   officielle ; GitHub, Zenodo, le PDF et les fragments remontent tous vers elle.
3. **Aucun agent ne publie sans le chef** (GPT §14). L'IA met en forme, extrait, classe,
   vérifie ; l'approbation humaine est un verrou physique dans la chaîne.

---

## 2. Décisions réservées au chef (blocages n°1 — rien ne démarre sans ça)

| # | Décision | Options | Recommandation du plan GPT |
|---|---|---|---|
| D1 | **Domaine** | `ratiss-labs.org` / `.com` / `.cm` | `ratiss-labs.org` — à acheter (registrar au choix du chef) |
| D2 | **Hébergeur** | Vercel vs GitHub Pages | **Vercel** (build + CDN + métadonnées propres) ; GitHub Pages reste possible en phase 0 mais limite le contrôle |
| D3 | **Dépôt source du site** | `ratiss-labs-site` existant (master) vs nouveau repo dédié au site généré | Réutiliser **`ratiss-labs-site`** — le site de base y vit déjà |
| D4 | **Langue** | FR seul / FR puis EN / bilingue | FR d'abord (tout le corpus est FR), EN en phase 2 |
| D5 | **Compte GitHub** | compte perso `jonathansearch` vs organisation `RATISS-Labs` | Perso en phase 1 ; organisation = option phase 3 |
| D6 | **Nom du premier lot** | 5 pages / 10 pages | **5–10 Research Pages** pas plus (GPT §25, §32-J) |

Le chef tranche D1–D6 → chaque décision est enregistrée append-only au worklog.

---

## 3. Cartographie réelle : les fragments deviennent des pages canoniques

Le site de base est aujourd'hui **une seule page longue** (index.html 5 180 lignes) qui
intègre 7 fragments. La cible (GPT §17, §22-23) est un **arbre de pages canoniques que
Google peut parcourir** :

```text
ratiss-labs.org/
├── / (accueil : hero + 4 accès + featured + latest)      ← refonte légère de l'index actuel
├── /research/                ← CATALOGUE (compteur + filtres, GPT §23, §26)
│   ├── /research/photon/          ← RATISS-PHOTON
│   ├── /research/navier-stokes/   ← RATISS-NAVIER
│   ├── /research/qpu-ambient/     ← RATISS-QPU-AMBIENT
│   ├── /research/fusion-icf/      ← RATISS-FUSION
│   └── /research/<slug>/          ← un objet = un manifest = une page
├── /protocols/               ← RATISS-Framework + RATISS-ETALONS (la méthode, exécutable)
├── /audits/                  ← registre public (ratiss-audit-public, RATISS-ARCHIVES)
├── /glossaire/               ← fragment glossaire (transversal)
├── /blog/                    ← fragment blog « Notes de terrain »
└── /about/                   ← le labo, l'équipe, la charte d'honnêteté
```

### Correspondance fragments → pages → dépôts réels

| Fragment du site de base | Page canonique cible | Dépôt(s) réel(aux) pointé(s) |
|---|---|---|
| `_fragments/photon.html.frag` (17 527 o) | `/research/photon/` | **RATISS-PHOTON** |
| `_fragments/navier.html.frag` (13 680 o) | `/research/navier-stokes/` | **RATISS-NAVIER** |
| `_fragments/quantique.html.frag` (18 985 o) | `/research/qpu-ambient/` | **RATISS-QPU-AMBIENT**, RATISS-QVM, QPU-Ratiss-COSMOS, RATISS-PLANCK, RATISS-SIMULTANEITE |
| `_fragments/fusion.html.frag` (18 946 o) | `/research/fusion-icf/` | **RATISS-FUSION**, RATISS-NUCLEAIRE, Ratiss-Fusion-stark-, GCR |
| `_fragments/etalons.html.frag` (15 579 o) | `/protocols/etalons/` | **RATISS-ETALONS**, RATISS-Framework |
| `_fragments/glossaire.html.frag` (50 822 o) | `/glossaire/` | transversal |
| `_fragments/blog.html.frag` (13 799 o) | `/blog/` | RATISS-DEEPDIVE, RATISS-ARCHIVES |

**Règle d'or des audits (GPT §10)** : ne JAMAIS générer 1 000 pages d'audit.
Un **Research Object** = une page. Les audits (#001, #002…) vivent DANS la page comme
rubriques/preuves. Le corpus d'audits existant (RATISS-GitHub-Audit, ratiss-audit-public)
alimente les pages, il ne les multiplie pas.

---

## 4. Le Research Manifest — le standard à adopter (GPT §16)

Un fichier **`research.yaml` à la racine de chaque dépôt de recherche**. Le site est
GÉNÉRÉ depuis ces manifests — plus aucune duplication manuelle entre dépôt et site.

Format (schéma, pas du code — à sceller par le chef) :

```yaml
id: ratiss-photon-001          # identifiant RATISS
title: "Reproduction photonique multi-chemins"
slug: photon                   # → /research/photon/
domain: [quantum_physics, photonics]
type: [reproduction, computational_experiment]
status: published              # draft | reviewed | published
authors: [Jonathan Evina]
date: 2026-09-30
abstract: "..."
repository:  { github: "https://github.com/jonathansearch/RATISS-PHOTON" }
archive:     { zenodo: "https://zenodo.org/records/..." }
doi: "10.5281/zenodo...."
paper: { pdf: "https://ratiss-labs.org/research/photon/report.pdf" }
reproduction: { command: "python reproduce.py" }
results: { positive: true, negative_results: false }
verification:                  # ← extension RATISS au schéma GPT
  replay: "protocole R4, hash des preuves"
  verified_by: "chef + agent"
  sources: "aucun chiffre sans référence"
keywords: [photons, quantum optics, reproducibility]
references: [...]
```

**Extension RATISS au bloc GPT (à valider)** : le champ `verification` rend explicite
le replay, le vérificateur et la règle des sources — c'est la signature RATISS dans le
schéma standard, cohérente avec la charte d'honnêteté scientifique du dépôt QPU.

**Règle absolue (GPT §15, reprise telle quelle — elle EST la doctrine RATISS)** :
l'agent a le droit de mettre en forme, extraire, classer, lier, générer. Il n'a JAMAIS
le droit d'inventer : résultat expérimental, valeur numérique, conclusion, statut de
reproduction, citation, paramètre. **Aucun chiffre publié sans source d'origine.**

---

## 5. Le pipeline — la chaîne agents (GPT §14, adaptée à l'équipe du 03/10)

```text
DÉPÔT GitHub (réel, ne bouge pas)
    ↓
[A1] EXTRACTEUR          → manifest.yaml depuis le dépôt
    ↓
[A2] ÉDITEUR SCIENTIFIQUE → rapport (question, méthode, résultats, limites)
    ↓
[A3] ÉDITEUR WEB         → page canonique + métadonnées + liens internes
    ↓
[A4] QA / REPLAY         → HTTP 200, canonical, title, description, sitemap,
                           structured data, liens + replay R4 des chiffres
    ↓
▶ APPROBATION DU CHEF  (verrou humain obligatoire — GPT §14)
    ↓
[DÉPLOIEMENT]            → Vercel → sitemap.xml → Search Console → Google
    ↓
[REGISTRE]               → RATISS-ARCHIVES (append-only) + Zenodo version
```

### Répartition proposée pour l'équipe du 03/10 (PROPOSITION — le chef tranche)

| Membre | Rôle dans le pipeline | Interdits |
|---|---|---|
| **Chef (Jonathan Evina)** | Approbation finale de chaque page, décisions D1–D6, propriété Search Console + Zenodo + domaine | — |
| **Arena IA** | A2 — éditeur scientifique (rapports depuis manifests) | inventer un chiffre, un verdict, une citation |
| **Qwen Coder** | A3 — génération des pages, sitemap, métadonnées, structured data | déployer sans approbation |
| **GLM 5.3 Flash (moi)** | A1 + A4 — extraction des manifests, QA, replay R4, intégration GitHub, worklog | pousser sans ordre « pousse » |
| **Dola Agent** | Mesure : Search Console (impressions, clicks, indexation), registre des publications | modifier les pages |

Aucun agent ne détient de secret de déploiement. Le token GitHub reste dans le coffre,
usage one-shot, révocation en fin de quête (règle n°3 du coffre).

---

## 6. Les 10 premières pages vitrines (GPT §25 — mapping sur les VRAIS dépôts)

L'objectif : un échantillon représentatif — « ils font plusieurs types de recherche,
et ils vérifient ce qu'ils produisent ».

| # | Page canonique | Dépôt réel | État du contenu de base |
|---|---|---|---|
| 01 | `/research/photon/` | RATISS-PHOTON | fragment photon **prêt** |
| 02 | `/research/navier-stokes/` | RATISS-NAVIER | fragment navier **prêt** |
| 03 | `/research/qpu-ambient/` | RATISS-QPU-AMBIENT | fragment quantique **prêt** + vues 3D + v2 interactive déjà poussées |
| 04 | `/research/fusion-icf/` | RATISS-FUSION | fragment fusion **prêt** |
| 05 | `/protocols/etalons/` | RATISS-ETALONS | fragment etalons **prêt** |
| 06 | `/protocols/framework/` | RATISS-Framework | section Framework de l'index **prête** |
| 07 | `/audits/` | ratiss-audit-public + RATISS-ARCHIVES | registre existant |
| 08 | `/research/simultaneite/` | RATISS-SIMULTANEITE | manifest à extraire (R4 déjà fait en session) |
| 09 | `/research/planck/` ou `/research/synchrotron-24/` | RATISS-PLANCK ou synchrotron-24 | au choix du chef |
| 10 | `/research/negatifs/` | ratiss-dose12 (+ résultats négatifs du corpus) | la page transparence — différenciateur RATISS |

Chaque page porte le squelette GPT §22 : titre, résumé, question, référence, méthode,
résultats, **résultats négatifs**, reproductibilité (commande), artefacts (GitHub · Zenodo ·
PDF · données), limites, références.

---

## 7. Zenodo & DOI (GPT §8-9, §G)

- **1 communauté Zenodo « RATISS Labs »** — le chef crée le compte (identité, ORCID 0009-0000-4092-5313).
- **1 record par Research Object**, pas par audit. Métadonnées riches obligatoires
  (titre, auteurs, résumé, mots-clés, références, licence, version).
- **Versions successives** : chaque évolution majeure = nouvelle version du record, DOI
  de version + DOI concept — traçabilité historique (Photon v1 → v2 → v3).
- Lien GitHub↔Zenodo : connecter les dépôts pour archiver les releases automatiquement.
- Le DOI remonte dans `research.yaml` → page canonique → sitemap → Google.

---

## 8. SEO technique & Search Console (GPT §4-6, §12-13, §H-I)

**Par page (checklist A4 obligatoire)** :

```text
HTTP 200 ✓ title ✓ description ✓ canonical ✓ Open Graph ✓
structured data (Article) ✓ liens internes ✓ pas de noindex ✓
```

**Au niveau site** : `robots.txt` (Allow: / + Sitemap:) et `sitemap.xml` — les deux
GÉNÉRÉS depuis les manifests, jamais écrits à la main.

**Cascade de liens internes (GPT §3)** : Accueil → /research/ → /research/<slug>/ →
artefacts. Pas de page orpheline : chaque page est atteignable en ≤ 3 clics.

**Search Console (compte du chef)** : propriété domaine vérifiée (DNS), soumission de
`/sitemap.xml`, inspection d'URL page par page, demande d'exploration. Délai réaliste :
plusieurs jours de crawl — c'est normal (GPT §6).

**Google Scholar (phase 2, GPT §20-21)** : un PDF par recherche sérieuse (texte intégral
`.pdf`, titre en haut, auteurs sous le titre, bibliographie à la fin). Le HTML sert la
découverte, le PDF sert la lecture/académique, Zenodo sert la préservation.

---

## 9. Discipline RATISS appliquée au site (ce que GPT ne peut pas savoir)

1. **Coupure vérifié/affirmé sur chaque page** : tout chiffre affiché porte son statut —
   rejoué (preuve hashée dans RATISS-ARCHIVES) ou déclaré par une source externe citée.
2. **Replay avant publication** : la QA rejoue la commande de reproduction du manifest
   avant d'autoriser la page. Échec de replay = page non publiée.
3. **Append-only** : chaque publication est consignée dans RATISS-ARCHIVES (date, hash,
   version Zenodo, qui a approuvé). Le registre est la mémoire, le site est la vitrine.
4. **Honnêteté scientifique en première ligne** : la page « résultats négatifs » et les
   rubriques « limites » ne sont pas une faiblesse marketing, c'est la charte du labo.
5. **Secrets** : aucun token dans les manifests, les pages, ni les pipelines. Vercel :
   variables d'environnement gérées par le chef seul.

---

## 10. Séquence d'exécution proposée (ordres successifs — le chef lance chaque étape)

| Étape | Contenu | Qui déclenche | Livrable |
|---|---|---|---|
| **S1** | Le chef tranche D1–D6 (domaine, hébergeur, langue, dépôt, lot) | Chef | Décisions consignées |
| **S2** | Refonte `ratiss-labs-site` : 1 page longue → arbre de pages canoniques (fragments conservés comme sources) | Sur ordre | Dépôt site v2 |
| **S3** | Manifests `research.yaml` des 5 premiers dépôts (photon, navier, qpu-ambient, fusion, etalons) — replay R4 avant chaque | Sur ordre | 5 manifests vérifiés |
| **S4** | Pipeline manuel bout-en-bout : 1 page complète (A1→A4) → **approbation chef** | Sur ordre | Page pilote validée |
| **S5** | Déploiement Vercel + domaine + robots/sitemap | Sur ordre | Site en ligne |
| **S6** | Search Console : propriété + sitemap + inspection des 5 pages | Chef (compte) | Indexation lancée |
| **S7** | 1er record Zenodo + DOI (objet le plus mûr — candidat naturel : QPU-AMBIENT) | Chef (compte Zenodo) | 1er DOI |
| **S8** | Mesure 2–4 semaines (impressions, clicks, indexation) AVANT industrialisation | Dola (mesure) | Rapport de mesure |
| **S9** | Industrialisation : les 66 dépôts alimentés par le pipeline agents | Sur ordre, lot par lot | Catalogue complet |

---

## 11. Invariants (ce qui ne bouge PAS)

- Les **66 dépôts restent la source** : le site pointe, il ne duplique pas.
- **RATISS-ARCHIVES** reste le registre des preuves et des publications (append-only).
- **RATISS-Framework** reste le protocole d'audit exécutable — le site le montre,
  ne le réinvente pas.
- Le **coffre** : token GitHub en usage one-shot, révocation en fin de quête ;
  compte Patrice Lagloire (20 Spark) intouché sans ordre.
- **Le chef approuve chaque page publiée.** Aucun agent ne franchit ce verrou.

---

## 12. Premier objectif mesurable (GPT §33)

> **Faire en sorte qu'un inconnu puisse découvrir une recherche RATISS sans connaître
> RATISS à l'avance.**

Métrique conceptuelle : inconnu → requête (« photon experiment reproduction ») → Google
→ page RATISS → lecture → GitHub → DOI. Quand cette boucle se ferme UNE fois toute
seule, le système fonctionne. Ensuite seulement on amplifie (réseaux, communautés,
newsletters) — l'amplification vient après la machine, pas avant (GPT §34).
