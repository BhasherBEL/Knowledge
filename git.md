# Git

---

## git init

**`git init`** permet d'initialiser le projet. Il doit être effectué à la racine du projet.

Arguments:

- `--bare` permet de ne pas utiliser le sous-fichier `.git` et d'avoir les informations directement à la racine du projet.

---

## git config

**`git config [...] <command> "<string>"`** permet de configurer un projet. 

Arguments:

- `--global` permet de changer les valeurs de configuration par défaut.
- `--list` permet le lister la configuration actuelle.

Sous-commandes:

- `git config user.email "paul@gmail.com"` permet de définir notre email dans le projet.
- `git config user.name "paul"` permet de définir notre nom dans le projet. Ces deux fonctions permettent de différencier les différentes personnes ayant modifié un projet.
- `git config color.ui true` permet de rajouter des couleurs dans l'invite de commande git.
- `git config branch.autosetuprebase always` permet de toujours utiliser `--rebase` lors d'un `pull` (recommandé).

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

**`git commit [...]`** permet de valider vos modifications sous la forme d'une *snapshot*. Celui ci doit être accompagné d'un message. 

Arguments:

- `-m <message>` permet de spécifier le message. Si l'argument n'est pas présent, un éditeur s'affiche dans lequel le message peut être inscrit.
- `-a` permet de commit tous les fichiers trackés ayant été modifié.
- `--ammend` permet de rajouter les modifications au dernier commit.

---

## git log

**`git log [...]`** permet d'afficher les commits ayant déjà eu lieu.

Arguments:

- `-n <amount>` permet de ne voir que les *`amount`* derniers commits.
- `--oneline` permet d'afficher un commit par ligne.

---

## git diff

**`git diff`** permet de voir les modifications depuis le dernier commit.

---

## git checkout

**`git checkout <commit id|branch name> [...]`** permet de se déplacé vers le commit ou la branche spécifiée.

Arguments:

- `[files]` permet de préciser les fichiers. (Uniquement pour le 1er usage)

---

## git revert

**`git revert <id>`**  permet d'annuler un commit en particulier. Les modifications effectuées par les commits antérieurs et postérieurs sont conservés.

---

## git reset

**`git reset [...]`** permet de revenir en arrière sur différentes choses. Par défaut, la commande vide la liste des fichiers trackés.

Sous commandes:

- `git reset HEAD <file>...` permet de ne plus tracker un ou plusieurs fichier spécifique.
- `git reset --hard` permet de revenir au précédent commit. ⚠ irréversible ⚠
- `git reset <id>` supprime tous les commits postérieurs au commit `id`. Les fichiers modifiés sont mis dans le stage et sont prêt à être commit. ⚠ irréversible ⚠
- `git reset <id> --hard` Permet de revenir au commit `id` et supprime tous les commits postérieurs. ⚠ irréversible ⚠

---

## git branch

**`git branch [...] <name>`** permet de créer la branche *`name`*.

Arguments:

- `-d` permet de supprimer la branche cible.

---

## git merge

**`git merge [...] <name>`** permet de ramener la branche `name` sur la branche courante.

Arguments:

- '--no-ff' permet d'empecher le *fast-forward* (qui rapatrie automatiquement les modifications de la branche si aucune modification n'a eu lieu sur la branche *master*)

---

## git rebase

**`git rebase [...] <branch name>`** déplace tous les commits de la branche courante vers la branche *`name`*. Autrement, on force un *fast-forward*.

Arguments:

- `id` permet de faire un *rebase* interactif.
- `--continue` permet de continuer en cas d'erreur.

Sous commandes:

- `git rebase~~` permet de fusionner les *n* derniers commits où *n* est le nombre de *~* présent.

---

## git stash

**`git stash`** permet de mettre de coté nos modifications depuis le dernier commit.

Arguments:

- `-u` permet de *stasher* aussi les fichiers non trackés.

Sous commandes:

- `git stash apply` permet de réappliquer les modifications mises de coté.
- `git stash list` permet de voir la liste des *stashs*.
- `git stash drop` permet de supprimer le dernier *stash*.
- `git stash pop` combine `apply` et `drop`.
- `git stash branch <branch name>` transforme le *stash* en branche.

---

## git remote

**`git remote [...]`** permet de  gérer les dépôts distants.

Sous commandes:

- `git remote -v` liste les dépôts distants.
- `git remote rename <old nom> <new name>` permet de renommer le dépôt distant. 
- `git remote remove <name>` permet de supprimer la branche distante.

---

## git push

**`git push <distant branch> <local branch>`** permet d'envoyer les modifications.

---

## git pull

**`git pull <distant branch> <local branch>`** permet de mettre à jour la branche locale.

Arguments:

- `--rebase` permet de considérer les commits distants comme faisant parti du commit local.

---

## git clone

**`git clone <distant branch> [local folder]`** permet de cloner un dépôt distant.

Arguments:

- `--depth <prof>` permet de définir la profondeur de récupération. (le nombre d'anciens commits)

