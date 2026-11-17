## En une phrase (mes mots):
> git est un logiciel qui tourne dans ton pc qui vas garder tous les historique et Github est un site internet dans le qu'elle on peu publier nos depots git et parcourir d'autre depots. Git marche **sans** GitHub, mais GitHub ne sert à rien sans Git.

## A quoi ca sert concretement:
>git permet de sauvgarder toute les version d'un depot et permet de revenir en arriere en cas de casse et github est une vitrine pour mes depot 
## Comment ca marche (mecanisme):

>Git ca sert stocker les historique de mes commit dans  (les snapshot).git et apres une fois que je fait un git push ca vas envoyer les commit a github via SSH

## Exemple reel:
.git et .gitignore.      utilise le git fans .git y son stocker tous les ancien commit 
et la suite c ma clef public ^

```
abdel@MacBook-Air-de-abdelmalek vault % cd ~/dev/cyber-journey
ls -a
git remote -v
. .. .git .gitignore README.md cheatsheet.md journal.md
origin git@github.com:Abdelmalek-madjour/cyber-journey.git (fetch)
origin git@github.com:Abdelmalek-madjour/cyber-journey.git (push)
```

## Ce que je n'ai pas encore compris
- git en profondeur c'est un logiciel qui vas s'intergrer  a notre tableau de cmd ?

Git, c’est comme mon appareil photo : chaque commit est une photo que je garde chez moi. GitHub, c’est comme Instagram ou tu peu poster les photos et voir d'autre photos 

## Liens
[[cle-ssh]]
[[modele-3-zones-git]]

Source : Pro Git, chapitre 1.1 « About Version Control » — git-scm.com/book