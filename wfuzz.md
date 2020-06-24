# Wfuzz

---

## Help

```bash
wfuzz [argument] <url>
```

- documentation: https://wfuzz.readthedocs.io/en/latest/user/basicusage.html.

### Arguments

- `-c` : Sortie colorée.
- `--hc <code>`: Filtre sur le code de la réponse (rejete le code). Exemple: `--hc 404`.
- `--hs <text>`: Rejete si le texte mentionné est présent.
- `--ss <text>`: N'accepte que si le texte mentionné est présent.
- `-z <type>,<content>`: Données à injecter. types possibles:
  - `file` : *content* est un fichier contenant la liste des mots à tester.
  - `list`: *content* est la liste des mots à tester, séparés par des `-`.
- `-r<n>`: Recherche récursive de profondeur `n`.
- `-H "<name>: <value>"`: Défini un header custom.

## Recursion (trouver des répertoires non linkés)

### Recherche de base

```bash
wfuzz -c -z file,/usr/share/wfuzz/wordlist/general/common.txt --hc 404 https://exemple.com/FUZZ
```

### Recherche récursive (de niveau 1)

```bash
wfuzz -c -z file,/usr/share/wfuzz/wordlist/general/common.txt --hc 404 -R1 https://exemple.com/FUZZ
```

### Recherche dans certains sous domaines

```bash
wfuzz -c -z file,/usr/share/wfuzz/wordlist/general/common.txt -z list,js-css-assets --hc 404 https://exemple.com/FUZ2Z/FUZZ
```

