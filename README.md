# funda-calendar

Cache automatique du calendrier économique (ForexFactory / faireconomy), rafraîchi
chaque jour par GitHub Actions.

Le serveur de génération des posts trading (`daily_funda_report.py`) ne peut pas
récupérer ForexFactory directement (IP de datacenter bloquées, HTTP 429). Ce dépôt
sert de relais : un workflow GitHub récupère le calendrier depuis les runners
GitHub (IP non bloquées) et le commit ici. Le flow le lit ensuite via l'URL raw.

**Données publiques uniquement** (calendrier économique public). Aucun secret.

- `ff_calendar.json` : calendrier de la semaine (title, country, date, impact, forecast, previous).
- `.github/workflows/refresh-calendar.yml` : rafraîchissement quotidien (05:30 UTC) + manuel.
