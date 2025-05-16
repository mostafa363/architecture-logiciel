# User Service - VendreFacile

Ce service est responsable de la gestion des comptes utilisateurs, de l'authentification, et des profils utilisateurs pour la plateforme VendreFacile.

## Fonctionnalités

- Inscription des utilisateurs
- Connexion / Déconnexion
- Gestion de profil (consultation, mise à jour)
- Récupération de mot de passe (à détailler)
- Gestion des rôles (Utilisateur, Admin)

## Technologies

- Python (FastAPI)
- MongoDB (via Motor pour l'accès asynchrone)
- JWT (JSON Web Tokens) pour l'authentification

## API Endpoints

Une spécification OpenAPI (Swagger) sera disponible sur `/docs` lorsque le service est en cours d'exécution.
Principaux endpoints prévus :

- `POST /users/register` : Inscription d'un nouvel utilisateur.
- `POST /users/login` : Connexion d'un utilisateur et émission d'un token JWT.
- `POST /users/logout` : (Optionnel, si gestion de tokens côté serveur) Invalidation du token.
- `GET /users/me` : Récupérer les informations du profil de l'utilisateur connecté.
- `PUT /users/me` : Mettre à jour le profil de l'utilisateur connecté.
- `GET /users/{user_id}` : (Admin) Récupérer les informations d'un utilisateur spécifique.
- `PUT /users/{user_id}` : (Admin) Mettre à jour un utilisateur spécifique.
- `DELETE /users/{user_id}` : (Admin) Supprimer un utilisateur.

## Variables d'Environnement

Créez un fichier `.env` à la racine de ce service basé sur `.env.example` et configurez les variables :

- `MONGODB_URL`: URL de connexion à la base de données MongoDB.
- `JWT_SECRET_KEY`: Clé secrète pour signer les tokens JWT.
- `JWT_ALGORITHM`: Algorithme pour les tokens JWT (ex: HS256).
- `ACCESS_TOKEN_EXPIRE_MINUTES`: Durée de validité du token d'accès.
- `SERVICE_PORT`: Port sur lequel le service écoute (ex: 8001).
- `ENVIRONMENT`: (ex: development, production)

## Démarrage Local (via Docker Compose)

Ce service est conçu pour être lancé via le `docker-compose.yml` à la racine du projet.

```bash
# Depuis la racine du projet (vendre-facile/)
docker-compose up --build user-service