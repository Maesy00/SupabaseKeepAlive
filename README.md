# Supabase keep-alive

Envoie une requête tous les 3 jours aux projets Supabase gratuits (Aurora/Ironly/Osmosy et Finance Nerd) pour éviter leur mise en pause après 7 jours d'inactivité.

Le workflow (`.github/workflows/keepalive.yml`) fait aussi un commit automatique environ une fois par mois, pour que GitHub ne désactive pas le workflow planifié (règle des 60 jours sans activité).

Lancement manuel : onglet Actions → Supabase keep-alive → Run workflow.
