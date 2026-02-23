# 🏀 Basket Arena – Duel Central
### Édition Tactique – 3 Joueurs (1 Humain + 2 IA)

**Basket Arena** est un jeu de cartes tactique jouable directement dans le navigateur.
Il se joue **sans backend**, en **hébergement statique**, avec une IA avancée et un système de duels basé sur les statistiques **OFF / DEF**.

👉 Aucun compte, aucune installation, aucun serveur requis.

---

## 🎯 Concept du jeu

- 3 équipes : **Vous**, **IA 1**, **IA 2**
- Chaque équipe aligne **5 joueurs**
- Objectif : être le **premier à 10 points**
- À chaque attaque :
  - Lancer de dé 🎲
  - Duel **OFF vs DEF**
  - Gestion tactique des remplacements
- Les rôles tournent dynamiquement entre les équipes

---

## 🧠 Mécaniques principales

- Contraintes strictes de composition :
  - 5 joueurs sur le terrain
  - Minimum **1 S**, **1 M**, **1 L**
  - Maximum **2 joueurs par poste**
  - Ordre obligatoire : **S → M → L**
- IA capable de :
  - Choisir la meilleure cible
  - Optimiser ses remplacements
  - Ajuster sa stratégie après chaque panier
- Animation des duels + feedback visuel
- Système de logs chronologique

---

## 📂 Structure du projet

```
JEU_CARTE_2025/
├─ index.html
├─ data/
│  └─ players.csv
├─ cartes2/
│  └─ TEAM_card_ID.png
```

---

## 📄 Format du fichier CSV

Le jeu attend un CSV séparé par `;` avec **au minimum** les colonnes suivantes :

```csv
PLAYER_ID;NAME;Poste;OFF;DEF;TEAM_x
```

Exemple :

```csv
12;Durant, Kevin;M;9;7;BKN
```

- `Poste` doit être : `S`, `M` ou `L`
- Les images doivent suivre le format :
  ```
  cartes2/TEAM_card_PLAYER_ID.png
  ```

---

## 🚀 Lancement en local

⚠️ Le jeu **ne fonctionne pas en double-cliquant sur le fichier HTML**
(utilisation de `fetch()` → serveur requis)

### Option 1 – Python (recommandé)

```bash
python -m http.server 8000
```

Puis ouvrir :

```
http://localhost:8000/index.html
```

### Option 2 – VS Code

- Installer l’extension **Live Server**
- Clic droit sur `index.html` → *Open with Live Server*

---

## 🌐 Publication gratuite (statique)

Le jeu est compatible avec :

- **GitHub Pages**
- **Netlify**
- **Cloudflare Pages**

Aucune configuration particulière requise.
Il suffit d’héberger les fichiers tels quels.

---

## 🔄 Chargement des données

Au lancement :
1. Le jeu tente de charger automatiquement :
   ```
   data/players.csv
   ```
2. Si le fichier est introuvable ou bloqué :
   - Un **upload manuel** est proposé en fallback

---

## 🛠️ Technologies utilisées

- React 18 (CDN)
- Tailwind CSS (CDN)
- JavaScript moderne (ES6+)
- Canvas Confetti
- 100% frontend, zéro backend

---

## 🏆 Auteur

Projet expérimental de jeu tactique.
Bon match 🏀🔥
