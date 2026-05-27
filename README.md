Cette Page regroupe des details pour un projet en Vue d'apprendre Git , une sorte de CTF du developeur pour la formation 48


##  Outils Utilisés
* **Git** (Log, Reflog, Fsck)
* **TruffleHog / GitLeaks** *(Optionnel)*
* **CyberChef** *(Optionnel)*

## Résolution (Step-by-Step)

### Étape 1 : Analyse initiale
J'ai commencé par cloner le dépôt et inspecter l'historique standard des commits :
```bash
git clone <url_du_depot>
cd <nom_du_depot>
git log --oneline
```
*Constat* : L'historique visible semblait propre, mais un message de commit mentionnait la suppression de fichiers temporaires.

### Étape 2 : Exploration de l'historique caché
Pour retrouver les traces des commits supprimés ou modifiés, j'ai utilisé le journal de référence de Git :
```bash
git reflog
```
Cette commande a révélé un commit orphelin nommé `HEAD@{3}` avec le message *"Oops, credentials exposed"*.

### Étape 3 : Extraction du Flag
En inspectant le contenu de ce commit spécifique, le drapeau est apparu :
```bash
git show HEAD@{3}
```

## Flag
```text
FLAG{G1t_N3v3r_F0rg3ts_S3cr3ts}
```

## Leçons apprises
* **Git n'oublie rien** : Supprimer un fichier ou écraser un commit ne supprime pas instantanément les données de la base Git.
* **Bonne pratique** : Toujours utiliser un fichier `.gitignore` avant le premier commit et faire tourner un outil comme *GitLeaks* en CI/CD.

