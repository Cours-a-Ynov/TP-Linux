[← Retour à la page principale]()

# 🐧 TPn°1

## Sommaire :
a) [Mettre en place une machine virtuelle]()
b) [Configurer les services réseaux]()
c) [Configurer un outil de gestion de ticket]()
d) [Ajouter au serveur un plugin de remontée de poste client pour pouvoir réaliser l’inventaire du parc]()
e) [Mettre en place un poste client Windows 10 et remonter le poste client dans l’inventaire GLPI]()
f) [Mettre en place une sauvegarde de GLPI]()
g) [Déterminer si le serveur de messagerie doit être installé sur le même serveur que GLPI ?]()
h) [Installer et configurer le service de messagerie.]()
i) [Installer et configurer le plugin d’envoi de mail.]()
j) [Source]()

***
## 1- Mettre en place une machine virtuelle
#### (Configuration réseau, accès à Internet, SSH)

Pour installer **Debian11** il va falloir [Cliquez sur ce lien](https://cdimage.debian.org/debian-cd/current/amd64/iso-cd/debian-11.0.0-amd64-netinst.iso) et alors vous téléchargerez **amd64 CD** :

Ainsi que **VMWorkstation** [Télécharger](https://www.vmware.com/go/getworkstation-win) et faites une installation classique de logiciel.



***
## 2- Configurer les services réseaux
#### (Adresse IP, résolution DNS)

***
## 3- Configurer un outil de gestion de ticket
#### (Installer et configurer GLPI, ajouter un Utilisateur, supprimer l’Utilisateur par défaut)

Dans un premier temps il faut mettre à jour les packets avec la commande suivante:
~~~
> apt-get update && apt-get upgrade
~~~

On installe ensuite **Apache 2** :
~~~
> apt-get install apache2 php libapache2-mod-php
~~~

Ainsi que **PHP** :
~~~
> apt-get install php-imap php-ldap php-curl php-xmlrpc php-gd php-mysql php-cas
~~~

On installe **MariaDB** en repondant Y à toute les questions :
~~~
> apt-get install mariadb-server
> mysql_secure_installation
~~~

On installe les modules complémentaires :
~~~
> apt-get install apcupsd php-apcu
~~~

On redemarre les services :
~~~
> /etc/init.d/apache2 restart
> /etc/init.d/mysql restart
~~~

On entre dans les paramètres de **MariaDB** :
~~~
> mysql -u root -p
~~~

On crée ensuite la base de donnée qui nous permettra d'installer le **GLPI**, on y met un nom d'utilisateur ainsi qu'un mot de passe :
~~~
MariaDB [(none)]> create database glpidb; 
MariaDB [(none)]> grant all privileges on glpidb.* to glpiuser@localhost identified by "votre-mot-de-passe";
MariaDB [(none)]> quit
~~~

On installe **phpMyAdmin** :
~~~
> apt-get install phpmyadmin
~~~

On peut donc enfin installer **GLPI** en toute tranquilité et en ligne de commande :
~~~
> cd /usr/src/
> wget https://github.com/glpi-project/glpi/releases/download/9.3.3/glpi-9.3.3.tgz
> tar -xvzf glpi-9.3.3.tgz -C /var/www/html
~~~

Nous allons ensuite donner les droits :
~~~
> chown -R www-data /var/www/html/glpi/
~~~

Nous allons ensuite configurer **GLPI**.
Il va falloir aller sur l'adresse suivante :
~~~
http://*son adresse IP*/glpi
~~~
Alors vous allez atterir sur cette page si :
![](https://user.oc-static.com/upload/2019/01/29/15487708638493_image36.png)

On appuie sur OK, on accepte les thermes et on clique sur continuer.
![](https://user.oc-static.com/upload/2019/01/29/15487709292633_image8.png)

Ensuite nous atterissons sur cette page et nous faisons **INSTALLER**.
![](https://user.oc-static.com/upload/2019/01/29/15487709822209_image23.png)

Nous allons ensuite être dirigé sur cette page, il faut verifier que tout soit avec une coche verte, et cliquer sur continuer. Si ce n'est pas le cas il faut régler les problemes qui sont souvent les suivants :

S’il manque l’extension CAS, la commande est la suivante →  
~~~
> apt-get install php-cas
~~~
S’il manque l’extension CURL, la commande sera →  
~~~
> apt-get install php-curl
~~~
etc.
![](https://user.oc-static.com/upload/2019/01/29/15487710173635_image6.png)

Sur cette fenêtre, nous allons **associer GLPI à sa base de données** créée précédemment sur **MariaDB**.
Il faut donc bien reprendre ce que l'on a rentré dans MariaDB et non inventer des logs.
Ensuite cliquer sur continuer.
![](https://user.oc-static.com/upload/2019/01/29/15487712420173_image28.png)

Qaund vous atterissez sur cette page vous selectionnez **glpidb** puis cliquez sur continuer.
![](https://user.oc-static.com/upload/2019/01/29/15487714238912_image12.png)

Si vous avez cette page cela voudra dire que vous avez bien configué le **GLPI** et donc cliquez sur continuer.
![](https://user.oc-static.com/upload/2019/01/29/15487716041866_image34.png)

L'installation est donc terminée, on clique alors sur **Utiliser GLPI**.
![](https://user.oc-static.com/upload/2019/01/29/15487716699915_image9.png)

Nous atterissons donc sur la page des login pour utiliser GLPI.
Les identifiants de base sont :
~~~
Identifiant : glpi
Mot de passe : glpi
~~~
![](https://user.oc-static.com/upload/2019/01/29/15487717733595_image2.png)

***
## 4- Ajoutez au serveur un plugin de remontée de poste client pour pouvoir réaliser l’inventaire du parc
#### (Installer Fusion Inventory)

Il va falloir aller dans le repertoire suivant et entrer les commandes qui suivent pour pouvoir installer le plugin **FusionInventory** :
~~~
> cd /usr/src
> wget https://github.com/fusioninventory/fusioninventory-for-glpi/archive/glpi9.3+1.3.tar.gz
> tar -zxvf glpi9.3+1.3.tar.gz -C /var/www/html/glpi/plugins 
~~~

Ainsi on lui attribue les droits :
~~~
chown -R www-data /var/www/html/glpi/plugins
~~~

On prépare la compatibilité en allant dans le dossier plugins :
~~~
> cd /var/www/html/glpi/plugins
> mv fusioninventory-for-glpi-glpi9.3-1.3/ fusioninventory/
~~~

On retourne sur notre page de connexion au **GLPI**. On s'y connecte.
![](https://user.oc-static.com/upload/2019/01/29/15487725681875_image25.png)

Une fois connecté, rendez vous dans la rubrique suivante : Configuration > Plugins :
![](https://user.oc-static.com/upload/2019/01/29/15487727238486_image11.png)

On atterit donc sur cette page ci si tout est bon, nous devrions voir le plugins s'afficher. Si c'est le cas vous allez pouvoir cliquez sur **Installer**. Ensuite un bouton **Activer** s'affichera, cliquez dessus.
![](https://user.oc-static.com/upload/2019/01/29/15487727999289_image21.png)

Rendez-vous dans : Administration > FusionInventory. Ou nous voyons le menu de configuration. Un message d'erreur s'affiche indiquant que (une absence de cron.php du GLPI dans le cron de Linux).
![](https://user.oc-static.com/upload/2019/01/29/15487729341367_image19.png)

Nous allons donc résoudre le problème :
~~~
> crontab -u www-data -e
~~~

~~~
*/1 * * * * /usr/bin/php5 /var/www/html/glpi/front/cron.php &>/dev/null
~~~

Redmarrez ensuite daemon du **cron** avec la commande suivante :
~~~
> /etc/init.d/cron restart
~~~

Retournez ensuite sur la page web de GLPI et allez dans le menu : Configuration > Actions Automatiques.
Dans la liste (souvent en page 2), cherchez l’action automatique nommée TaskScheduler  :
![](https://user.oc-static.com/upload/2019/01/29/15487733998798_image40.png)

Cliquez dessus pour ouvrir et ensuite Cliquez sur **Executer**.
Si vous retournez dans : Administration > FusionInventory, le message d’erreur en jaune devrait avoir disparu !
![](https://user.oc-static.com/upload/2019/01/29/1548773509188_image17.png)

***
## 5- Mettre en place un poste client Windows 10 et remonter le poste client dans l’inventaire GLPI
#### GLPI (Fusion Inventory)

Pour télécharger l’agent Fusion 2.4.2 pour Windows (64 bit), [cliquez sur ce lien de téléchargement](https://github.com/fusioninventory/fusioninventory-agent/releases/download/2.4.2/fusioninventory-agent_windows-x64_2.4.2.exe).

Une fois le téléchargement effectué, exécutez l’installation de l’agent en mode Administrateur (clic droit > Exécuter en tant qu’administrateur).
![](https://user.oc-static.com/upload/2019/01/29/15487739682453_image4.png)

Vous arrivez ensuite sur l'écran de bienvenue. Cliquez sur **Suivant** :
![](https://user.oc-static.com/upload/2019/01/29/15487740560574_image30.png)

La seconde fenêtre est un rappel de la licence. Là encore, pensez à lire les licences avant de les accepter. Cliquez ensuite sur **Suivant**.
La fenêtre suivante ouvre un choix des outils inclus dans **FusionInventory**, que l'on va pouvoir installer.
![](https://user.oc-static.com/upload/2019/01/29/15487741223551_image24.png)

L'écran suivant vous propose l’installation de l’agent Fusion dans un répertoire par défaut. Vous pouvez changez la destination des fichiers d’installation en cliquant sur le bouton **Parcourir…**. Une fois votre choix arrêté, cliquez sur **Suivant**.
![](https://user.oc-static.com/upload/2019/01/29/15487757664963_image39.png)

En effet, une fois que l’agent Fusion a fait son inventaire, il doit envoyer ses résultats à votre serveur. Pour ce faire, vous devez indiquer la destination, comme dans l’exemple ci-dessous. Pour personnaliser votre manipulation, remplacez l’adresse **IP** de l’exemple par la vôtre :
![](https://user.oc-static.com/upload/2019/01/29/15487742401926_image33.png)

Une fois votre agent installé, ouvrez un navigateur web sur le client et tapez l’adresse "http://localhost:62354".
Si l'installation est correcte, vous devriez voir un résultat similaire apparaître :
![](https://user.oc-static.com/upload/2019/01/29/15487761693585_image22.png)

Pour ce faire, cliquez sur Administration > FusionInventory. Puis, dans le sous-menu, sur Général > Gestion des Agents :
![](https://user.oc-static.com/upload/2019/01/29/15487763077273_image13.png)

Vous trouverez alors la liste des agents remontés dans FusionInventory. Vous devriez y retrouver votre machine.
![](https://user.oc-static.com/upload/2019/01/29/15487763919247_image3.png)

***
## 6- Mettre en place une sauvegarde de GLPI
#### (Configurer une tâche CRON)

Nous allons créer un script qui s’exécutera quotidiennement (pour l'exemple) il est à placer dans le dossier :
~~~
/etc/cron.daily.
~~~

On nommera le fichier **backup.sh**.

Une fois dans le dossier il faut lui donner les droits nécessaires pour l’exécution, voici la commande a taper :
~~~
> chmod 700 backup.sh
~~~

Voici le script a inscrire dans le fichier :
~~~
1.  #!/bin/bash
2.
3.  # date du jour
4.  backupdate=$(date +%Y-%m-%d)
5.
6.  #répertoire de backup
7.  dirbackup=/backup/backup-$backupdate
8.
9.  # création du répertoire de backup
10. /bin/mkdir $dirbackup
11.
12. # tar -cjf /destination/fichier.tar.bz2 /source1 /source2 /sourceN
13. # créé une archive bz2
14. # sauvegarde de /home
15. /bin/tar -cjf $dirbackup/home-$backupdate.tar.bz2 /home
16.
17. # sauvegarde mysql
18. /usr/bin/mysqldump --user=xxxx --password=xxxx --all-databases | /usr/bin/gzip > $dirbackup/mysqldump-$backupdate.sql.gz
~~~

***
## 7- Déterminer si le serveur de messagerie doit être installé sur le même serveur que GLPI ? (option).

D'apres moi il est mieux de l'installer sur un serveur appars car

***
## 8- Installer et configurer le service de messagerie (option).

Postfix est un serveur de messagerie électroniquesous licencepublique. Il est utilisé pour l’acheminement de courriers électroniques. Il l’uns des nombreux logiciels de messagerie existants tel que Sendmail.Il est communémentappelé MTA (Message Transport Agent)
~~~
> apt-get install postfix
~~~

Prendre l’option Internet avec un «smarthost»
Le nom de courrier sera: entreprise.com
Effacer le serveur relais SMTP
Créer un utilisateur avec  adduser [nom]
Nous allons créer 2 utilisateurs: Sandrine et Ingrid
~~~
> adduser sandrine
~~~

Le document de configuration de Postfix se trouve dans l’arborescence suivante:Nano 
~~~
/etc/postfix/main.cf
~~~

Commentez la ligne Mailbox_command puis créer la ligne
~~~
 home_mailbox=Maildir/
~~~

Cette manipulation va nous permettre de faire en sorte que l’utilisateur reçoive ses mails dans son dossier personnel.
Le dossier de chaqueutilisateurs contiendra un dossier  Maildir dans lequel se trouvera:
•New (nouveaux mails)
•Cur (mails lus)
•Temp (brouillons)
Une fois cette configuration établie, redémarrez Postfix.

##### A noter :
Le redémarrage de postfix est nécessaire une fois la configuration changée: 
~~~
/etc/init.d/postfix restart
~~~
Taper :
~~~
tail -30 /var/log/syslog
~~~
pour avoir un rapport détaillé de ce qui s’est déroulé.

***
## 9- Installer et configurer le plugin d’envoi de mail (option).

Dans cette partie nous allons utiliser Outlook version 2010.Avant toutes choses, il faut savoir ce qu’est un serveur pop et smtp:
•Pop.[nomDeDomaine] représente le serveur de courrier entrant
•Smtp.[nomDeDomaine] représente le serveur de courrier sortant
Actuellement, notre serveur de messagerie n’est pas capable d’utiliser les serveurs pop et smtp.

Pour cela, nous devons procéder à l’installation de ces derniers:
•apt-get install courier-authdaemon courier-base courier-imap courier-maildrop courier-pop courier-pop-ssl courier-imap-ssl
•Aller dans l’onglet Fichier de Outlook
•Cliquez sur Ajouter un compte•Configurer Manuellement les paramètres du serveur
•Messagerie internetPage 5
•Remplir le formulaire:Sandrine à maintenant son compte correctement configuré sur le client de messagerie:

Maintenant, vous pouvez faire de même pour l’utilisateur ingrid!

***
## 🔍 Source :
#### - [Numetopia](https://www.numetopia.fr/comment-parametrer-virtualbox-pour-acceder-au-reseau-local/)
#### - [Neptunet](https://neptunet.fr/install-glpi/)
#### - [Open Classroom](https://openclassrooms.com/fr/courses/1730516-gerez-votre-parc-informatique-avec-glpi/5993816-installez-votre-serveur-glpi)
#### - [Open Classroom](https://openclassrooms.com/fr/courses/1730516-gerez-votre-parc-informatique-avec-glpi/5994176-installez-le-plugin-et-l-agent-fusioninventory)
#### - [DocPlayer](https://docplayer.fr/3049813-Installer-un-serveur-de-messagerie-sous-linux.html)
#### - [Hostinger](https://www.hostinger.fr/tutoriels/cron-job/)

***
[← Retour à la page principale]()