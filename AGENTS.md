# Règles du dépôt (labo-info-pass)

Sources : commits / templates de `labo-tech-info-2`, `labo-tech-info-3`, `tech-info-1`, `methodo-algo` (et conventions proches dans `outils-info-ia`). Aucun `AGENTS.md` / `.cursor/rules` / `CONTRIBUTING` chez les voisins — les règles sont dans le HTML des quiz, le workflow Pages et les messages de commit.

## Quiz (strict)

1. **Pas de gras sur les réponses** — choix (liste + récap) en graisse normale, y compris `<strong>` / `<b>` imbriqués ; idem feedback / verdict du débrief. Stem (énoncé) : emphase UI autorisée.  
   *Sources :* commits « remove bold… » LTI2/LTI3/tech-info-1 ; « pas de gras dans les choix » methodo-algo.
2. **Ordre des réponses aléatoire** — `shuffleAllOptions()` (ou équivalent) au chargement et au reset ; scoring sur `question.correct` (ids stables `value`), pas la position ni la lettre affichée.  
   *Sources :* commits « shuffle quiz answer choices… » LTI2/LTI3/tech-info-1/methodo-algo.
3. **Lettres A–D = ordre visuel uniquement** — dans les données, `label` **sans** préfixe « A. » / « B. » (ni lettre collée au texte du type « Réponse A »). À l’affichage (liste + récap), toujours montrer `A.` `B.` `C.` `D.` selon la position après shuffle (`String.fromCharCode(65 + index)`). Le `value` / `correct` reste l’identité stable pour le scoring.  
   *Sources :* modèle methodo-algo (`orderedOptions` + `letter`) ; bug évité : shuffle inutile si la lettre est hardcodée dans le label.
4. **Titres d’onglet / H1 quiz** — format `Séance N — Quiz` (pas `Labo … — Quiz séance N`).  
   *Sources :* commits « align page titles with Tech Info 1 » ; templates origin LTI2/LTI3/tech-info-1/methodo-algo.

## Titres Pages (strict)

5. **Onglet exercices** — `Séance N — Exercices` (via `page_title` dans `.github/workflows/deploy.yml`).  
6. **Onglet accueil** — `Labo Info Pass — ISIB` (em dash).  
7. **Marp `title` des slides** — `Séance N — <thème>` ; le `header` garde la marque du cours (`Labo Info Pass — Séance N …`).  
   *Sources :* mêmes commits d’alignement des titres ; front matter origin des labos voisins.

## Contenu quiz (quand on remplit pour de vrai)

8. **~10 QCM** par séance une fois le quiz réel rédigé (pratique tech-info-1 / methodo-algo).  
9. **Pas d’indice « leading »** dans l’énoncé qui donne la réponse (commit tech-info-1 « strip leading quiz hints… »).  
10. **Mauvaises réponses en rouge** (`--color-error`) : en vigueur sur le template « toutes questions visibles » (tech-info-1 / methodo-algo). Le template LTI2/LTI3/labo-info-pass (une question à la fois + récap) utilise pour l’instant le gris + barré — **ne pas divergir de LTI2/LTI3** sans décision explicite.

## Slides (style)

11. **Pas de tirets cadratins « IA » dans la prose** des slides (séparateurs de propositions) — préférer virgules / parenthèses / points-virgules ; garder `—` dans titres / headers / plages numériques.  
    *Sources :* tech-info-1 « remove AI-style em dashes… » ; outils-info-ia « retire tirets longs… ».

Tout nouveau `quiz_seance_*.html` / page générée doit respecter 1–7 ; 8–11 dès qu’on écrit du contenu pédagogique.
