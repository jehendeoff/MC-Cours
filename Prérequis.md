# Objectif
> Installer les outils nécessaires pour le développement / l'hébergement de serveur Minecraft

# Introduction
Minecraft est un jeu basé sur le langage Java (il existe une version c#, Minecraft Bedrock, mais plus limitée).
Différentes versions de Minecraft utilisent différentes versions de java, nous allons utiliser la version 1.20 de Minecraft, qui utilise java 17.
Puisque tout le monde devra tester que ce qu'il fait fonctionne, tout le monde doit installer Minecraft 1.20.

Ceux qui ont un compte Minecraft payé, vous pouvez l'installer comme bon vous semble (le launcher Minecraft officiel gère les versions de java, sinon, vous devrez Installer JAVA) 
Pour ceux qui n'ont pas de compte Minecraft payé, il vous faudra passer par un launcher cracké, ces derniers n'installent pas java, vous devrez donc 

# Installer Java
## Préambule
Il existe différentes versions de Java : JRE, JSE, JDK
- JRE signifie `Java Runtime Environment`, n'est plus disponible pour les versions récentes de java, c'est une version permettant uniquement d'exécuter.
- JSE signifie `Java platform Standart Edition`, pour notre utilisation, c'est simplement JRE.
- JDK signifie `Java Development Kit`, la version avec les outils de développement, contient JRE, donc pas besoins d'installer deux versions.

Nous voulons installer le JDK, même si nous n'allons pas développer, les versions JRE / JSE sont compliquées à avoir depuis la version 11.

## Téléchargement
Il vous faudra aller [le site de Java](https://www.oracle.com/java/technologies/javase/jdk17-archive-downloads.html) puis télécharger la version la plus récente (17.09 lors de l'écriture) compatible avec votre OS (`Windows x64 MSI Installer`).

Si vous n'avez pas envie de chercher, voici [le lien](https://download.oracle.com/java/17/archive/jdk-17.0.9_windows-x64_bin.msi) pour `Java 17.0.9 Windows x64 MSI Installer`.

## Installation
![[Pasted image 20231031142921.png]]
Ceci est l'installateur de Java 17, vous pouvez choisir ou installer Java sur la deuxième page (si vous avez un ssd + disque dur par exemple). 

Une fois terminé, vous pouvez fermer l'installateur Java.

# Installer un launcher Minecraft 
## Préambule
Minecraft ne se lance pas tout seul, il faut un "Launcher" un launcher est une application simple permettant de choisir les paramètres java, et la version de minecraft.

## Téléchargement Launcher
Pour les comptes Minecraft payés, je recommande [Prism](https://prismlauncher.org/download/) (basé sur MultiMC avec pleins de petits bons ajouts, **mais** oblige un compte pour lancer une instance minecraft)

Pour les comptes non payés, je recommande [Prism Cracké](https://github.com/Diegiwg/PrismLauncher-Cracked/releases/tag/7.1) (une version modifiée de prism, qui désactive les restrictions de compte) 
Pour télécharger, prenez la version Windows (Vous êtes sous windows (valentin, le seul sous linux, empreinte un compte payé)) MinGW (le compilateur) x64 (l'architecture compilée pour) Setup (on souhaite l'installer)

## Installation Launcher
Les deux installateurs sont les mêmes, donc les étapes sont les mêmes.
Tout d'abord, au deuxième écran, cocher **toutes** les cases
![[Pasted image 20231031144938.png]]
puis on vous proposera l'emplacement d'installation (si vous avez ssd + hdd, vous voudrez peut-être changer l'emplacement).

À la fin, ouvrez prism, l'installation n'est pas finie.
![[Pasted image 20231031145110.png]]

Le premier écran demande la langue choisie, sélectionner `Français`.
Le deuxième écran demande la version par défaut de minecraft, sélectionnez impérativement la version 17.0.X (suivant votre installation).
Pour l'allocation de mémoire, mettez 1024 dans les deux cases (on force java à utiliser au minimum 1GO, car java gère la RAM comme un pied et est lent lorsqu'il doit allouer plus de ram une fois le programme lancé)
![[Pasted image 20231031145519.png]]
La troisième (et dernière) et dernière page est la page de customisation, à vous de choisir ce que vous aimez le plus.

## Téléchargement Instance minecraft
Puisque certains sont sur des PC avec peu de performaces, on va utiliser une version non officielle (moddée) avec ajouts qui devraient permettre jusqu'à 3 fois les performance natives.

Dans prism, en haut à gauche, cliquez sur `Ajouter une instance`
![[Pasted image 20231031145913.png]]
Puis choisissez `Modrinth` à gauche (Modrinth est un catalogue de Modpack (des versions moddées de minecraft)) et choisisez `Simply Optimized` (si vous avez un plutôt bon PC, vous pouvez choisir `Fabulously optimized`)
![[Pasted image 20231031150107.png]]
Cependant, avant de cliquer sur `OK`, on a besoin de changer de version, dans le coin en bas à droite, sélectionner la version `1.20.1-096` puis cliquez sur `OK`
![[Pasted image 20231031150204.png]]
## Lancer Minecraft
Vous avez téléchargé les ajouts, pas encore minecraft, pour le télécharger, il faut lancer minecraft, pour ce faire, cliquez sur lancer.
![[Pasted image 20231031150514.png]]
Après, cliquez sur `Yes` (Prism vous avertit qu'il ne connait pas de compte ni de nom)
![[Pasted image 20231031150729.png]]
Par la suite, si vous avez un compte minecraft, cliquez sur `Ajouter un compte Microsoft` et suivez les étapes, sinon, cliquez sur `Ajouter un compte hors ligne` à droite et mettez votre pseudo.
![[Pasted image 20231031150841.png]]
Ensuite, fermer la page de compte et lancer l'instance, si elle ne se lance pas toute seule, vous devriez avoir une fenêtre de téléchargement au premier démarrage.
![[Pasted image 20231031151023.png]]
Le premier lancement est long, c'est normal.

Si vous avez ce message ![[Pasted image 20231031154108.png]]
vous n'avez pas sélectionnez java 17 précédemment. Allez dans Paramètres à gauche, sélectionnez `Installation Java` et `détecter automatiquement` puis sélectionner la version 17.0.X (prism veut la version 17.X exactement, une version supérieur ne fonctionnera pas sans cocher la case `Passer les vérifications de compatibilités de Java`)
![[Pasted image 20231031154327.png]]

Si vous avez un message vous disant que vos drivers graphiques ne sont pas à jour, fermer Minecraft, et mettez-les à jours
![[Pasted image 20231031151445.png]]
Pour vérifier si votre PC tient Minecraft, allez sur un serveur et regardez vos FPS, pour se faire 2 façons : 
1. Si vous avez un overlay, c'est marqué dedans (non mon ryzen n'a pas que 4 cœurs, c'est une VM, avec GPU et que 16GO de ram)
	![[Pasted image 20231031152230.png]]
2. Appuyez sur F3 et tout en haut à gauche, vous aurez vos FPS (j'ai commenté les choses qui pourraient être utile en fond vert, le reste sont utiles, mais pas pour nous)
	![[Pasted image 20231031153156.png]]
Vous pouvez fermer Minecraft

Si vous n'avez pas beaucoup de FPS et que vous avez au moins 4GO de RAM libre (regarder dans votre gestionnaire de tâche) (Attention pour les SLAM, vous aurez un serveur à faire tourner en même temps, ce dernier prend au moins 4GO de ram), vous pouvez allouer plus de RAM à l'instance Minecraft.

Pour ce faire, cliquez sur modifier
![[Pasted image 20231031154646.png]]
puis `Paramètres`, cocher `Mémoire` et ajuster là les deux sections à un multiple de 2 (recommandés 1024 ; 2048 ; 4096 plus ne servira que lorsque vous jouez avec beaucoup de mod (donc si vous avez 86go de ram, et un modpack lourd, oui, vous pouvez allouer 64 GO à Minecraft… je parle d'expérience hein))
![[Pasted image 20231031155057.png]]
![[Pasted image 20231031155023.png]]
# SLAM
Cette section est dédié aux outils que les SLAM vont devoir installer

## Maven
Java est un langage compilé (bon… ce n'est pas réellement le cas, mais pour notre utilisation, on va dire que si) Le compilateur que l'on va utiliser est Maven, il permet d'utiliser des librairies d'internet et est simple à comprendre et utiliser.

### Téléchargement
Vous devez tout d'abord télécharger une archive avec les exécutables maven, allez sur [la page de téléchargement](https://maven.apache.org/download.cgi) et dans le tableau, cliquez le lien à l'intersection `Link` et `Binary zip archive`.

### Installation
Ouvrez ensuite le .zip et clissez le dossier `apache-maven-3.9.X` où vous voulez (ssd / hdd, choisissez), j'ai choisi `C:\Program Files\` (Attention les droits administrateurs sont nécessaires pour écrire dans `C:\Program Files\`)
![[Pasted image 20231031160649.png]]

Une fois fait, ouvrez le dossier copié et allez dans le sous dossier `bin` et copier le chemin (dans la barre d’adresse)
![[Pasted image 20231031160952.png]]
ensuite, ouvrez le menu windows et tapez `env` ça devrait vous proposez `Modifier les variables d'environnement système`![[Pasted image 20231031161140.png]]
ensuite, sélectionnez `Variables d'environnement...` en bas
![[Pasted image 20231031161251.png]]
après, dans la section `Variables système` trouvez la variable `Path` et cliquez sur modifier (toujours dans la section `variables systèmes`)
![[Pasted image 20231031161419.png]]
ensuite, cliquez sur nouveau et coller votre chemin précédemment copié
![[Pasted image 20231031161518.png]]
puis cliquez sur `OK` sur toutes les fenêtres ouvertes.
Pour vérifier si maven est installé, ouvrez une console (`win` + r, tapez `cmd` et OK) et tapez `mvn` Vous devriez avoir une erreur de compilation comme celle-là : 
![[Pasted image 20231031161739.png]]
## IntelliJ IDEA
Notre IDE java va être IntelliJ IDEA, car il a beaucoup de fonctionnalité très utile.
### Téléchargement
Il existe deux versions d'IDEA : Ultimate et Community, l'un est pour les entreprises / professionnels et l'autres est pour Monsieur tout le monde.
- Ultimate coûte 599/utilisateur/an.
- Community est gratuit.
Puisqu'on n'a pas envie de perdre un rein pour apprendre, on va utiliser la version community qui est disponible [ici](https://download.jetbrains.com/idea/ideaIC-2023.2.4.exe)

### Installation
exécuter, droit d'admin, `next`, (emplacement du programme, ssd + hdd voudront peut-être changer l'emplacement) `next`, **cochez TOUT** `next`, `install`, lancez Intellij IDEA, acceptez les CGU, n'envoyez pas vos données d'utilisations et allez dans l'onglet `Plugins`, cherchez `minecraft` et cliquez sur `Install` (ça vous demandera d'accepter encore des CGU)
![[Pasted image 20231031163001.png]]
une fois l'installation finie, le bouton deviendra `Restart IDE`, faites et TADA, vous avez installé IntelliJ IDEA

## Serveur Minecraft
Pour modifier un serveur Minecraft, il faut un dit serveur, je vous en ai fait un tout prêt disponible [ici](https://www.mediafire.com/file/ny9bvhmjzae2uxa/Serveur_DEV_SIO.zip/file)
Il n'y a pas "d'installation" à proprement parler pour vous, j'ai tout fait, vous avez juste qu'à l'extraire où vous voulez.
![[Pasted image 20231031163534.png]]
Pour lancer le serveur, lancez `Démarreur.bat` (vous pouvez regarder ce qu'il y a dedans si vous avez des doutes), ça prendra du temps lors du premier démarrage (téléchargement des librairies minecraft), ça devrait vous ouvrir une fenêtre avec les infos serveur, vous saurez que votre serveur a fini de se lancer, lorsque vous verrez `Done (<temps>)! For help, type "help"` dans les logs
![[Pasted image 20231031164217.png]]
Pour rejoindre ce serveur, dans minecraft, allez dans `Multiplayer`, `Add Server` dans `Server Address` mettez `localhost`, cliquez sur `Done`
![[Pasted image 20231031164357.png]]
Ensuite, cliquez soit sur `Join Server`, la tête de flèche, la touche entrée ou double-cliquez dessus.
Vous devriez apparaître dans l'eau, la génération a fait que
![[Pasted image 20231031165853.png]]
Pour vous mettre les droits d'administrateur, dans la console tapez `op <votre pseudo> `

# SISR