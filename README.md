# Analyse du marché de l'emploi Data

Ce dépôt contient un jeu d'offres d'emploi orienté Data (Science, Analyse, IA) et un notebook d'exploration en R.

## Données brutes (`data/raw/`)
- `job_postings.csv` : méta-infos par offre (`job_link`, `job_title`, `company`, `job_location`, `first_seen`, `search_city`, `search_country`, `search_position`, `job_level`, `job_type`, etc.).
- `job_skills.csv` : compétences listées par offre (`job_link`, `job_skills` séparées par virgule).
- `job_summary.csv` : résumé textuel de chaque offre (`job_link`, `job_summary`).
- Les fichiers sont liés par `job_link`. Le dossier `data/clean/` est prévu pour les versions préparées (actuellement vide).

## Pré-requis
- R (>= 4.0).
- Jupyter + kernel R pour exécuter le notebook (`IRkernel`).

Installation rapide du kernel R :
```r
install.packages("IRkernel")
IRkernel::installspec()  # rend le kernel R disponible dans Jupyter
```

## Exécution de l'analyse
- Option notebook : ouvrir `notebooks/01_exploration.ipynb` dans Jupyter (kernel R) et exécuter toutes les cellules.
- Option Quarto (converti depuis le notebook) : `quarto render report/analysis.qmd --to html` (produit `report/analysis.html` et garde les assets dans `report/analysis_files/`).
- Exécution batch du notebook : `jupyter nbconvert --execute --to html notebooks/01_exploration.ipynb --output report/report.html`

## Organisation des sorties
- Figures : enregistrer les plots dans `figures/` (ex. dans R `png("figures/top_jobs.png", width=1200, height=800); ...; dev.off()`).
- Rapports : exporter le notebook en HTML/PDF dans `report/` (ex. `jupyter nbconvert --execute --to html notebooks/01_exploration.ipynb --output report/report.html`).
