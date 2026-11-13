## terminal

| Commande | Effet | Piège |
|---|---|---|
| `pwd` | où je suis | à faire avant tout `rm -rf` |
| `ls -a` | liste, fichiers cachés inclus | sans `-a`, on ne voit pas `.git` |
| `cd ..` | remonte d'un dossier | |
| `cat fichier` | affiche le contenu du fichier | sur le DISQUE, pas dans le commit |
| `nano fichier` | éditer | `Ctrl+X` puis `O` puis Entrée |
| `mkdir -p` | crée un dossier | `-p` crée aussi tous les dossiers parents manquants |
| `rm -rf` | supprime définitivement | `-r` récursif, `-f` sans confirmation. Pas de corbeille. `pwd` avant, toujours |
| `mv` | déplace ou renomme | `mv ancien.md nouveau.md` | 
| `history 1 | grep "mot"` | retrouver une commande déja tapée ||
| `tail -20 fichier`|afficher les 20 dernieres lignes d'un fichier ||


## git

| Commande | Effet | Piège |
|---|---|---|
| `git init` | crée le dépôt (dossier `.git`) | |
| `git status` | état des 3 zones | à taper à chaque début de session |
| `git add f` | **copie** f vers la staging | copie, ne marque pas. Remodifier après = refaire `add` |
| `git commit -m "..."` | photographie la staging | ne regarde JAMAIS le disque |
| `git log --oneline` | l'historique | |
| `git show HEAD:f` | contenu de f dans le commit | |
| `git show :f` | contenu de f dans la staging | |
| `git remote -v` | affiche l'adresse du depot d'orgine ||
| `git config user.email `| affiche l'email qui signe mes commit ||
| `git log -1 --format="%an <%ae>" `| nom + e-mail de l'auteur du DERNIER commit ||

### SSH

| commande | Effet |
| `ssh -vT git@github.com` | teste ma connexion SSH a github,etape par tape (-v =bavard ) |
| `ssh-keygen -F github.com` | cherche github.com dans known_hosts et affiche ses clés publiques |


`git  @  github.com  :  Abdelmalek-madjour  /  cyber-journey.git`
 `│           │                │                      │`
 `│       le serveur        ton compte             le dépôt`
 `│     (l'immeuble)     (l'appartement)          (la boîte)`
 `│`
 `utilisateur SSH : « git », le MÊME pour tout le monde sur GitHub`


- `abdel@MacBook-Air-de-abdelmalek cyber-journey % git config user.email` 
	`git log -1 --format="%an <%ae>"`
	`323791980+Abdelmalek-madjour@users.noreply.github.com`
	`Madjour Abdelmalek <==🔵323791980==+==🔴Abdelmalek-madjour@users.noreply.github.com==>`

### Préfixes de commit (Conventional Commits)

| Préfixe | Sens | Quand | Exemple |
|---|---|---|---|
| `feat:` | feature | le projet sait faire un truc nouveau | `feat: ajoute le scan de ports TCP` |
| `fix:` | correction | un comportement cassé ne l'est plus | `fix: corrige le crash si le fichier est absent` |
| `docs:` | documentation | README, notes, rien d'exécutable | `docs: complete le README` |
| `chore:` | corvée | config, outillage, plomberie | `chore: ajoute le .gitignore` |
| `refactor:` | réécriture | le code change, le comportement non | `refactor: extrait le parsing` |
| `test:` | tests | ajout ou correction de tests | `test: couvre les ports fermés` |
| `style:` | forme | indentation, espaces, zéro logique | `style: reformate selon PEP 8` |
| `perf:` | performance | pareil mais plus rapide | `perf: remplace la boucle` |
| `build:` | build | dépendances, packaging | `build: passe requests en 2.31` |
| `ci:` | intégration continue | pipelines, GitHub Actions | `ci: ajoute le lint sur chaque push` |
| `revert:` | annulation | annule un commit précédent | `revert: annule feat: scan UDP` |
| `notes:` | notes | hors standard, pour un dépôt d'apprentissage | `notes: fiche sur les permissions Linux` |

### Syntaxe

`type: description à l'impératif, minuscule, sans point final`

- pas d'espace avant les `:` — `chore:` et non `chore :`
- impératif présent : « ajoute », pas « ajouté » ni « ajout de »
- minuscule après les `:`
- pas de point final

Logique de l'impératif : le message complète « Ce commit va… ».

### Confusions à éviter

| Cas | Préfixe | Pourquoi |
|---|---|---|
| renommer un fichier | `chore:` | ni feature ni bug |
| corriger une faute dans le README | `docs:` | c'est de la doc |
| corriger une faute affichée à l'écran | `fix:` | l'utilisateur voit la différence |
| réorganiser sans changer le comportement | `refactor:` | rien n'était cassé |
| reformater sans toucher la logique | `style:` | même structure |

Test `fix` vs `refactor` : est-ce qu'un utilisateur voit la différence ?
Oui → `fix`. Non → `refactor`.

### Options

- scope : `feat(scanner): ajoute le support UDP`
- breaking change : `feat!: change le format de sortie en JSON`

Spec officielle FR : https://www.conventionalcommits.org/fr/

## Pièges rencontrés

- `#` dans zsh interactif n'est pas un commentaire → `too many arguments`
- backtick ouvert → prompt `bquote>` → `Ctrl+C`
- guillemet courbe `"` ≠ guillemet droit `"` → prompt `dquote>`
- `\` au lieu de `/` dans un chemin


