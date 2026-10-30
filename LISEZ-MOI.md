# RECOUVREMENT TMF — mise en ligne (Firebase + Render)

## 1. Firebase (une seule fois, ~10 min)
1. https://console.firebase.google.com → **Ajouter un projet** (ex. `recouvrement-tmf`).
2. **Authentication → Commencer → Adresse e-mail/Mot de passe → Activer**.
3. **Firestore Database → Créer une base** (mode production, région europe-west).
4. Firestore → onglet **Règles** → remplacer tout par le contenu de `firestore.rules` → **Publier**.
5. ⚙️ **Paramètres du projet → Vos applications → icône Web `</>`** → enregistrer l'appli → copier le bloc `firebaseConfig`.
6. (Déjà fait : la configuration Firebase est intégrée dans `index.html`.)

## 2. Render
1. Créer un dépôt GitHub (ex. `recouvrement-tmf`) et y déposer **tous les fichiers** de ce dossier.
2. Render → **New → Static Site** → choisir le dépôt.
   - Build Command : *(vide)*
   - Publish Directory : `.`
3. Ou, sur votre service existant : remplacer les fichiers du dépôt actuel par ceux-ci → Render redéploie tout seul.

## 3. Premier accès
- Ouvrir l'application → saisir **wassim.khalfalli@tmf.com.tn** + un mot de passe → **Créer un compte**.
  Vous êtes automatiquement **administrateur**.
- Mot de passe oublié : bouton **Mot de passe oublié** (e-mail envoyé par Firebase).
- Changer le mot de passe : onglet **Mon compte**.
- Collègues : ils créent leur compte avec leur adresse **@tmf.com.tn** (rôle utilisateur : ajout, relances, consultation ; pas de modification ni suppression).
- Ajouter un autre administrateur : ajouter son e-mail dans `ADMINS` (index.html) **et** dans `firestore.rules`.

Les données (clients, factures, relances) sont enregistrées dans Firebase : elles restent après déconnexion et sont partagées entre tous les utilisateurs.
