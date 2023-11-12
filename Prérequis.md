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
![Image](https://github.com/jehendeoff/MC-Cours/blob/main/Images/Pasted image 20231031142921.png?raw=true)
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
![Image](https://github.com/jehendeoff/MC-Cours/blob/main/Images/Pasted image 20231031144938.png?raw=true)
puis on vous proposera l'emplacement d'installation (si vous avez ssd + hdd, vous voudrez peut-être changer l'emplacement).

À la fin, ouvrez prism, l'installation n'est pas finie.
![Image](https://github.com/jehendeoff/MC-Cours/blob/main/Images/Pasted image 20231031145110.png?raw=true)

Le premier écran demande la langue choisie, sélectionner `Français`.
Le deuxième écran demande la version par défaut de minecraft, sélectionnez impérativement la version 17.0.X (suivant votre installation).
Pour l'allocation de mémoire, mettez 1024 dans les deux cases (on force java à utiliser au minimum 1GO, car java gère la RAM comme un pied et est lent lorsqu'il doit allouer plus de ram une fois le programme lancé)
![Image](https://github.com/jehendeoff/MC-Cours/blob/main/Images/Pasted image 20231031145519.png?raw=true)
La troisième (et dernière) et dernière page est la page de customisation, à vous de choisir ce que vous aimez le plus.

## Téléchargement Instance minecraft
Puisque certains sont sur des PC avec peu de performaces, on va utiliser une version non officielle (moddée) avec ajouts qui devraient permettre jusqu'à 3 fois les performance natives.

Dans prism, en haut à gauche, cliquez sur `Ajouter une instance`
![Image](https://github.com/jehendeoff/MC-Cours/blob/main/Images/Pasted image 20231031145913.png?raw=true)
Puis choisissez `Modrinth` à gauche (Modrinth est un catalogue de Modpack (des versions moddées de minecraft)) et choisisez `Simply Optimized` (si vous avez un plutôt bon PC, vous pouvez choisir `Fabulously optimized`)
![Image](https://github.com/jehendeoff/MC-Cours/blob/main/Images/Pasted image 20231031150107.png?raw=true)
Cependant, avant de cliquer sur `OK`, on a besoin de changer de version, dans le coin en bas à droite, sélectionner la version `1.20.1-096` puis cliquez sur `OK`
![Image](https://github.com/jehendeoff/MC-Cours/blob/main/Images/Pasted image 20231031150204.png?raw=true)
## Lancer Minecraft
Vous avez téléchargé les ajouts, pas encore minecraft, pour le télécharger, il faut lancer minecraft, pour ce faire, cliquez sur lancer.
![Image](https://github.com/jehendeoff/MC-Cours/blob/main/Images/Pasted image 20231031150514.png?raw=true)
Après, cliquez sur `Yes` (Prism vous avertit qu'il ne connait pas de compte ni de nom)
![Image](https://github.com/jehendeoff/MC-Cours/blob/main/Images/Pasted image 20231031150729.png?raw=true)
Par la suite, si vous avez un compte minecraft, cliquez sur `Ajouter un compte Microsoft` et suivez les étapes, sinon, cliquez sur `Ajouter un compte hors ligne` à droite et mettez votre pseudo.
![Image](https://github.com/jehendeoff/MC-Cours/blob/main/Images/Pasted image 20231031150841.png?raw=true)
Ensuite, fermer la page de compte et lancer l'instance, si elle ne se lance pas toute seule, vous devriez avoir une fenêtre de téléchargement au premier démarrage.
![Image](https://github.com/jehendeoff/MC-Cours/blob/main/Images/Pasted image 20231031151023.png?raw=true)
Le premier lancement est long, c'est normal.

Si vous avez ce message ![Image](https://github.com/jehendeoff/MC-Cours/blob/main/Images/Pasted image 20231031154108.png?raw=true)
vous n'avez pas sélectionnez java 17 précédemment. Allez dans Paramètres à gauche, sélectionnez `Installation Java` et `détecter automatiquement` puis sélectionner la version 17.0.X (prism veut la version 17.X exactement, une version supérieur ne fonctionnera pas sans cocher la case `Passer les vérifications de compatibilités de Java`)
![Image](https://github.com/jehendeoff/MC-Cours/blob/main/Images/Pasted image 20231031154327.png?raw=true)

Si vous avez un message vous disant que vos drivers graphiques ne sont pas à jour, fermer Minecraft, et mettez-les à jours
![Image](https://github.com/jehendeoff/MC-Cours/blob/main/Images/Pasted image 20231031151445.png?raw=true)
Pour vérifier si votre PC tient Minecraft, allez sur un serveur et regardez vos FPS, pour se faire 2 façons : 
1. Si vous avez un overlay, c'est marqué dedans (non mon ryzen n'a pas que 4 cœurs, c'est une VM, avec GPU et que 16GO de ram)
	![Image](https://github.com/jehendeoff/MC-Cours/blob/main/Images/Pasted image 20231031152230.png?raw=true)
2. Appuyez sur F3 et tout en haut à gauche, vous aurez vos FPS (j'ai commenté les choses qui pourraient être utile en fond vert, le reste sont utiles, mais pas pour nous)
	![Image](https://github.com/jehendeoff/MC-Cours/blob/main/Images/Pasted image 20231031153156.png?raw=true)
Vous pouvez fermer Minecraft

Si vous n'avez pas beaucoup de FPS et que vous avez au moins 4GO de RAM libre (regarder dans votre gestionnaire de tâche) (Attention pour les SLAM, vous aurez un serveur à faire tourner en même temps, ce dernier prend au moins 4GO de ram), vous pouvez allouer plus de RAM à l'instance Minecraft.

Pour ce faire, cliquez sur modifier
![Image](https://github.com/jehendeoff/MC-Cours/blob/main/Images/Pasted image 20231031154646.png?raw=true)
puis `Paramètres`, cocher `Mémoire` et ajuster là les deux sections à un multiple de 2 (recommandés 1024 ; 2048 ; 4096 plus ne servira que lorsque vous jouez avec beaucoup de mod (donc si vous avez 86go de ram, et un modpack lourd, oui, vous pouvez allouer 64 GO à Minecraft… je parle d'expérience hein))
![Image](https://github.com/jehendeoff/MC-Cours/blob/main/Images/Pasted image 20231031155057.png?raw=true)
![Image](https://github.com/jehendeoff/MC-Cours/blob/main/Images/Pasted image 20231031155023.png?raw=true)
# SLAM
Cette section est dédié aux outils que les SLAM vont devoir installer

## Maven
Java est un langage compilé (bon… ce n'est pas réellement le cas, mais pour notre utilisation, on va dire que si) Le compilateur que l'on va utiliser est Maven, il permet d'utiliser des librairies d'internet et est simple à comprendre et utiliser.

### Téléchargement
Vous devez tout d'abord télécharger une archive avec les exécutables maven, allez sur [la page de téléchargement](https://maven.apache.org/download.cgi) et dans le tableau, cliquez le lien à l'intersection `Link` et `Binary zip archive`.

### Installation
Ouvrez ensuite le .zip et clissez le dossier `apache-maven-3.9.X` où vous voulez (ssd / hdd, choisissez), j'ai choisi `C:\Program Files\` (Attention les droits administrateurs sont nécessaires pour écrire dans `C:\Program Files\`)
![Image](https://github.com/jehendeoff/MC-Cours/blob/main/Images/Pasted image 20231031160649.png?raw=true)

Une fois fait, ouvrez le dossier copié et allez dans le sous dossier `bin` et copier le chemin (dans la barre d’adresse)
![Image](https://github.com/jehendeoff/MC-Cours/blob/main/Images/Pasted image 20231031160952.png?raw=true)
ensuite, ouvrez le menu windows et tapez `env` ça devrait vous proposez `Modifier les variables d'environnement système`![Image](https://github.com/jehendeoff/MC-Cours/blob/main/Images/Pasted image 20231031161140.png?raw=true)
ensuite, sélectionnez `Variables d'environnement...` en bas
![Image](https://github.com/jehendeoff/MC-Cours/blob/main/Images/Pasted image 20231031161251.png?raw=true)
après, dans la section `Variables système` trouvez la variable `Path` et cliquez sur modifier (toujours dans la section `variables systèmes`)
![Image](https://github.com/jehendeoff/MC-Cours/blob/main/Images/Pasted image 20231031161419.png?raw=true)
ensuite, cliquez sur nouveau et coller votre chemin précédemment copié
![Image](https://github.com/jehendeoff/MC-Cours/blob/main/Images/Pasted image 20231031161518.png?raw=true)
puis cliquez sur `OK` sur toutes les fenêtres ouvertes.
Pour vérifier si maven est installé, ouvrez une console (`win` + r, tapez `cmd` et OK) et tapez `mvn` Vous devriez avoir une erreur de compilation comme celle-là : 
![Image](https://github.com/jehendeoff/MC-Cours/blob/main/Images/Pasted image 20231031161739.png?raw=true)
## IntelliJ IDEA
Notre IDE java va être IntelliJ IDEA, car il a beaucoup de fonctionnalité très utile.
### Téléchargement
Il existe deux versions d'IDEA : Ultimate et Community, l'un est pour les entreprises / professionnels et l'autres est pour Monsieur tout le monde.
- Ultimate coûte 599/utilisateur/an.
- Community est gratuit.
Puisqu'on n'a pas envie de perdre un rein pour apprendre, on va utiliser la version community qui est disponible [ici](https://download.jetbrains.com/idea/ideaIC-2023.2.4.exe)

### Installation
exécuter, droit d'admin, `next`, (emplacement du programme, ssd + hdd voudront peut-être changer l'emplacement) `next`, **cochez TOUT** `next`, `install`, lancez Intellij IDEA, acceptez les CGU, n'envoyez pas vos données d'utilisations et allez dans l'onglet `Plugins`, cherchez `minecraft` et cliquez sur `Install` (ça vous demandera d'accepter encore des CGU)
![Image](https://github.com/jehendeoff/MC-Cours/blob/main/Images/Pasted image 20231031163001.png?raw=true)
une fois l'installation finie, le bouton deviendra `Restart IDE`, faites et TADA, vous avez installé IntelliJ IDEA

## Serveur Minecraft
Pour modifier un serveur Minecraft, il faut un dit serveur, je vous en ai fait un tout prêt disponible [ici](https://www.mediafire.com/file/ny9bvhmjzae2uxa/Serveur_DEV_SIO.zip/file)
Il n'y a pas "d'installation" à proprement parler pour vous, j'ai tout fait, vous avez juste qu'à l'extraire où vous voulez.
![Image](https://github.com/jehendeoff/MC-Cours/blob/main/Images/Pasted image 20231031163534.png?raw=true)
Pour lancer le serveur, lancez `Démarreur.bat` (vous pouvez regarder ce qu'il y a dedans si vous avez des doutes), ça prendra du temps lors du premier démarrage (téléchargement des librairies minecraft), ça devrait vous ouvrir une fenêtre avec les infos serveur, vous saurez que votre serveur a fini de se lancer, lorsque vous verrez `Done (<temps>)! For help, type "help"` dans les logs
![Image](https://github.com/jehendeoff/MC-Cours/blob/main/Images/Pasted image 20231031164217.png?raw=true)
Pour rejoindre ce serveur, dans minecraft, allez dans `Multiplayer`, `Add Server` dans `Server Address` mettez `localhost`, cliquez sur `Done`
![Image](https://github.com/jehendeoff/MC-Cours/blob/main/Images/Pasted image 20231031164357.png?raw=true)
Ensuite, cliquez soit sur `Join Server`, la tête de flèche, la touche entrée ou double-cliquez dessus.
Vous devriez apparaître dans l'eau, la génération a fait que
![Image](https://github.com/jehendeoff/MC-Cours/blob/main/Images/Pasted image 20231031165853.png?raw=true)
Pour vous mettre les droits d'administrateur, dans la console tapez `op <votre pseudo> `

# SISR