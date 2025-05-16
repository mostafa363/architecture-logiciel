```markdown
# VendreFacile - Application Frontend (ReactJS)

Cette application est l'interface utilisateur web pour la plateforme VendreFacile.

## Fonctionnalités

- Affichage et recherche d'annonces
- Inscription et connexion des utilisateurs
- Gestion du profil utilisateur
- Publication et gestion des annonces (pour les utilisateurs connectés)
- Messagerie interne
- Gestion des favoris

## Technologies

- ReactJS (avec Create React App ou Vite)
- JavaScript / TypeScript
- Axios (pour les appels API)
- React Router (pour la navigation)
- State Management (ex: Context API, Zustand, Redux)
- CSS Framework (ex: Tailwind CSS, Material-UI, Bootstrap)

## Scripts Disponibles

Dans le répertoire du projet, vous pouvez exécuter :

### `npm start` ou `yarn start`

Lance l'application en mode développement.
Ouvrez [http://localhost:3000](http://localhost:3000) pour la voir dans le navigateur.
La page se rechargera si vous faites des modifications.
Vous verrez également les erreurs de lint dans la console.

### `npm test` ou `yarn test`

Lance le runner de test en mode interactif.

### `npm run build` ou `yarn build`

Construit l'application pour la production dans le dossier `build/`.
Il regroupe correctement React en mode production et optimise la construction pour les meilleures performances.

## Variables d'Environnement

Créez un fichier `.env` à la racine de ce projet basé sur `.env.example`.
Exemple de variable :

- `REACT_APP_API_GATEWAY_URL`: L'URL de base de l'API Gateway (ex: `http://localhost:8000/api`)

## Démarrage Local (via Docker Compose)

Le frontend est conçu pour être servi via le `docker-compose.yml` à la racine du projet principal. Il est généralement servi par un conteneur Nginx.

```bash
# Depuis la racine du projet (vendre-facile/)
docker-compose up --build frontend