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

---
 **Note** : Pensez à configurer un fichier `.gitignore` dès le début du projet pour éviter de suivre les fichiers sensibles ou inutiles (`.env`, `node_modules/`, etc.).





