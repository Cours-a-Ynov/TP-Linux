# 🐧 TP-Linux
***
**Intervenant :** Clémence Caribaux
***
Je fait ce document en prenant compte que vous connaissez un minimum les bases des commandes linux.
## Sommaire :
1) [TPn°1 Services réseaux "17/09/2021"](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/TP1.md#1--mettre-en-place-une-machine-virtuelle)

    1) [Mettre en place une machine virtuelle](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/TP1.md#1--mettre-en-place-une-machine-virtuelle)
    2) [Configurer les services réseaux](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/TP1.md#2--configurer-les-services-réseaux)
    3) [Configurer un outil de gestion de ticket](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/TP1.md#3--configurer-un-outil-de-gestion-de-ticket)
    4) [Ajouter au serveur un plugin de remontée de poste client pour pouvoir réaliser l’inventaire du parc](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/TP1.md#4--ajoutez-au-serveur-un-plugin-de-remontée-de-poste-client-pour-pouvoir-réaliser-linventaire-du-parc)
    5) [Mettre en place un poste client Windows 10 et remonter le poste client dans l’inventaire GLPI](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/TP1.md#5--mettre-en-place-un-poste-client-windows-10-et-remonter-le-poste-client-dans-linventaire-glpi)
    6) [Mettre en place une sauvegarde de GLPI](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/TP1.md#6--mettre-en-place-une-sauvegarde-de-glpi)
    7) [Déterminer si le serveur de messagerie doit être installé sur le même serveur que GLPI ?](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/TP1.md#7--déterminer-si-le-serveur-de-messagerie-doit-être-installé-sur-le-même-serveur-que-glpi--option)
    8) [Installer et configurer le service de messagerie.](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/TP1.md#8--installer-et-configurer-le-service-de-messagerie-option)
    9) [Installer et configurer le plugin d’envoi de mail.](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/TP1.md#9--installer-et-configurer-le-plugin-denvoi-de-mail-option)
    10) [Source](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/TP1.md#-source-)

2) [TPn°2 Services réseau "04/10/2021"](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/TP2.md#-tpn2)

    1)

3) [TPn°3 Services réseaux](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/TP3.md#-tpn3)

    1)

4) [Mot à retenir](https://github.com/Cours-a-Ynov/TP-Linux/blob/main/motaretenir.md#mot-a-retenir-)

5) [Dossier des screen](https://github.com/Cours-a-Ynov/TP-Linux/tree/main/Image)

***
## 👤 Docummentation fait par :
- ``Malo LOYER-VIAUD`` alias [@Karrwolf](https://github.com/Karrwolf) (ATTENTION Problème de GIT, Malo est aussi nommé [@LemonIceStuff](https://github.com/LemonIceStuff))

***
![Logo Linux](http://i.nextmedia.com.au/news/linux-logo.jpg)
![Logo Débian](https://images-wixmp-ed30a86b8c4ca887773594c2.wixmp.com/f/23b88179-ec54-450c-8969-d7913da8e013/d1rbqib-dae623c9-3c03-42f4-9778-52a76acb7347.jpg?token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJ1cm46YXBwOjdlMGQxODg5ODIyNjQzNzNhNWYwZDQxNWVhMGQyNmUwIiwic3ViIjoidXJuOmFwcDo3ZTBkMTg4OTgyMjY0MzczYTVmMGQ0MTVlYTBkMjZlMCIsImF1ZCI6WyJ1cm46c2VydmljZTpmaWxlLmRvd25sb2FkIl0sIm9iaiI6W1t7InBhdGgiOiIvZi8yM2I4ODE3OS1lYzU0LTQ1MGMtODk2OS1kNzkxM2RhOGUwMTMvZDFyYnFpYi1kYWU2MjNjOS0zYzAzLTQyZjQtOTc3OC01MmE3NmFjYjczNDcuanBnIn1dXX0.CqOPQiOZP-4MpvHyMqfg9BOL2t613AYwjBrYy4WH5Bs "Le logo Debian")

***
*Nantes YNOV Campus - B2 Informatique - 2021/2022*
