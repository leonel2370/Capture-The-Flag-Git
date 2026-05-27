Cette Page regroupe des details pour un projet en Vue d'apprendre Git , une sorte de CTF du developeur pour la formation 48


#  Guide de Survie Git : Les Commandes de Base

Ce guide regroupe de manière structurée les commandes Git fondamentales indispensables pour gérer et collaborer sur un projet.

---

## 1. Initialisation & Configuration

Préparer l'environnement de travail et l'identité de l'auteur.

*   `git init` — Initialise un nouveau dépôt Git local dans le dossier courant.
*   `git clone <url>` — Copie un dépôt distant existant sur la machine.
*   `git config --global user.name "Nom"` — Définit le nom de l'auteur des commits.
*   `git config --global user.email "email"` — Définit l'adresse email de l'auteur.

## 2. Suivi des Modifications

Gérer l'état des fichiers et préparer les changements.

*   `git status` — Liste les fichiers modifiés, supprimés ou non suivis.
*   `git add <fichier>` — Ajoute un fichier spécifique à la zone de préparation (*Staging Area*).
*   `git add .` — Ajoute l'ensemble des modifications à la zone de préparation.
*   `git diff` — Visualise les changements précis non encore indexés.

## 3. Enregistrement & Historique

Sauvegarder l'état du projet et consulter son évolution.

*   `git commit -m "Message"` — Enregistre les modifications indexées dans l'historique local.
*   `git commit --amend` — Modifie le message ou le contenu du tout dernier commit.
*   `git log` — Affiche l'historique complet et chronologique des commits.
*   `git log --oneline` — Condense l'affichage de l'historique (un commit par ligne).

##  4. Branches & Fusions

Isoler le développement de nouvelles fonctionnalités.

*   `git branch` — Liste les branches locales du projet.
*   `git branch <nom>` — Crée une nouvelle branche à partir de la position actuelle.
*   `git switch <nom>` — Bascule sur la branche spécifiée pour y travailler.
*   `git merge <nom>` — Fusionne l'historique de la branche spécifiée dans la branche active.
*   `git branch -d <nom>` — Supprime la branche locale spécifiée (si fusionnée).

##  5. Synchronisation & Collaboration

Partager et récupérer le code avec un serveur distant (GitHub, GitLab...).

*   `git remote add origin <url>` — Lie le dépôt local à un serveur distant principal.
*   `git fetch` — Récupère les données du serveur distant sans modifier le code local.
*   `git pull` — Télécharge et fusionne directement les nouveautés distantes.
*   `git push origin <branche>` — Envoie les commits locaux vers le serveur distant.

##  6. Gestion des Erreurs & Annulations

Corriger les fautes de frappe ou revenir en arrière en toute sécurité.

*   `git checkout -- <fichier>` — Annule les modifications non enregistrées d'un fichier.
*   `git reset HEAD <fichier>` — Retire un fichier de la zone de préparation sans perdre le code.
*   `git reset --soft HEAD~1` — Annule le dernier commit mais conserve les modifications dans le code.
*   `git reset --hard HEAD~1` — Efface définitivement le dernier commit et supprime toutes ses modifications.

##  7. Résolution des Conflits de Fusion

Un conflit survient lorsque Git ne sait pas quelle version du code choisir lors d'un `git merge` ou d'un `git pull`.

### Processus de résolution :
1.  **Identifier** : Git bloque la fusion et marque les fichiers en conflit. Tapez `git status` pour les lister.
2.  **Ouvrir** : Ouvrez les fichiers concernés. Git insère des balises visuelles :
    ```text
    <<<<<<< HEAD
    Mon code local actuel (Option A)
    =======
    Le code distant ou de l'autre branche (Option B)
    >>>>>>> branche-conflit
    ```
3.  **Choisir** : Supprimez les balises et gardez uniquement le code final souhaité.
4.  **Enregistrer** : Finalisez la fusion avec les commandes suivantes :
    ```bash
    git add <fichier-conflit>
    git commit -m "Fix: résolution du conflit de fusion"
    ```

##  8. Bonnes Pratiques : Écrire de Bons Messages (Conventional Commits)

Adopter un standard d'écriture permet de rendre l'historique du projet lisible par n'importe quel développeur et d'automatiser la création de rapports de version (Changelog).

### Structure d'un commit :
```text
<type>(<portée_optionnelle>): <description courte au présent>
```

### Principaux types à utiliser :
*   `feat`: Ajout d'une nouvelle fonctionnalité (ex: `feat(auth): ajout de la connexion Google`).
*   `fix`: Correction d'un bug (ex: `fix(nav): correction du menu qui ne s'ouvre pas`).
*   `docs`: Modification de la documentation ou du README (ex: `docs: mise à jour du guide de démarrage`).
*   `style`: Changement cosmétique qui n'affecte pas le code (espaces, mise en page, point-virgule).
*   `refactor`: Modification du code qui n'ajoute pas de fonction ni ne répare de bug.
*   `test`: Ajout ou correction de tests unitaires.



---
 **Note** : Pensez à configurer un fichier `.gitignore` dès le début du projet pour éviter de suivre les fichiers sensibles ou inutiles (`.env`, `node_modules/`, etc.).





