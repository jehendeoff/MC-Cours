# Objectif
> créer/modifier un plugin et modifier le comportement d'un fruit

# Introduction
Vous avez vue comment créer une commande, envoyer des messages et comment trouver les méthodes dans une classe.
Maintenant, vous allez voir comment déclarer votre classe, comment lire et interpréter la documentation de spigot, comment récupérer un événement, ajouter des conditions par-dessus votre événement et comment ajouter certains effets à votre joueur.
En gros, vous allez devoir récupérer quand le joueur mange, regarder lequel, c'est, modifier le comportement. 

Voici ce que je veux que votre plugin face : quand je mange un `chorus fruit`, ça donne :
- un effet de résistance
- un item
- droit de voler pendant 20 seconde (ne pas chercher longtemps, c'est chiant, le corriger arrivera)
Si le bloque sous le joueur est de la Grass (herbe), j'aimerais qu'il reçoit un effet de ralentissement (Slowness) en plus

# Créez votre classe servant pour le(s) événement(s) 
Oui, "le(s)", contrairement aux commandes, il est assez facile de mettre plusieurs événements dans une seule classe !

**Pour tous les exemples que je vais utiliser, le code ne sera le code que vous devrez avoir !** (ce code vient d'un possible futur exercice)

Tout d'abord, vous allez devoir créer une nouvelle classe, vous pourrez la nommer comme vous voulez, mais puisqu'elle concernera un événement, il vous faudra mettre "Event" dans son nom (par convention). (ma clase sera `FishEvent`)

Votre classe devra implémenter la classe `Listener` (`org.bukkit.event.Listener`)

Vous aurez donc une ligne qui devrait ressembler à :
```java
public class FishEvent implements Listener
```

ensuite vous devrez 
# Écouter les événements
Pour ça vous aurez besoins de dire au serveur quelle est votre classe qui écoute un (ou plus / tous) événements.

Pour ça, dans votre classe principale, vous aurez besoins d'ajouter une ligne, la voici : 
```java
Bukkit.getPluginManager().registerEvents(new FishEvent(), this);
```

Je vais vous la décortiquer : 
```java
(org.bukkit.Bukkit)Bukkit.getPluginManager() // ça récupère le gestionnaire de plugin, c'est cette classe avec laquelle on doit communiquer dès que notre plugin a besoin de faire quelque chose qui est un tout petit peut complexe (asynchrone, events, etc)

/* La méthode */ registerEvent /* prend deux arguments en compte : une classe Listener, et une classe Javaplugin */
new FishEvent() // est une classe qui implémente la classe Listener, donc cet argument serait le premier
this // réfère à votre classe principale, qui doit étendre la classe JavaPlugin, donc ce sera le second argument

//Vous n'avez pas besoins de savoir quelle est la différence entre extends et implements, pour vous, c'est les même, mais quand vous faites un extends, vous devez importer les méthodes
```

Une fois que vous avez fait ça, vous allez devoir 
# Chercher l'événement voulut
Pour ça, vous aurez besoin de la documentation de Spigot. 
Les documentations java sont souvent nommées des JavaDoc (c'est un format plus qu'un nom, mais c'est utilisé partout, car très simple à générer)

(La version de la javadoc n'a pas d'importance, la dernière version n'a pas trop de delta avec la version que vous avez)

Vous aurez donc besoins besoin de chercher la `javadoc spigot` sur votre moteur de recherche favoris, vous devriez trouver un site un peu austère qui ressemble à : 
![Image](/Images/Pasted_image_20231129164723.png)
Non, le CSS a bien chargé, et la javadoc ressemble bien à ça, mais ne prenez pas peur ! Il est très simple de naviguer grâce à une merveille de notre temps : la barre de recherche en haut à droite de la page, sauf si vous êtes maso et que vous voulez.

En l'occurence, on veut voir la liste des Event, donc on va chercher Event, et on aura 
![Image](/Images/Pasted_image_20231129195248.png)
Si on clique dessus ou appuie sur tab, on aura les différentes catégories d'événements (oui, ils ont été gentils et les ont classés)
![Image](/Images/Pasted_image_20231129195403.png)
En l'occurrence, on veut un événement qui se déclenche quand un joueur mange, donc ça devrait se trouver dans la catégorie `org.bukkit.event.player`, donc je vais cliquer dessus et obtenir une liste trop grande pour que je mette une capture d'écran.
Vu que je n'ai pas envie de m'amuser à regarder tous les event, je vais simplement faire un `ctrl + f` et chercher `eat` ... Malheureusement, vous ne trouverez rien, c'est à cause de ça que je n'ai pas directement cherché `eat` dans la barre de recherche, car en cherchant dans la barre, je n'ai pas trouvé d'event (les événements sont forcément dans le package org.bukkit.event)
![Image](/Images/Pasted_image_20231129195940.png)
(`org.bukkit.event.entity.entityRegainHealthEvent` est l'événement, `RegainReason.EATING` est un enum (c'est un type java) / une variable)

Donc vue que je ne trouve rien pour `eat`, je vais chercher `food` dans la page et ... oh, bah on dirait que ça a trouvé un événement qui se déclenche à chaque fois qu'un joueur a fini de consommer un item : 
![Image](/Images/Pasted_image_20231129200237.png)
J'ai donc trouvé l'événement que je dois utiliser, je dois donc
# Écouter pour l'événement
tout d'abord, retourner dans votre classe d'événement, et ajouter 
```java
@EventHandler  
public void PlayerFish(@NotNull PlayerFishEvent event) { 
}
```

Cette fonction (oui, c'est une fonction) sera appelé à chaque fois que l'événement `PlayerFishEvent` sera appelé (vous voudrez peut-être y changer avec l'événement approprié). Mais qu'est-ce que tout le charabia veut dire ? 
```java
@EventHandler // cette ligne dit à java que cette fonction sera à appelé suivant un certain event

public void // ces doux mots veulent dire que : 1. c'est une fonction publique, tout le monde peut l'utiliser 2. Cette fonctione ne retournera aucune valeur

PlayerFish // Ce mot est le nom de la fonction, dans un événement, le nom de la fonction n'est pas important, vous pouvez mettre ce que vous voulez

@NotNull // ce mot veut simplement dire que si spigot tente de vous la mettre à l'enver, ça va pas marcher

PlayerFishEvent // Ceci est la classe de l'événement, c'est sûrement le mot le plus important de toute la fonction avec public void

event // ceci est le nom de la variable que spigot va vous donner, contenant les informations à propos de l'événement
```

Mais d'ailleurs, quelles seront les informations que spigot va me donner à propos de mon événement ? Bah si vous avez Intellij Idea, vous avez juste besoin de faire `event.` et Intellij vous donnera toutes les méthodes disponibles pour cet événement 
![Image](/Images/Pasted_image_20231129201040.png)

Mais si vous êtes pommé, la documentation de spigot est complète et vous dira tout à propos de l'événement en question 
Pour l'événement `PlayerFishEvent` voici [la doc](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerFishEvent.html) (ou chercher `playerFishEvent` dans la doc, ça fonctionnera aussi)

Dans tout le tas d'information, les premières vous seront inutiles, vous voudrez les `Method Summary` (Sommaire des Méthodes) et `Method Details` (Détails des Méthodes), donc pour reprendre Intellij, je cherche la méthode `getCaught`, qui devrait renvoyer une `Entity` et bingo 
![Image](/Images/Pasted_image_20231129201502.png)
Spigot me donnera même une petite description de l'événement, comme ils ont été gentils quand même.

# à vous de jouer
Donc pour résumer, vous savez comment créer uen classe pour le(s) événement(s), déclarer un événement, et écouter un événement, maintenant à vous de chercher, sachant que dans 15~ min, une première aide sera disponible, si j'y pense

# Projets supplémentaires pour les plus rapides
- faire en sorte que l'on en puisse pas suffoquer
- désactiver l'explosion des creeper
- faire en sorte que la faim ne descende pas
