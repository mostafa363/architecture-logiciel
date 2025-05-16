# VendreFacile - Plateforme de Petites Annonces

L'entreprise VendreFacile souhaite lancer une plateforme web de petites annonces gratuites, inspirée de LeBonCoin. Ce projet vise à permettre la publication, la consultation et la recherche d'annonces, ainsi que les interactions entre vendeurs et acheteurs via une messagerie interne.

## Table des Matières

- [Architecture d'Ensemble](#architecture-densemble)
- [Structure du Dépôt](#structure-du-dépôt)
- [Technologies Utilisées](#technologies-utilisées)
- [Prérequis](#prérequis)
- [Démarrage Rapide (Local)](#démarrage-rapide-local)
- [Documentation Détaillée](#documentation-détaillée)
- [Équipe Projet](#équipe-projet)

## Architecture d'Ensemble

VendreFacile est conçu selon une architecture microservices pour assurer la scalabilité, la maintenabilité et la résilience.
Les principaux composants sont :

- **Frontend**: Application web ReactJS.
- **API Gateway**: Point d'entrée unique pour les requêtes du client.
- **Services Backend**:
    - `user-service`: Gestion des comptes utilisateurs et profils.
    - `ad-service`: Gestion des annonces (CRUD, recherche).
    - `messaging-service`: Messagerie interne entre utilisateurs.
    - `notification-service`: (Fonctionnalité souhaitée) Gestion des alertes et notifications.
- **Base de données**: MongoDB (base de données NoSQL distribuée).
- **Conteneurisation**: Docker pour l'environnement de développement et de production.

Pour plus de détails, voir le [document d'architecture](./docs/architecture.md).

## Structure du Dépôt

- `api-gateway/`: Configuration et Dockerfile pour l'API Gateway.
- `services/`: Contient les microservices backend (Python/FastAPI).
    - `user-service/`
    - `ad-service/`
    - `messaging-service/`
    - `notification-service/` (si implémenté)
- `frontend/`: Application ReactJS.
- `docs/`: Documentation technique du projet (diagrammes, décisions d'architecture).
- `docker-compose.yml`: Fichier pour orchestrer tous les services en local.
- `.github/`: Workflows CI/CD (GitHub Actions).

Chaque service et le frontend possèdent leur propre `README.md` avec des instructions spécifiques.

## Technologies Utilisées

- **Frontend**: ReactJS, JavaScript/TypeScript
- **Backend (Microservices)**: Python (FastAPI/Flask)
- **Base de données**: MongoDB
- **API Gateway**: (À définir - ex: Kong, Nginx, custom)
- **Conteneurisation & Orchestration**: Docker, Docker Compose (Kubernetes pour le cloud)
- **Messagerie Asynchrone**: (À considérer pour la communication inter-services - ex: RabbitMQ, Kafka)

## Prérequis

Avant de commencer, assurez-vous d'avoir installé :

- Docker Engine
- Docker Compose
- Node.js et npm (pour le développement frontend direct si besoin)
- Python 3.x (pour le développement backend direct si besoin)
- Git

## Démarrage Rapide (Local)

1.  Clonez le dépôt :
    ```bash
    git clone <URL_DU_DEPOT>
    cd vendre-facile
    ```

2.  (Optionnel) Créez les fichiers `.env` à partir des `.env.example` dans chaque service et le frontend, puis configurez les variables d'environnement nécessaires (ex: clés API, secrets de base de données). Pour un démarrage rapide, les valeurs par défaut pourraient suffire.

3.  Lancez tous les services avec Docker Compose :
    ```bash
    docker-compose up --build
    ```
    L'option `--build` reconstruit les images si des changements ont été faits dans les Dockerfiles.

4.  Une fois tous les conteneurs démarrés :
    - L'application frontend sera accessible sur `http://localhost:3000` (ou le port configuré).
    - L'API Gateway sera accessible sur `http://localhost:8000` (ou le port configuré).
    - MongoDB sera accessible sur `mongodb://localhost:27017` (par défaut).

## Documentation Détaillée

- [Document d'Architecture](./docs/architecture.md)
- [Spécifications API](./docs/api-specs/) (à venir)
- [Décisions d'Architecture (ADRs)](./docs/adrs/) (à venir)

## Équipe Projet

- **PO / Client**: 1
- **Dev Senior**: 1
- **Dev Juniors**: 2
- **QA**: 1
- **Architectes Logiciels (Vous)**

---