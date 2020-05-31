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

**`git status`** permet de connaitre l'état du projet. Il fait la distinction entre trois types de fichiers:

- Les fichiers prêts être *commit*
- Les fichiers qui ont été modifiés
- Les fichiers non trackés

---

## git add

**`git add <file>...`** permet de tracker un ou plusieurs nouveaux fichiers. Les regex peuvent être utilisées.

---

## git commit

**`git commit [args]`** permet de valider vos modifications sous la forme d'une *snapshot*. Celui ci doit être accompagné d'un message. 

Arguments:

- `-m <message>` permet de spécifier le message. Si l'argument n'est pas présent, un éditeur s'affiche dans lequel le message peut être inscrit.
- `-a` permet de commit tous les fichiers trackés ayant été modifié.