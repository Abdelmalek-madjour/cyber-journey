## En une phrase :
>une cle-ssh est une paire : une cle privée qui est propre a mon ordinateur qui permet de signer et reste privée .et une cle public que on vas voir publiquement , ca vas nous permettre de nous connecter, et permet de verifier la signature de la privée 

## A quoi ca sert concrètement :
dans mon cas ca permet de connecter mon terminal a github et qui vas me permettre de faire mes push,pull,clonne tranquillement ,


## Comment ca marche (mecanisme):
pour me connecter mon mac utilise la cle public apres github la reconnais et ensuite mon mac signe la connexion avec la cle privée (mais il la montre pas ) en suite GitHub vérifie la signature avec la clé publique


## Exemple reel :

>« la publique c’est une photocopie de l’original, exemple quand tu fais des procédures administratives à chaque fois j’envoie une copie pas l’original, je dois jamais donner l’original (la privée)
>
>la privée pour ordonée la connexion a github donc meme,si quelqu'un possed la cle public peu pas ce connecter
	
	abdel@MacBook-Air-de-abdelmalek vault % ssh -vT git@github.com 2>&1 | grep -E "Offering|accepts|Hi " 
	
	debug1: Offering public key: /Users/abdel/.ssh/id_ed25519 ED25519 SHA256:MUkDngwcAcDJ3X35rU2D8a8Mj5PXmqBtQxqSkExMpfI agent
	
	debug1: Server accepts key: /Users/abdel/.ssh/id_ed25519 ED25519 SHA256:MUkDngwcAcDJ3X35rU2D8a8Mj5PXmqBtQxqSkExMpfI agent
	
	Hi Abdelmalek-madjour! You've successfully authenticated, but GitHub does not provide shell access. 


## Ce que je n'ai pas encore compris:

- ~~la privée signe mais la public qui aparait ??:~~:
	oui la public aparait partout et la privée reste cacher la public on la vois dans les fichier .pub ,dans les reglag GITHUB 

- Comment on protège la clé privée si quelqu'un vole mon Mac ?
## Liens:

[[known-hosts]]
[[git-vs-github]]
Source : session de formation du 06/11 + ma sortie ssh -vT


