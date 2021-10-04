[← Retour à la page principale](https://github.com/Cours-a-Ynov/TP-Linux#-tp-linux)

# 🐧 TPn°2

## Sommaire :
1) [Mettre en place une machine virtuelle](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/TP2.md#1--mettre-en-place-une-machine-virtuelle)
2) [Configurer les services réseaux](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/TP2.md#2--configurer-les-services-réseaux)
3) [Configurer les services Web](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/TP2.md#3--configurer-les-services-web)
4) [Mise en place d’une solution de haute-disponibilité](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/TP2.md#4--mise-en-place-dune-solution-de-haute-disponibilité)
5) [Axes d'améliorations](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/TP2.md#5---axes-daméliorations)
6) [Conclusion](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/TP2.md#6--conclusion)
7) [Source](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/TP2.md#-source-)

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
## 3- Configurer les services Web
### (Créer un site Web, nom de domaine, certificat SSL)

Un serveur web est un logiciel permettant de rendre accessibles à de nombreux ordinateurs (les clients) des pages web stockées sur le disque. Cette fiche pratique explique comment installer le serveur web Apache sur un système de type UNIX (typiquement une distribution de Linux telle que RedHat, Mandrake ou n'importe quelle autre).

Pour cela quelques connaissances sur Linux ou bien Unix sont nécessaires. Le but de cette fiche va être d'être capable de récupérer les sources des différents éléments nécessaires et de les compiler (un compilateur C est donc nécessaire, il est généralement installé par défaut sur la plupart des distributions Linux) afin d'avoir un système opérationnel.

L'installation suivante comprend l'installation de l'interpréteur PHP, un langage de programmation permettant de créer des pages créées dynamiquement, ainsi que le SGBD MySQL, un système de gestion de bases de données relationnelles puissant fonctionnant sous Linux (et gratuit!).

Télécharger les sources
Les sources de PHP peuvent être téléchargées sur le site https://www.php.net/
Les sources de Apache peuvent être téléchargées sur le site http://www.apache.org
Les sources de MySQL peuvent être téléchargées sur le site http://www.mysql.org
installer Apache et PHP
Décompresser les archives
~~~
tar zxvf apache_1.3.x.tar.gz  
tar zxvf php-3.0.x.tar
~~~
Configurer Apache
~~~
cd apache_1.3.x  
./configure --prefix=/www
~~~
Configurer PHP
~~~
cd ../php-3.0.x  
./configure --with-mysql --with-apache=../apache_1.3.x --enable-track-vars
~~~
Compiler PHP
Si vous préférez installer PHP dans un autre répertoire, il faut utiliser l'option de configuration --with-config-file-path=/path
~~~
make  
make install
~~~
Installer Apache
~~~
cd ../apache_1.3.x  
./configure --prefix=/www --activate-module=src/modules/php3/libphp3.a  
make  
make install
~~~
Modifier le fichier de configuration de PHP
~~~
cd ../php-3.0.x  
cp php3.ini-dist /usr/local/lib/php3.ini
~~~

Vous pouvez désormais éditer le fichier de configuration /usr/local/lib/php3.ini.
Editez le fichier de configuration du serveur apache (généralement httpd.conf ou srm.conf et ajoutez la ligne suivante :
~~~
AddType application/x-httpd-php .php
~~~
Il s'agit de choisir l'extension associée aux scripts PHP. Par souci d'homogénéité, il est courant de choisir l'extension .php

Démarrez le serveur Apache.
(Il est essentiel d'arrêter et redémarrer le serveur, et non uniquement de le relancer. Il suffit généralement de taper apachectl stop, puis apachectl start).

Premier lancement
Pour vérifier si l'installation a bien fonctionnée, il vous suffit de créer un petit fichier dans la racine des documents du serveur web (appelée DocumentRoot dans le fichier de configuration httpd.conf). Nommez ce fichier toto.php, et mettez le code suivant dans ce fichier :

~~~
<html>  
<head><title>Exemple</title></head>  
<body>  
<?php  
echo "PHP fonctionne!";  
?>  
</body>  
</html>
~~~

Lancez un navigateur sur cette machine et entrez l'URL suivante :
~~~
http://localhost/toto.php
~~~

localhost désigne la machine sur laquelle vous vous trouvez...

Vous devriez logiquement voir apparaître la phrase "PHP fonctionne!" sur votre navigateur !

***
## 4- Mise en place d’une solution de haute-disponibilité
### (Configurer Corosync, Pacemaker).


***
## 5- 📈 Axes d'améliorations.

J'ai vraiment trouvé le cours sympathique à apprendre surtout en manipulant. Cependant j'aurais aimé que l'on est des moments ou l'on se réunit pour voir ou tout le monde se situe et si des questions sont  à poser ou des informations pouvant être données soient mise en commun.

***
## 6- Conclusion.

Pour conclure j’ai pu répondu à tout les objectifs demander. Le TP m’a appris à créer un gestionnaire libre de parc informatique (GLPI) puis de configurer une sauvegarde automatique via CRON et aussi la création d’une messagerie. De plus j’ai pu renforcer mes compétences dans la création de VM Windows et linux et la configuration des services réseaux.

***
## 🔍 Source :
####

***
[← Retour à la page principale](https://github.com/Cours-a-Ynov/TP-Linux#-tp-linux)
