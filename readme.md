#﻿Tutoriel pour créer sa clé SSH et la lier à son compte

Avantages : 
- Plus d'identifiant et de mot de passe à rentrer sur git
- Sécurité augmentée

1) Sur le terminal (ctrl+alt+t) :
Taper :
```
ssh-keygen
```
(Optionnel : rentrer une passphrase (ex : un ecureuil mange une glace) l'absence de passphrase enlève un peu de securité car si quelqu'un vous mets la main sur votre clef privée il pourra alors s'en servir))

Taper:
``` bash
cat ~/.ssh/id_rsa.pub
```

_Aller sur github / profil /ssh keys
_Cliquer sur « add ssh key »
_Rentrer la clé (publique!)
_Enregistrer

2)
Lors de la création d'un nouveau dépots utiliser l'adresse SSH ( git.... ) et pas celle commençant par http://...

Pour vos dépôts existant, aller dans un de vos 'repository' sur Github auquel vous souhaitez vous connecter maintenant grâce à votre clef
_En bas à droite là où se trouve le lien de votre url habituelle, cliquez sur « SSH », copiez le lien.
Il faut alors retirer le dépot distant configuré en http
_Faire un git remote rm origin 
_Faire un git remote add origin + le lien que vous venez de copier
_Au prochain 'git push' vous n'aurez plus à saisir votre login/mot de passe

/!\ 
_N'oubliez pas de rentrer l'url correspondant à votre clé ssh, sinon Git continuera à demander l'identifiant+mot de passe
_Vous avez généré une clé publique, et une privée: cette dernière est à garder pour vous.
_Pour en savoir plus: http://www.git-attitude.fr/2010/09/13/comprendre-et-maitriser-les-cles-ssh/
