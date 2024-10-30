# TP1DevOps
Partie 1 : Préparation de l'environnement Git
4. Comment vérifier la configuration actuelle de Git sur votre machine, notamment le nom
d’utilisateur et l’adresse e-mail ?

→ git config --list

5. Comment modifier votre adresse e-mail si vous l'avez mal configurée lors de l'installation
de Git ?

→ git config --global user.email "nouvelle-adresse@example.com" 
→ git config user.email "nouvelle-adresse@example.com" 

Partie 2: Création d'un nouveau projet
6. Si vous avez oublié de créer un fichier README.md lors de l'initialisation du projet,
comment pouvez-vous l'ajouter après coup et commiter les changements ?
touch README.md
git add README.md
git commit -m "Ajout du fichier README.md"
git push origin main
7. Comment définir un dépôt distant si vous n'en avez pas configuré un lors de la créa�on
du projet ?
Ajouter l’URL du dépôt distant :
git remote add origin [URL-du-dépôt]
Pousser les commits vers le dépôt distant
git push -u origin main
Partie 3 : Concepts de base de Git
3. Comment annuler les modifica�ons locales d'un fichier avant de les ajouter à l'index ?
Revenir aux changements du dernier commit pour un fichier spécifique :
git checkout – nom_du_fichier
. Visualiser les fichiers prêts à être commités dans Git (staging)
Voir les fichiers en staging (prêts à être commités) :
git status
4. Comment visualiser les fichiers qui sont prêts à être commités dans Git (staging) ?
Ajouter un dépôt distant et récupérer toutes les branches : Si le dépôt distant est déjà
configuré, vous pouvez récupérer toutes les branches avec cette commande :
 git fetch –all
Cela télécharge toutes les branches sans les fusionner dans les branches locales.

 Suivre une branche spécifique : Si vous voulez suivre une branche spécifique (par exemple,
feature-branch), vous pouvez utiliser :
git checkout --track origin/feature-branch
Cela crée une branche locale qui suit origin/feature-branch.
5. Supprimer une branche locale après l'avoir fusionnée dans main
 Supprimer la branche locale : Après avoir fusionné la branche dans main et vérifié que tout est
en ordre, vous pouvez la supprimer localement avec cette commande :
git branch -d nom-de-la-branche
Si la branche n’a pas encore été fusionnée et que vous souhaitez la supprimer de
force, utilisez -D (notez que cela est irréversible) :
git branch -D nom-de-la-branche
8. Comment interrompre un rebase en cours si vous avez commis une erreur ?
 Annuler un rebase en cours : Si vous avez fait une erreur pendant le rebase et que vous
souhaitez l'annuler, vous pouvez utiliser la commande suivante :
git rebase –abort
Cela annule toutes les modifications du rebase et ramène la branche à son état
initial, avant que le rebase ne commence.
9. Comment lister les commits qui vont être rebasés avant de lancer un rebase ?
 Lister les commits à rebaser : Pour voir les commits de ma-fonctionnalite qui ne sont
pas dans main
 git log master..ma-fonctionnalite
 Cette commande montre la liste des commits sur ma-fonctionnalite
qui seront rebasés sur main. Vous pouvez ainsi vérifier quels
commits seront affectés avant de lancer le rebase.
 8. Comment afficher la liste des branches actives et en cours de
développement dans GitFlow ?
Afficher les branches actives : Vous pouvez utiliser la commande suivante pour lister toutes les branches
:
git branch
 Cette commande affiche toutes les branches locales, y compris
celles créées avec GitFlow.
 Lister les branches GitFlow spécifiques : Bien que GitFlow ne
fournisse pas une commande directe pour afficher les branches

actives, vous pouvez voir les branches GitFlow spécifiques (comme
feature, release, hotfix) en utilisant la commande suivante :

git branch | grep "feature/" # pour les branches de fonctionnalités
git branch | grep "release/" # pour les branches de versions
git branch | grep "hotfix/" # pour les branches de correctifs
9. Comment annuler une branche de correctif (hotfix) avant de la finaliser si vous constatez une
erreur ?
 Annuler une branche de correctif (hotfix) : Pour supprimer une branche de correctif avant sa
finalisation, assurez-vous d'être sur une autre branche (comme develop ou main) et utilisez

git flow hotfix delete mon-correctif
Si cette commande n’est pas disponible, vous pouvez supprimer manuellement la branche
hotfix :
git branch -D hotfix/mon-correctif
