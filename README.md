# Panel Club 7-7

Panel de direction du Club 7-7 (patronne et manager) : to-do, choix à venir, services, achats, stock, contrats, carte & recettes, réunions.
Site statique (un seul `index.html`) branché sur Firebase pour que les données soient partagées en direct.

## Mise en place (une seule fois)

1. **Créer le projet Firebase** sur https://console.firebase.google.com → « Ajouter un projet » (Google Analytics pas nécessaire).
2. **Firestore** : menu *Firestore Database* → « Créer une base de données » → mode production → région `eur3` (Europe).
   Onglet *Règles* : colle le contenu de `firestore.rules` → *Publier*.
3. **Connexion** : menu *Authentication* → « Commencer » → active **E-mail/Mot de passe**.
   Onglet *Utilisateurs* → « Ajouter un utilisateur » : un compte pour la patronne, un pour la manager.
4. **Clé du site** : *Paramètres du projet* (roue crantée) → *Vos applications* → icône `</>` (Web) → donne un nom → copie l'objet `firebaseConfig` dans `firebase-config.js`.
5. **Vercel** : https://vercel.com → *Add New… → Project* → importe ce dépôt GitHub → *Deploy* (aucun réglage à changer).
6. **Domaine autorisé** : dans Firebase → *Authentication* → *Paramètres* → *Domaines autorisés* → ajoute l'adresse donnée par Vercel (ex. `club77-panel.vercel.app`).

À la première connexion, le panel se remplit tout seul avec la carte (mocktails, cocktails, offres) et le stock contenus dans `seed.json`.

## Fichiers

- `index.html` : le panel
- `firebase-config.js` : la configuration de ton projet Firebase
- `firestore.rules` : règles de sécurité à coller dans Firebase
- `seed.json` : données de départ (carte et stock)
