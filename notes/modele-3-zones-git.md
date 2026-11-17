## En une phrase (mes mots):
> les Zone son [1]Disque , [2]stagning et [3]depot et les 3 son stocker dans notre machine  pour passer de la zone 1 a 2 on doit utiliser ` git add `et pour passer de la 2 a 3 on utilise `git commit `  mais une fois que on fait un `git push `pour que ca ce transmet a github

## A quoi ca sert concretement:
>le stagning : tu peu mettre en plusieur commit different avec diifferent message donc meilleur trace de l'avancement donc a cause de ca tu peu choisir ce que tu veux commit c une fois c fait `git push `te permet de poster sur github

## Comment ca marche (mecanisme):
>comment ca marche : une fois fichier volue modier -> `git add fichier.txt` -> ca vas copier le fichier dans stagning -> `git commit -m "message" ` -> vas permetre de copier le fichier dans le depot donc j'ai plus que as le `git push` pour l'envoyer sur le github

## Exemple reel:
>prenons exemple je veux poster des photos sur intagram, une fois que j'ai pris des photo et je l'ai est modifier (donc ils sont dans le disque) donc je choisi les photo que je veux poster (dans le stagning) une fois je prepare le poste et je choisi les #(il sont dans le depot) et une fois poster(ca veux dire que je l'ai push dans le github)

` abdel@MacBook-Air-de-abdelmalek cyber-journey % git status`
`Sur la branche main`
`Votre branche est à jour avec 'origin/main'.`
  `Modifications qui seront validées :`
  `(utilisez "git restore --staged <fichier>..." pour désindexer)`
`modifié :         journal.md`
`Modifications qui ne seront pas validées :`
  `(utilisez "git add <fichier>..." pour mettre à jour ce qui sera validé)`
  `(utilisez "git restore <fichier>..." pour annuler les modifications dans le répertoire de travail)`
`modifié :         cheatsheet.md ``

## Ce que je n'ai pas encore compris
- dans notre machine les 3 zones son stocker dans qu'elle fichier ??
- 

## Liens
[[git-vs-github]]
[[commits-atomiques]]
Source : Pro Git, chap. 1.3 « What is Git? » — git-scm.com/book
