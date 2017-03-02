#﻿Tutoriel pour créer sa clé SSH et la lier à son compte

Avantages : 
- Plus d'identifiant et de mot de passe à rentrer sur git
- Sécurité augmentée

1) Sur le terminal (ctrl+alt+t) :
Taper :
```
ssh-keygen
```
(Optionnel : rentrer une passphrase (ex : un ecureuil mange une glace) l'absence de passphrase enlève un peu de securité car si quelqu'un vous mets la main sur votre clef privée il pourra alors s'en servir)  
Conseil : ne pas en mettre pour gagner du temps.


Taper:
``` bash
cat ~/.ssh/id_rsa.pub
```
Copier la chaîne qui s'affiche en prenant garde de ne pas prendre d'espace à la fin ou au début

2)
- [Aller sur github](https://github.com/settings/keys)
- Cliquer sur « New ssh key »
- Rentrer la clé (publique!)
- Enregistrer

Lors de la création d'un **nouveau dépot** ou d'un **clone** utiliser l'adresse SSH ( git@.... ) et pas celle commençant par http://...
exemple du format de l'url origin de ce dépot : git@github.com:Boyquotes/Tutosshkey.git  
- Au prochain 'git push' vous n'aurez plus à saisir votre login/mot de passe

Pour vos dépôts déjà existant en local et cloner avec l'url en http (vous pouvez vérirfier en utilisant la commande git config --list ), ils ont donc leur remote configuré en http. Pour changer la configuration, aller dans un de vos 'repository' sur Github auquel vous souhaitez vous connecter maintenant grâce à votre clef et donc en utilisant l'url git@
- Sur la page du dépot à droite, en dessous du bouton "Clone or download" là où se trouve le lien de votre url habituelle, cliquez sur « SSH », copiez le lien.
Il faut alors donc retirer le dépot distant configuré avec la méthode http
- Faire un 
```
git remote rm origin 
```
- et Faire un
```
git remote add origin + le lien que vous venez de copier
```
- Au prochain 'git push' vous n'aurez plus à saisir votre login/mot de passe

/!\ 
- N'oubliez pas de rentrer l'url correspondant à votre clé ssh, sinon Git continuera à demander l'identifiant+mot de passe
- Vous avez généré une clé publique, et une privée: cette dernière est à garder pour vous.
- Vous pouvez voir l'URL qui est configuré comme url origin distante :
```
git config --list
```
- Pour en savoir plus: http://www.git-attitude.fr/2010/09/13/comprendre-et-maitriser-les-cles-ssh/
