# QuaiAntiqueRestaurantBack

Projet Symfony 6.4 — API REST pour la gestion d’un restaurant (back-end).  
Documenté avec Swagger / NelmioApiDocBundle.

---

## Prérequis

- PHP 8.1 ou supérieur
- Composer
- XAMPP (Apache + MySQL)
- Symfony CLI
- Navigateur web (pour Swagger UI)

---

## Installation locale

### 1. Cloner le dépôt

```bash
git clone https://github.com/ton-utilisateur/QuaiAntiqueRestaurantBack.git
cd QuaiAntiqueRestaurantBack
```

### 2. Installer les dépendances PHP

```bash
composer install
```

### 3. Créer le fichier `.env.local`

```bash
cp .env .env.local
```

Puis configure ta base de données, par exemple :

```
DATABASE_URL="mysql://root:@127.0.0.1:3306/restaurant_db?serverVersion=5.7"
```

### 4. Créer la base de données

```bash
php bin/console doctrine:database:create
php bin/console doctrine:migrations:migrate
```

---

## Lancer le serveur local

```bash
symfony server:start
```

Ou via XAMPP : place le projet dans `htdocs/` et accède à `http://localhost/QuaiAntiqueRestaurantBack/public`.

---

## 🔍 Documentation de l’API

Accessible à l'adresse suivante :

```
http://localhost:8000/api/doc
```

Générée avec **NelmioApiDocBundle**, elle inclut tous les endpoints disponibles, les schémas de requête et les réponses.

---

## Endpoints principaux

- `POST /api/registration` — Créer un utilisateur
- `POST /api/login` — Connexion
- `GET /api/account/me` — Informations de l'utilisateur connecté
- `PUT /api/account/edit` — Modifier son compte
- `POST /api/restaurant` — Ajouter un restaurant
- `GET/PUT/DELETE /api/restaurant/{id}` — Affichage / modification / suppression

---

## Tests

Tests fonctionnels réalisés via Swagger UI et Postman :

- Validation des statuts HTTP
- Vérification des champs obligatoires
- Contrôle des réponses JSON
- Authentification via token `X-AUTH-TOKEN`

---

## Structure du projet

- `/src/Controller/` — Contrôleurs API
- `/src/Entity/` — Entités Doctrine
- `/config/` — Configuration (routes, services, bundles)
- `/public/` — Point d’entrée HTTP (accessible via Apache ou Symfony CLI)

---

## Licence

Projet réalisé dans le cadre d’une formation Studi.
