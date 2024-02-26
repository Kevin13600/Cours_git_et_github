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
$ git checkout main <<>> Fusionner la branche necessite de ce repositionner sur la branche principal.
$ git merge cagnotte


/* Cloner un projet sur la machine locale */

<<>> Cliquer sur code pour obtenir l'URL
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

/* en cas d'erreur sur une modification de la branche principale */

- Effectuer une remise :

$ git status
$ git stash
$ git branch NouvelleBranch
$ Git checkout Nouvellebranch
$ git stash apply stash@{..}

/* en cas d'erreur avec en plus un commit */

$ git log <== Récuperer l'ID 
$ git log commit
git reset --hard HEAD^

/* modifier message d'un commit */

$ git commit --amend -m "Votre nouveau message de commit"

/* j'ai oublier un fichier dans mon dernier commit */

$ git add FichierOublie.txt
¤ git commit --amend --no-edit

/* annuler un push */

$ git revert HEAD^ <== sert à annuler des changements commités
$ git reset HEAD <== permet d'annuler des changements non commités.

/* les 3 types de réinitialisation de Git */

$ git reset notreCommitCible --hard <== Cette commande permet de revenir à n'importe quel commit mais en oubliant absolument tout ce qu'il s'est passé après.
$ git reset notreCommitCible --mixed <== va permettre de revenir juste après votre dernier commit ou le commit spécifié, sans supprimer vos modifications en cours.

- Si rien n'est spécifié après $ git reset , par défaut il exécutera un $ git reset --mixed HEAD~

$ git reset notreCommitCible --soft <== permet de se placer sur un commit spécifique afin de voir le code à un instant donné, ou de créer une branche partant d'un ancien commit.

/* Corrigez un commit raté */

- les techniques de journalisation de Git ont été prévues pour répondre à ce genre de situation. 

$ git reflog <== permet de consulter l'historique de votre projet
$ git checkout [ref] <== permet de revenir a un ancien commit

/* Savoir qui est l'auteur des modifications */

$ git blame [file] <== permet d’examiner le contenu d’un fichier ligne par ligne et de déterminer la date à laquelle chaque ligne a été modifiée, et le nom de l’auteur des modifications.
