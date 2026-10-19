# Règles du dépôt (labo-info-pass)

Alignées sur labo-tech-info-2, labo-tech-info-3 et tech-info-1.

## Quiz (strict)

1. **Pas de gras sur les réponses** — le texte des choix (liste d’options et récap) reste en graisse normale, y compris un éventuel `<strong>` / `<b>` imbriqué. Idem pour le texte de feedback / verdict du débrief. Le libellé de la question (stem) peut rester en emphase UI.
2. **Ordre des réponses aléatoire** — à chaque chargement de page et à chaque « Recommencer », mélanger `question.options` côté client (`shuffleAllOptions`). La correction compare toujours `answers[id]` à `question.correct` (valeurs stables `A`/`B`/…), pas la position affichée.

Tout nouveau `quiz_seance_*.html` doit reprendre ces comportements (voir les stubs existants).
