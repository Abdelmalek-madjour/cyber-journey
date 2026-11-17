## En une phrase (mes mots):
> known-hosts: c'est le fichier qui enregistre les clés publiques des serveurs, à la première connexion, quand tu tapes yes , pour les prochaine connexion il compare si la cle est deja dans le fichier il se connect sans rien demander sinon il bloque tous 

## A quoi ca sert concretement

a verifier si la cle la deja autoriser ou pas 

## Comment ca marche (mecanisme)

serveur JAMAIS vu               →  demande si il peu lui faire confiance  par yes or no 
serveur connu + MÊME clé        → lui fait confiance directement 
serveur connu + clé DIFFÉRENTE  → affiche un message d'alerte  et bloque la connexion 

## Exemple reel:
>en 2023 github on leek leur cle privée dans un depot public daonc il on due changer leur cle urgament donc pour les utilisateur qui ce son connecter apres ca leur as bloquer l'accée donc il on du reverifier la cle avant de lui faire confiance  . donc c'est grace a Known-host que ca bloquer l'accée par securite

	abdel@MacBook-Air-de-abdelmalek vault % ssh-keygen -F github.com`
	`Host github.com found: line 1` 
		`github.com ssh-
	ed25519AAAAC3NzaC1lZDI1NTE5AAAAIOMqqnkVzrm0SdG6UOoqKLsabgH5C9okWi0dh2l9GKJl`
	`Host github.com found: line 2` 
		`github.com ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABgQCj7ndNxQowgcQnjshcLrqPEiiphnt+VTTvDP6mHBL9j1aNUkY4Ue1gvwnGLVlOhGeYrnZaMgRK6+PKCUXaDbC7qtbW8gIkhL7aGCsOr/C56SJMy/BCZfxd1nWzAOxSDPgVsmerOBYfNqltV9/hWCqBywINIR+5dIg6JTJ72pcEpEjcYgXkE2YEFXV1JHnsKgbLWNlhScqb2UmyRkQyytRLtL+38TGxkxCflmO+5Z8CSSNY7GidjMIZ7Q4zMjA2n1nGrlTDkzwDCsw+wqFPGQA179cnfGWOWRVruj16z6XyvxvjJwbz0wQZ75XK5tKSb7FNyeIEs4TT4jk+S4dhPeAUC5y+bDYirYgM4GC7uEnztnZyaVWQ7B381AK4Qdrwt51ZqExKbQpTUNn+EjqoTwvqNj4kqx5QUCI0ThS/YkOxJCXmPUWZbhjpCg56i+2aB6CmK2JGhn57K5mj0MNdBXA4/WnwH6XoPWJzK5Nyu2zB3nAZp+S5hpQs+p1vN1/wsjk=`
	`Host github.com found: line 3` 
	`github.com ecdsa-sha2-nistp256 AAAAE2VjZHNhLXNoYTItbmlzdHAyNTYAAAAIbmlzdHAyNTYAAABBBEmKSENjQEezOmxkZMy7opKgwFB9nkt5YRrYMjNuG5N87uRgg6CLrbo5wAdT/y6v0mKV0U2w0WZ2YB/++Tpockg=`

## Ce que je n'ai pas encore compris
- ~~pourquoi il la redamnde pas l'autorisation a chaque fois c'est pas plus securisée ??~~
	vu que la cle est longue ca vas faire trop de relir a chauqe fois et avec l'habitude l'etre humain vas juste mettre yes directement a la connexion alors que known-hosts vas verifier a chauque fois au charactere donc moi de risque 

- où trouver les empreintes officielles de GitHub pour vérifier ?
## Liens
[[cle-ssh]]
[[man-in-the-middle]]
Source : (GitHub's SSH key fingerprints — https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/githubs-ssh-key-fingerprints + ma sortie ssh-keygen -F github.com