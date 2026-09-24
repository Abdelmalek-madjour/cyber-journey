---------------------------Terminal-----------------------------

| Commande | Effet | Piège |
|---|---|---|
| `pwd` | où je suis | à faire avant tout `rm -rf` |
| `ls -a` | liste, fichiers cachés inclus | sans `-a`, on ne voit pas `.git` |
| `cd ..` | remonte d'un dossier | |
| `cat fichier` | affiche le contenu du fichier | sur le DISQUE, pas dans le commit |
| `nano fichier` | éditer | `Ctrl+X` puis `O` puis Entrée |

------------------------------Git--------------------------------

| Commande | Effet | Piège |
|---|---|---|
| `git init` | crée le dépôt (dossier `.git`) | |
| `git status` | état des 3 zones | à taper à chaque début de session |
| `git add f` | **copie** f vers la staging | copie, ne marque pas. Remodifier après = refaire `add` |
| `git commit -m "..."` | photographie la staging | ne regarde JAMAIS le disque |
| `git log --oneline` | l'historique | |
| `git show HEAD:f` | contenu de f dans le commit | |
| `git show :f` | contenu de f dans la staging | |

---------------------- Pièges shell rencontrés ------------------

- `#` dans zsh interactif n'est pas un commentaire → `too many arguments`
- backtick ouvert → prompt `bquote>` → `Ctrl+C`
- guillemet courbe `"` ≠ guillemet droit `"` → prompt `dquote>`
- `\` au lieu de `/` dans un chem
