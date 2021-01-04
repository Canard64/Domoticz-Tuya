# Domoticz-Tuya
Utilisation des API tuya pour intégration dans DOMOTICZ

[![made-with-python](https://img.shields.io/badge/Made%20with-Python-1f425f.svg)](https://www.python.org/)
Creer un compte sur la plateforme 

## Comment ça marche ?
### Step 1 - Obtenir des clés et lié son compte

1. Créez un compte sur ce site https://developer.tuya.com/en/cloud-development 
![Get Ids](img/CloudDev.jpg)
2. Enregistrez vos prises dans l'application via votre téléphone  ([Android](https://play.google.com/store/apps/details?id=com.tuya.smart&hl=fr) or [IOS](https://apps.apple.com/fr/app/tuyasmart/id1034649547)). 
3. Une fois le compte validé, cliquez sur "**Cloud Development**" dans la barre en haut puis cliquez sur  "**Create**".  Après avoir créé l'application cliquez dessus pour obtenir vos clés.
![Get Ids](img/CreateSAASApp.jpg)
4. A partir d'ici ma solution diffère un peu. Dans le menu de gauche cliquez sur "**Linked Devices**". Sélectionnez l'onglet "**Link devices by App Account**". Sur votre téléphone allez dans  "**Profil**" cliquez sur l’icône  "**Scan**". Dans la page web cliquez sur  "**Add App Account**" and scannez le QR code. Votre compte est maintenant lié "_Tuya Cloud_".

### Step 2 - Configure the application
Dans le dossier du script vous trouverez `code.json.model`. Renommez le en `code.json` et complétez le avec les informations Client ID et Client Secret.

![Get Ids](img/CloudDev.jpg)

`{
   "devices":{
      "prise_a":"",
      "prise_b":""
   },
   "client_id":"",
   "app_id":""
}`

La liste des devices est totalement optionnelle pour le moment. Je l'ai ajouté afin de garder en mémoire les ids des prises. Ces derniers se trouvent dans l'application dans les informatins du Device à la ligne ID Virtuel.


### Step 3 - Play with it
Ce script envoi des requêtes au Cloud Tuya pour envoyer des commandes aux prises.


`Options available
main.py --switch <ID> <True|False>
main.py --status <ID>
main.py --toggle <ID>`

## Installation 

Dans votre dossier de scripts Domoticz clonez le repo.

`git clone https://github.com/BreizhCat/domoticz-tuya.git `

Ajoutez le mode éxecutable au fichier main.py.
`chmod a+x main.py`


Dans Domoticz créez un dummy device et sur les actions On & Off appeller le script avec l'option switch True or False.

![Dummy Switch](assets/2.png)



