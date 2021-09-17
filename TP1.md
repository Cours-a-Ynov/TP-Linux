[← Retour à la page principale](https://github.com/Cours-a-Ynov/TP-Linux#-tp-linux)

# 🐧 TPn°1

## Sommaire :
1) [Mettre en place une machine virtuelle](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/TP1.md#1--mettre-en-place-une-machine-virtuelle)
2) [Configurer les services réseaux](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/TP1.md#2--configurer-les-services-réseaux)
3) [Configurer un outil de gestion de ticket](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/TP1.md#3--configurer-un-outil-de-gestion-de-ticket)
4) [Ajouter au serveur un plugin de remontée de poste client pour pouvoir réaliser l’inventaire du parc](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/TP1.md#4--ajoutez-au-serveur-un-plugin-de-remontée-de-poste-client-pour-pouvoir-réaliser-linventaire-du-parc)
5) [Mettre en place un poste client Windows 10 et remonter le poste client dans l’inventaire GLPI](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/TP1.md#5--mettre-en-place-un-poste-client-windows-10-et-remonter-le-poste-client-dans-linventaire-glpi)
6) [Mettre en place une sauvegarde de GLPI](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/TP1.md#6--mettre-en-place-une-sauvegarde-de-glpi)
7) [Déterminer si le serveur de messagerie doit être installé sur le même serveur que GLPI ?](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/TP1.md#7--déterminer-si-le-serveur-de-messagerie-doit-être-installé-sur-le-même-serveur-que-glpi--option)
8) [Installer et configurer le service de messagerie.](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/TP1.md#8--installer-et-configurer-le-service-de-messagerie-option)
9) [Installer et configurer le plugin d’envoi de mail.](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/TP1.md#9--installer-et-configurer-le-plugin-denvoi-de-mail-option)
10) [Conclusion](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/TP1.md#10--conclusion)
11) [Source](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/TP1.md#-source-)

***
## 1- Mettre en place une machine virtuelle
#### (Configuration réseau, accès à Internet, SSH)

Pour installer **Debian11** il va falloir [Cliquez sur ce lien](https://cdimage.debian.org/debian-cd/current/amd64/iso-cd/debian-11.0.0-amd64-netinst.iso) et alors vous téléchargerez **amd64 CD** :

Ainsi que **VMWorkstation** [Télécharger](https://www.vmware.com/go/getworkstation-win) et faites une installation classique de logiciel.

Nous allons donc suite a tout ce qui a été fait précédement créer la VM en cliquant sur **create a new machine** :
![](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/Image/Creation1.png)

Ensuite chercher le chemein ou vous avez mis le cd d'installation que vous avez telechargez au prealable :
![](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/Image/creation2.png)

Séléctionnez **Linux** et chercher **Debian 10.x 64-bit** :
![](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/Image/creation3.png)

Renommer comme vous souhaitez le nom de la **VM** :
![](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/Image/creation4.png)

Attribuez le nombre d'espace local a votre **VM** :
![](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/Image/creation5.png)

Verifiez que tout est bon ajoutez de la ram si vous le souhaitez :
![](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/Image/creation6.png)

Ensuite lancez la **VM** et faite **entrer** sur **Install** pour une installation normale :
![](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/Image/creation7.png)

Selectionner la langue Francaise ou celle que vous voulez et ce trois fois de suite :
![](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/Image/creation8.png)

Cela va ensuite charger et installer :
![](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/Image/creation9.png)

Faite **entre** pas besion de modifier debian :
![](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/Image/creation10.png)

Ne rien ecrire juste faire **entrer** :
![](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/Image/creation11.png)

Faites votre mot de passe **ADMIN** il faudra ensuite le valider :
![](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/Image/creation12.png)

Il faudra ensuite creer un utilisateur mettez le nom de votre choix :
![](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/Image/creation13.png)

Faite entrer l'identifiant sauf si vous souhaitez le modifier :
![](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/Image/creation14.png)

Creer ensuite le mot de passe de l'utilisateur et confimez le :
![](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/Image/creation15.png)

Enuite selectionner **utiliser un disque entier** :
![](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/Image/creation15.png)

Faites **entrer** :
![](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/Image/creation17.png)

Selectionner **Tout dans une seule partition** :
![](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/Image/creation18.png)

Séléctionner **Terminer** :
![](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/Image/creation19.png)

Faites appliquer les changements en selectionnant **OUI** :
![](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/Image/creation20.png)

Le systeme va s'installer :
![](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/Image/creation21.png)

Mettez **NON** au analyse :
![](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/Image/creation22.png)

Selectionner la langue **Francaise** ou celle de votre choix :
![](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/Image/creation23.png)

Selectionner **deb.debian.org** :
![](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/Image/creation24.png)

N'entrez rien faites juste entrer :
![](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/Image/creation25.png)

Par la suite faites le choix suivants et surtout selectionner **server SSH** :
![](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/Image/creation26.png)

Tout s'installera par la suite :
![](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/Image/creation27.png)

Selctionner **OUI** pour que les demarrage ce fasse sur le programme **GRUB** :
![](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/Image/creation28.png)

Pour le choix du périphérique séléctionner **/dev/sda** :
![](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/Image/creation29.png)

Et voila votre machine est fini d'installer cliquez sur **Continuer** :
![](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/Image/creation30.png)

Pour avoir accès a internet allez dans les paramètre de la **VM** et dans **Network Adapter** puis seletionnez **Bridged** :
![](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/Image/ConfigInternet.png)

***
## 2- Configurer les services réseaux
#### (Adresse IP, résolution DNS)

Pour connaitre mon adresse IP je fait la commande suivante :
~~~
> ip a
~~~

Et je peut connaitre mon adresse **IP** au meme niveau que l'encadrer rouge ici meme :
![](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/Image/ip1.png)

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

D'après moi il est mieux de l'installer sur un serveur appars car cela eviterai deja d'avoir des mails dans les sauvegardes du serveur **GLPI**.

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
- Pop.[nomDeDomaine] représente le serveur de courrier entrant
- Smtp.[nomDeDomaine] représente le serveur de courrier sortant
Actuellement, notre serveur de messagerie n’est pas capable d’utiliser les serveurs pop et smtp.

Pour cela, nous devons procéder à l’installation de ces derniers:
- apt-get install courier-authdaemon courier-base courier-imap courier-maildrop courier-pop courier-pop-ssl courier-imap-ssl
- Aller dans l’onglet Fichier de Outlook
- Cliquez sur Ajouter un compte•Configurer Manuellement les paramètres du serveur
- Messagerie internet
- Remplir le formulaire :
![](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/Image/mail1.png)

***
## 10- Conclusion.

Pour conclure j’ai pu répondu à tout les objectifs demander. Le TP m’a appris à créer un gestionnaire libre de parc informatique (GLPI) puis de configurer une sauvegarde automatique via CRON et aussi la création d’une messagerie. De plus j’ai pu renforcer mes compétences dans la création de VM Windows et linux et la configuration des services réseaux.

***
## 🔍 Source :
#### - [Numetopia](https://www.numetopia.fr/comment-parametrer-virtualbox-pour-acceder-au-reseau-local/)
#### - [Neptunet](https://neptunet.fr/install-glpi/)
#### - [Open Classroom](https://openclassrooms.com/fr/courses/1730516-gerez-votre-parc-informatique-avec-glpi/5993816-installez-votre-serveur-glpi)
#### - [Open Classroom](https://openclassrooms.com/fr/courses/1730516-gerez-votre-parc-informatique-avec-glpi/5994176-installez-le-plugin-et-l-agent-fusioninventory)
#### - [DocPlayer](https://docplayer.fr/3049813-Installer-un-serveur-de-messagerie-sous-linux.html)
#### - [Hostinger](https://www.hostinger.fr/tutoriels/cron-job/)

***
[← Retour à la page principale](https://github.com/Cours-a-Ynov/TP-Linux#-tp-linux)
