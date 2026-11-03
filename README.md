# Supabase keep-alive

Envoie une requête tous les 3 jours aux projets Supabase gratuits (Divers.ia, qui héberge Coach.ia, Brain.ia, Inventory.ia et Pause, et Finance Nerd) pour éviter leur mise en pause après 7 jours d'inactivité.

Chaque projet est pingé indépendamment : si l'un échoue, l'autre est quand même pingé, et la tâche devient rouge à la fin (GitHub envoie un email). Un ping qui échoue avec « Could not resolve host » signifie que le projet est en pause : à restaurer depuis le dashboard Supabase.

Un seul ping par projet suffit : pinger `coach_activities` garde tout Divers.ia actif, donc aussi les tables de Brain.ia, d'Inventory.ia et de Pause. Les tables pingées (`coach_activities`, `flows`) doivent exister et avoir une colonne `id`. Si une table est supprimée ou renommée, change-la dans `.github/workflows/keepalive.yml`.

Le workflow fait aussi un commit automatique environ une fois par mois, pour que GitHub ne désactive pas le workflow planifié (règle des 60 jours sans activité).

Lancement manuel : onglet Actions → Supabase keep-alive → Run workflow.
