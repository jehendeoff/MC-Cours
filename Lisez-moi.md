#mc #cours
# Objectif
> Faire des cours d'AP où l'on apprend à coder / héberger un serveur Minecraft

# Introduction
Avant de faire quoi que ce soit, tous les élèves devront installer les prérequis disponibles dans [[Prérequis]]

Minecraft est un jeu développé en Java d'abord par Markus Persson (Notch) puis désormais Mojang. 
C'est dorénavant un jeu basé sur une architecture client-serveur, même en solo, un serveur tourne en fond.
Ce jeu a été créé en 2007, depuis tout ce temps, il existe énormément de façon de modifier et de coder des ajouts pour ce jeu.


Il existe différents types de modifications, des modifications serveurs et des modifications client.

Les modifications clients requièrent que chaque utilisateur télécharge et exécute un client modifié (la plupart du temps, un client permettant l'ajout de modification (forge, fabric, quilt, liteloader, etc.) est distribué, et ce client permet d'ajouter des Mods à Minecraft. Ce qui évite de devoir modifier et envoyer tout un client pour faire de simples modifications.

Le même modèle de modification est aussi disponible pour les serveurs, les serveurs les plus souvent utilisés sont : 
- [SpigotMC](https://www.spigotmc.org/) était basé sur Bukkit, qui appartenait à Mojang mais qui a été fermé, car dé compilait le code source de Minecraft et le re-distribuait, spigot lui n'applique que des patchs au code de base
- [PaperMC](https://papermc.io/software/paper) est basé sur SpigotMC, est fait pour plus d'optimisation de performance
- [Folia](https://papermc.io/software/folia) est basé sur PaperMC, mais au lieu d'avoir qu'un thread principal qui gère tout le monde, désormais un thread est attribué à chaque groupe de joueurs, permettant d'accueillir beaucoup plus de joueurs 
- [Pufferfish](https://pufferfish.host/downloads) est basé sur PaperMC et n'est fait que pour avoir plus de performance 
- [PurpurMC](https://purpurmc.org/) est basé sur PaperMC et est fait pour rendre plus de chose personnalisable
- [Glowstone](https://glowstone.net/) n'est pas basé sur un autre logiciel. Glowstone ont l'ambition de re-coder tout un serveur de A à Z en faisant du reverse-engineering sur le protocol utilisé par minecraft. Les fous derrières ce projet ont même décidé d'utiliser la même API que PaperMC

Il existe aussi des Proxys et d'autres logiciels, mais dans le but de donner un simple entre vue sur les technologies et logiciels utilisé, je ne vais pas m'y attardé.

Les SLAM vont devoir faire des modifications serveurs (plus souvent appelé `plugins`) pour le logiciel Pufferfish (qui compatible avec l'API de PaperMC qui lui-même est compatible avec l'API SpigotMC qui lui-même est compatible avec l'API Bukkit qui lui-même est compatible avec l'API CraftBukkit)

Les SISR vont devoir faire fonctionner et administrer un panneau d'administration de serveur de jeu, ce dernier est Pterodactyl