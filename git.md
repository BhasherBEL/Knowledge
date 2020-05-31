# Git

---

## git init

**`git init`** permet d'initialiser le projet. Il doit être effectué à la racine du projet.

---

## git config

**`git config [args] <command> "<string>"`** permet de configurer un projet. 

Arguments:

- `--global` permet de changer les valeurs de configuration par défaut.
- `--list` permet le lister la configuration actuelle.

Sous-commandes:

- `git config user.email "paul@gmail.com"` permet de définir notre email dans le projet.
- `git config user.name "paul"` permet de définir notre nom dans le projet. Ces deux fonctions permettent de différencier les différentes personnes ayant modifié un projet.
- `git config color.ui true` permet de rajouter des couleurs dans l'invite de commande git.

---

## git status

**`git status`** permet de connaitre l'état du projet.

---

## git add

**`git add <file>...`** permet de tracker un nouveau fichier.