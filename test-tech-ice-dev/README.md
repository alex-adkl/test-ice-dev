📌 Test Technique - Ice Dev

Ce projet est un test technique pour Ice Development développé avec Vue.js 3, Vite et Tailwind CSS.
Il s’agit d’une interface permettant la gestion des patients d’un cabinet médical, avec un menu de navigation latéral et un menu mobile interactif.


📂 Arborescence du projet

test-tech-ice-dev
│── public/                # Fichiers statiques
│── src/                   # Code source du projet
│   ├── assets/            # Images, icônes, styles globaux
│   ├── components/        # Composants Vue.js
│   │   ├── AppHeader.vue  # Barre de navigation supérieure
│   │   ├── AppMenu.vue    # Menu latéral / mobile
│   │   ├── AppTop.vue     # Section "Les patients du cabinet"
│   │   ├── AppSearch.vue  # Barre de recherche des patients
│   │   ├── AppPatientCard.vue # Cartes des patients
│   ├── App.vue            # Composant racine Vue.js
│   ├── main.js            # Point d’entrée du projet
│── .gitignore             # Fichiers à ignorer par Git
│── package.json           # Dépendances et scripts du projet
│── vite.config.js         # Configuration Vite
│── README.md              # Documentation du projet


⚡ Installation et utilisation

🔧 Pré-requis
	•	Node.js (≥ 16.x)
	•	npm ou yarn

📥 Installation

	1.	Cloner le dépôt :
  git clone https://github.com/alex-adkl/test-ice-dev.git
  cd test-tech-ice-dev
  
	2.	Installer les dépendances :
  npm install
  # ou avec yarn
  yarn install

  🏃 Démarrage du projet

  Lancer le serveur de développement :
  npm run dev
  # ou
  yarn dev

  Le projet sera accessible à http://localhost:5173/.
