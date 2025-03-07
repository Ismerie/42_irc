# 42_irc
42_irc est un projet de groupe de l'école 42 dans lequel nous devons créer notre propre serveur IRC, suivant les normes Internet RFC.  
Ce projet a été réalisé avec [@ThibautCharpentier](https://github.com/ThibautCharpentier)

## 📋 Règles
Le serveur est capable de gérer plusieurs clients en même temps et ne jamais bloquer. Un seul **poll()** est utilisé pour gérer toutes ces opérations.  
**Irssi** est le client IRC utilisé. La communication entre le client et le serveur doit se faire via **TCP/IP**.

Les fonctionnalités suivantes sont implémentées :
* On peut s'authentifier, définir un **pseudo**, un **nom d'utilisateur**, rejoindre une **chaîne**, envoyer et recevoir des messages privés.
* Tous les messages envoyés d'un client à un **canal** sont transmis à tous les autres clients ayant rejoint le **canal**.
* Il y a **des opérateurs** et des utilisateurs réguliers.

Les commandes spécifiques aux opérateurs sont implémentés :
* ```KICK``` - Ejecter un client d'un canal
* ```INVITE``` - Inviter un client sur une chaîne
* ```TOPIC``` - Modifier ou afficher le sujet de la chaîne
* ```MODE``` - Changer le mode du canal :
  * **i** : pour définir/supprimer le canal sur invitation uniquement
  * **t** : pour définir/supprimer les restrictions de la commande ```TOPIC```
  * **k** : pour définir/supprimer la clé du channel
  * **o** : pour donner/prendre le privilège d'opérateur de canal
  * **l** : pour définir/supprimer la limite d'utilisateurs au canal.

### ✨ Bonus
Nous avons crée **un bot** capable de se connecter au serveur. Le bot peut répondre à plusieurs commandes si un utilisateur le demande avec la commande ```NOTICE```

## 🛠️ Usage
Utilisez la commande ```make``` pour compiler et exécutez le serveur avec :
```
./ircserv <port> <password>
```
Exemple:
```
./ircserv 6667 password
```
Ensuite, ouvez un nouveau prompt et utilisez la commande suivante pour connecter un client au serveur :
```
irssi -c localhost -p 6667 -w password
```
### ✨ Bonus
Pour exécuter la partie bonus, déplacez-vous vers le dossier ```bonus``` et utilisez la commande ```make```. Ensuite, lancez le serveut bonus avec :  
```
./ircserv_bonus <port> <password>
```
Exemple:
```
./ircserv_bonus 6667 password
```
Ensuite, ouvrez une autre prompt et accédez au dossier ```bonus/bot```. Utilisez la commande ```make``` et exécutez le bot avec :
```
./ircbot <name> <host> [port] [password]
```
Exemple:
```
./ircbot bot localhost 6667 password
```

Désormais, avec un client connecté vous poouvez parler au bot avec cette commande par exemple :
```
/notice bot !help
```
