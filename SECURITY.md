# Politique de sécurité

## Périmètre

Ce dépôt est un **projet académique** : un prototype de surveillance par caméra
(API FastAPI, simulateur ONNX, dashboard Next.js), sans déploiement en
production ni support garanti. Il est publié tel quel, sous licence MIT.

| Version | Suivie |
| --- | --- |
| `main` (dernier commit) | oui, au mieux |

Sont dans le périmètre :

- l'API FastAPI (`main.py`, `models.py`, `services.py`, `database.py`) ;
- le simulateur et les scripts (`simulator.py`, `convert_to_onnx.py`, `setup.ps1`) ;
- le dashboard Next.js (`dashboard/`) ;
- tout secret ou donnée personnelle publié par erreur, y compris dans l'historique.

Hors périmètre : Supabase, Ultralytics, ONNX Runtime, Next.js et les autres
dépendances (à signaler à leurs mainteneurs), ainsi que les limites déjà
listées dans le [README](README.md#limites) (API sans authentification, CORS
ouvert en développement).

## Signaler une vulnérabilité

Ne pas ouvrir d'issue publique. Utiliser le signalement privé de GitHub :
onglet **Security**, puis **Report a vulnerability**. Indiquer le fichier ou
le commit concerné, les étapes pour reproduire et l'impact attendu. Ne pas
joindre la valeur complète d'une clé : son emplacement suffit.

Projet personnel : la réponse se fait au mieux, sans délai garanti.

## Rappels pour les utilisateurs

- La clé Supabase **`service_role`** ne s'utilise que côté serveur (`.env` de
  l'API). Le dashboard n'utilise que la clé **`anon`** : les variables
  `NEXT_PUBLIC_*` sont envoyées au navigateur.
- Activer la sécurité au niveau des lignes (RLS) sur la table `alerts` avant
  d'exposer le dashboard.
- Une caméra filme des personnes : respecter le droit applicable à la
  vidéosurveillance et à la protection des données avant tout usage réel.
