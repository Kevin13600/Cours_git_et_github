/* Configuration Git */

$ git config --global user.name "Prenom Nom"
$ git config --global user.email adress@email.com
$ git config --global color.diff auto
$ git config --global color.status auto
$ git config --global color.branch auto
$ git config --global core.editor vim
$ git config --global merge.tool vimdiff


/* Travaillez depuis votre dépôt local Git */

- Crée au préalable un repository sur Github.
- Se positionner dans son dossier de travail.
- Créer les fichier de travail (index.html, styles.css).
- initialiser un nouveau dépôt Git dans le répertoire.

$ git init
Initialized empty Git repository in C:/../..

/* Indexez vos fichiers avec la commande git add */

$ git add index.html styles.css
$ git status <=== afficher l'état actuel du dépôt Git.

/* Créez une nouvelle version avec la commande git commit */

git commit -m “Ajout des fichiers html et css de base” <=== L'argument -m correspond a "message"


/* Création d'un clé SSH */

$ ssh-keygen -t ed25519 -C "email@adress.com" <==  Ed25519 est un algorithme de cryptographie asymétrique moderne qui offre de bonnes performances et une sécurité élevée. 
$ clip < ~/.ssh/id_github_ed25519.pub <== Copier la clé et l'inserer dans Github.

/* Lier le dépôt local au dépôt distant */

$ git remote add origin https://github.com/utilisateur/nom-du-repo.git

/* renomer la branche master en main */

$ git branch -M main

/* pousser vos modifications locales depuis la branche "main" (ou toute autre branche spécifiée) vers la branche correspondante sur le référentiel distant nommé "origin". /*

$ git push -u origin main <== -u configure la branche locale pour suivre la branche distante spécifiée.
$ git add index.html 
$ git commit -m "Modification du titre H1"

/* Effectuer un renomage du repository */

$ git remote set-url origin https://github.com/nouveau-nom-utilisateur/nouveau-nom-repo.git

/* Créer une branche, la pousser et la fusionner avec la branche main */

$ git branch <== Permet d'afficher la liste des branche.
$ git branch cagnotte <== Permet de créer la branche cagnotte.
$ git checkout cagnotte <== checkout permet de de switcher de branche.
$ touch cagnotte.txt
$ git add cagnotte.txt
$ git commit -m "Réalisation de la partie cagnotte côté front end"
$ git push -u origin cagnotte
 update-readme1
$ git checkout main <== Fusionner la branche necessite de ce repositionner sur la branche principal.
$ git merge cagnotte


/* Cloner un projet sur la machine locale */

 Cliquer sur code pour obtenir l'URL
$ git clone https://github.com/user/example_repo.git 

/* Mettre a jour un dépôt local */

 $ git pull origin main <== Cela mettra à jour votre branche locale main avec les dernières modifications de la branche main du dépôt distant origin.


/* Pull request */

- Créer une branche : Créez une nouvelle branche locale où vous ferez les modifications pour votre pull request.

$ git checkout -b nom_de_votre_branche

- Effectuer les modifications : Faites les modifications nécessaires dans votre branche locale.
- Commit des modifications : Une fois les modifications terminées, ajoutez et committez vos changements.

$ git add "document"
$ git commit -m "Description des modifications"
$ git push origin nom_de_votre_branche

- valider sur github dans pull request

/* en cas d'erreur */

$ git checkout main
$ git merge cagnotte





