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
