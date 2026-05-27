# Evolutcine - Plateforme de Streaming

Site de streaming pour regarder films et séries en ligne. Interface moderne avec catégories, recherche rapide et lecteur fluide.

## 🎬 Caractéristiques

- Interface Netflix-like avec design moderne
- Système de profils utilisateurs
- Lecteur vidéo HLS adaptatif
- Recommandations basées sur l'historique
- Favoris et historique de visionnage
- Support du contrôle parental
- Qualités multiples (4K, HDR, Dolby Vision, Atmos)
- Responsive design

## 🛠️ Stack Technologique

### Frontend
- Next.js 14 (App Router)
- React 18
- TypeScript
- Tailwind CSS
- Framer Motion (animations)
- HLS.js (streaming vidéo)

### Backend
- Express.js
- Node.js
- Prisma ORM
- PostgreSQL
- Redis (cache & sessions)

### Infra
- Docker & Docker Compose
- Nginx (reverse proxy)
- Node Media Server (RTMP/HLS)

## 📁 Structure du Projet

```
streaming-platform/
├── apps/
│   ├── web/                    # Next.js 14 frontend
│   └── api/                    # Express.js backend
├── packages/
│   ├── shared/                 # Types & utilities
│   ├── database/               # Prisma + migrations
│   └── ui/                     # Shared components
├── docker-compose.yml
└── nginx.conf
```

## 🚀 Démarrage Rapide

### Prerequisites
- Node.js 18+
- Docker & Docker Compose
- PostgreSQL 16+

### Installation

```bash
# Cloner le repo
git clone https://github.com/nathanbeaupere2-beep/evolutcine.git
cd evolutcine

# Installer les dépendances
npm install

# Configuration
cp .env.example .env.local

# Lancer avec Docker
docker-compose up -d

# Migrations BD
cd apps/web
npx prisma migrate dev
```

### Développement

```bash
# Frontend (http://localhost:3000)
cd apps/web
npm run dev

# Backend (http://localhost:3001)
cd apps/api
npm run dev
```

## 📦 Packages

### @evolutcine/shared
Types TypeScript communs et utilitaires partagés

### @evolutcine/database
Prisma client avec schéma complet et migrations

### @evolutcine/ui
Composants React réutilisables (HeroBanner, ContentRow, VideoPlayer, etc.)

## 🗄️ Modèles de Données

- **User** - Utilisateurs avec authentification
- **Profile** - Profils multiples par utilisateur
- **Content** - Films, séries, documentaires
- **Season/Episode** - Pour les séries
- **WatchHistory** - Historique de visionnage
- **Favorite** - Favoris des utilisateurs
- **CastMember** - Acteurs et réalisateurs

## 🎨 Composants Principaux

### Frontend
- `HeroBanner` - Banneau héros avec vidéo de trailer
- `ContentRow` - Carrousel horizontal de contenu
- `VideoPlayer` - Lecteur vidéo HLS avancé
- `Navbar` - Navigation sticky avec recherche
- `ContentCard` - Carte de contenu avec preview

## 📝 API Routes

- `GET /api/content?category=trending|new|recommended|continue` - Récupérer du contenu
- `POST /api/content` - Créer du contenu (admin)
- `GET /api/profiles` - Lister les profils
- `POST /api/watch-history` - Enregistrer la progression

## 🔐 Authentification

- JWT avec NextAuth
- Support SSO/SAML
- Profils multiples
- PIN parental

## 📊 Performance

- ISR (Incremental Static Regeneration)
- Image optimization avec Next.js
- Rate limiting sur l'API
- Compression gzip
- Cache Redis
- Streaming HLS adaptatif

## 📄 Licence

MIT

## 👤 Auteur

Nathan Beaupere
