# SynerVol : Essaim de Drones pour la Recherche et le Sauvetage (SAR)

Bienvenue sur l'organisation GitHub de **SynerVol**, un projet d'ingénierie dédié à la conception d'un système d'essaim de drones intelligent pour assister les services de secours (Sapeurs-Pompiers) dans la recherche de personnes disparues.

---

## Notre Mission

Les premières minutes d'une disparition sont cruciales. SynerVol vise à accélérer les opérations de **Search and Rescue (SAR)** en zones difficiles (plages, forêts, terrains escarpés) grâce à une flotte coordonnée de drones.

* **Simplicité** : Déploiement quasi instantané pour des opérateurs non-pilotes.
* **Rapidité** : Couverture de zones étendues par exploration simultanée.
* **Intelligence** : Architecture **Leader-Follower** avec distribution automatique des consignes GPS.
* **Fiabilité** : Communication hybride 4G (commande longue distance) et LoRa (inter-drones).

---

## Architecture Logicielle & Tech Stack

Le cœur technologique de SynerVol repose sur une approche **modulaire et embarquée**. Nous utilisons **Yocto Project** pour générer un OS sur mesure et **Docker** pour isoler nos services critiques.

### Projet Phare : [docker_system](./docker_system)
C'est le dépôt central qui orchestre l'intelligence embarquée du drone Leader. Il regroupe 5 micro-services essentiels :

| Service | Rôle |
| :--- | :--- |
| **Vite App** | Interface opérateur simplifiée pour le terrain. |
| **Python Backend** | Middleware gérant la logique d'essaim et les données. |
| **AI App (YOLO)** | Détection automatique de victimes par vision par ordinateur. |
| **MAVProxy** | Interface de communication avec le contrôleur de vol ArduPilot. |
| **Cloudflare Tunnel** | Accès distant sécurisé pour le monitoring en temps réel. |

### Releases :
Vous pouvez retrouvez les OS prète à l'emploi [ICI](./releases).

---

## Pipeline de Déploiement

Nous suivons un workflow industriel pour garantir la stabilité en vol :
1. **Développement** : Conteneurisation des services sur Ubuntu.
2. **Intégration** : Compilation via Yocto (Bitbake) pour Raspberry Pi 4.
3. **Déploiement** : Image système immuable incluant le runtime Docker.
4. **Initialisation** : Lancement automatique des services via Systemd au boot du drone.

---

## Objectifs du Projet

- [x] Conception et assemblage des drones Leader/Follower.
- [x] Établissement de la chaîne de communication 4G/LoRa.
- [x] Développement de l'interface utilisateur pompier.
- [ ] Finalisation de la logique de vol coordonné.
- [ ] Tests de validation en conditions réelles.

---

## L'Équipe
Projet réalisé par une équipe d'élèves-ingénieurs en dernière année, passionnés par la robotique et les solutions technologiques au service de l'humain.

---
*SynerVol - La technologie au service du sauvetage.*
