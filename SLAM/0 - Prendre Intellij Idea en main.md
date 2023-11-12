Ceci n'est pas le fichier à lire juste après l'introduction globale, vous voulez [[Projets/MC Cours/SLAM/Lisez-moi|Lisez-moi]]

# Objectif
> Créez votre premier plugin, charger le dans un serveur, et voyez son effet

**J'ai épuré les instructions, ne sautez pas de lignes lors de votre lecture**

# Créer son projet
Tout d'abord lancez Intellij Idea, vous devriez avoir une interface ressemblant à ça : 
![[Pasted image 20231112134255.png]]

Pour commencer à coder, faites donc `New Project` et dans les options `Generators` à gauche, sélectionnez `Minecraft`, vous aurez toute une ribambelle d'options 
![[Pasted image 20231112134554.png]]

Tout d'abord, 
1. veuillez sélectionner `Plugin` dans `Plateform type`,
2. puis `Bukkit` dans `Platform`
3. ensuite `Paper` dans `Bukkit platform`
4. après, sélectionnez la version `1.20` dans `Minecraft version`
Toutes ces options définissent quel genre de modification nous allons faire (mods / plugins)

Ensuite, vous allez configurer le nom de votre plugin, sa classe principale (et son paquet)
![[Pasted image 20231112135107.png]]
Tout d'abord : 
1. dans la case `Name:` tout en haut, vous allez mettre le nom du **projet Java** (différent de celui du plugin)
2. plus bas, dans `Plugin Name:` vous allez mettre le nom du plugin (qui sera présenté au serveur)
3. *ne touchez pas à `Main Class:` ni à `Build System`*.
4. dans `Build System Properties > Group ID` vous allez mettre le nom du paquet, une norme est l'inverse de l'ordre de votre nom de domaine, exemple : Mon nom de domaine est `jehende.fr`, j'inverse l'ordre, ça me donne `fr.jehende`. Puisque vous n'avez pas de nom de domaine, vous allez utiliser `io.github.<votre pseudo github>` *(`<votre pseudo>.github.io` est un domaine que vous pouvez utiliser)*
Attention à ne pas confondre votre nom et votre pseudo / nom d'utilisateur, mon pseudo est `jehendeoff`.
![[Pasted image 20231112140013.png]]
*(pour faire simple, un paquet est un dossier, ça permet d'éviter que mon plugin remplace le code d'un autre plugin, ce qui se passerait si on n'utiliserait pas de paquet et qu'on a une classe du même nom)*
5. Vérifiez que le `JDK` est sur la version 17 (qu'importent les versions mineures) 

Vous avez Fini, vous pouvez lancer votre premier projet Java, cliquez sur `Create`.
Attendez qu'Intellij Idea charge, ça prend du temps.

# Découvrir
Une fois que vous avez un avion en papier bleu (le logo de PaperMC) en haut à gauche, Intellij idea a fini de charger :
![[Pasted image 20231112141624.png]]

Mais, où est mon code ? caché dans le menu déroulant du fameux avion en papier
![[Pasted image 20231112142042.png]]

Tout d'abord, nous allons voir le fichier le plus important : `plugin.yml`. Il permet de déclarer au serveur Minecraft (Bukkit, Spigot, Paper) quelle est la classe principale à charger au démarrage, pour quelle version de Minecraft le plugin a été créé, quelles commandes à attribuer et beaucoup plus d'autres choses, que nous n'allons pas utiliser, par manque de temps.
![[Pasted image 20231112142359.png]]

Maintenant, allons voir comment se présente notre classe principale :
![[Pasted image 20231112142758.png]]

# Votre premier plugin
> Vous allez devoir faire une commande, mais pas n'importe laquelle, une commande `/ping`
> 
> Tout d'abord, elle ne devra que renvoyer `Pong !` lorsque quelqu'un fait la commande
> 
> Puis, la commande ne devra qu'être utilisable par les joueurs (je ne veut pas que la commande puisse faire `/ping` (enfin, dans la console on ne met pas de `/` devant une commande, donc `ping` en réalité))
> 
> Ensuite, au lieu de `Pong !`, je veut que ça renvoie `<nom du joueur> !`
> 
> pour finir, j'aimerais que ça réponde `<ping numérique du joueur>ms de ping !`

<details>
<summary>Déclarer une commande</summary>

Pour déclarer une commande, Il vous faudra d'abord dire au serveur de vous réserver la commande dans le fichier `plugin.yml`.

Pour ce faire, il suffit d'ajouter : (l'autocomplétion devrait vous aider un peu)
<code>
```yaml
commands: 
	"commande sans le slash":
		usage: /<command> #mettez <command>, il ne faut pas y remplacer ici
```
</code>

Ça devrait ressembler à ça : 
![[Pasted image 20231112143958.png]]

Une fois que le serveur vous a réservé la commande, vous allez devoir l'utiliser, pour ça vous allez devoir créer une nouvelle classe, pour ce faire, faites un clique droit sur votre paquet principal, puis `New` et `Java Class`
![[Pasted image 20231112144151.png]]

Vous nommerez votre classe `PingCommand` ensuite faites `entré` (on essayera de toujours mettre des majuscules aux classes, des majuscules genre `onCommand` aux fonctions et des underscores pour les variables)
![[Pasted image 20231112144318.png]]

Vous aurez : 
![[Pasted image 20231112144431.png]]

Cependant, votre classe doit implémenter le `TabExecutor`, pour ça, à la ligne 3
```java
public class PingCommand {
```
Vous allez ajouter `implements TabExecutor` entre `PingCommand` et l'accolade ouverte. 

Idea vous criera dessus, car il ne connait pas `TabExecutor`, il faut l'important dans la classe, pour ça, survoler TabExecutor, il devrait vous proposer d'`Import class`, faites. 

Hors, il n'est toujours pas satisfait, une classe implémentant `TabExecutor` ne peut être vide. Survoler donc la ligne et chosissez `Implement methods` et cliquez sur `OK` (ne touchez à **rien**).
![[Pasted image 20231112144926.png]]

Vous devriez vous retrouver avec ça : 
<code>
```java
public class PingCommand implements TabExecutor {
    @Override
    public boolean onCommand(@NotNull CommandSender commandSender, @NotNull Command command, @NotNull String s, @NotNull String[] strings) {
        return false;
    }

    @Override
    public @Nullable List<String> onTabComplete(@NotNull CommandSender commandSender, @NotNull Command command, @NotNull String s, @NotNull String[] strings) {
        return null;
    }
}
```
</code>

Pour que ça soit plus simple à lire, je vous propose de changer, et de mettre ça : (j'ai sauté une ligne avant chaque `@NotNull` et changer le nom des variables)
<code>
```java
    @Override
public boolean onCommand(@NotNull CommandSender sender, 
						 @NotNull Command command, 
						 @NotNull String label, 
						 @NotNull String[] args) {
	return false; // nous renvoyons false quand la commande a mal été éxécuté, ou à échoué
}

@Override
public @Nullable List<String> onTabComplete(@NotNull CommandSender commandSender, 
											@NotNull Command command, 
											@NotNull String label, 
											@NotNull String[] args) {
	return null;
}
```
</code>

Votre commande est réservée, et sa classe est créee, le problème est que l'on ne l'a pas encore lié à la commande à la classe.

Pour se faire, dans votre classe principale, dans la fonction `OnEnable()`, ajoutez : (utilisez l'autocomplétion, ça importera la classe `PingCommand` automatiquement)
```java
this.getCommand("ping").setExecutor(new PingCommand());
```

Ce que cette ligne fait, simplement, est de dire au serveur, que pour toute commande "ping" exécuter, utiliser la classe `PingCommand`.

Vous devriez avoir : 
Apprendre_intellij
```java
package fr.jehende.apprendre_intellij; //Attention à changer cette ligne !

import org.bukkit.plugin.java.JavaPlugin;

public final class Apprendre_intellijidea extends JavaPlugin {
    @Override
    public void onEnable() {
        this.getCommand("ping").setExecutor(new PingCommand());

    }
    @Override
    public void onDisable() {
    }
}
```

PingCommand
<code>
```java
package fr.jehende.apprendre_intellij; //Attention à changer cette ligne !

import org.bukkit.command.Command;
import org.bukkit.command.CommandSender;
import org.bukkit.command.TabExecutor;
import org.jetbrains.annotations.NotNull;
import org.jetbrains.annotations.Nullable;

import java.util.List;

public class PingCommand implements TabExecutor {
    @Override
    public boolean onCommand(@NotNull CommandSender sender, 
                             @NotNull Command command, 
                             @NotNull String s, 
                             @NotNull String[] args) {
        return false;
    }

    @Override
    public @Nullable List<String> onTabComplete(@NotNull CommandSender commandSender, 
                                                @NotNull Command command, 
                                                @NotNull String s, 
                                                @NotNull String[] args) {
        return null;
    }
}

```
</code>
</details>

Désormais, tentez, vous-même, de faire en sorte que la commande renvoie "Pong !" à quiconque fait la commande. (n'y passez pas plus de 5 minutes)

<details>
<summary>Spoiler : répondre "Pong !"</summary>

Si vous êtes ici, c'est que vous ne savez pas comment faire en sorte que la commande réponde `Pong !` à quiconque exécute la commande.

Tout d'abord, il vous faudra modifier la fonction `onCommand` dans `PingCommand`, dedans, mettez : 
```java
sender.sendMessage("Pong !");
```
et changer 
```java
return false;
```
en 
```java
return true;
```

ce qui donne : 
```java
@Override
public boolean onCommand(@NotNull CommandSender sender,
						 @NotNull Command command,
						 @NotNull String s,
						 @NotNull String[] args) {
	sender.sendMessage("Pong !");
	return true;
}
```
</details>

<details>
<summary>Tester notre plugin</summary>

Pour tester notre plugin, nous aurons besoin de tout d'abord compiler notre plugin, qui ne devrait pas avoir d'erreur (n'est pas souligné en rouge).

Pour compiler notre plugin, nous allons cliquer sur la flèche verte en haut à gauche : 
![[Pasted image 20231112150848.png]]

Nous allons ignorer tout `WARNING` dans la console.
Si vous n'avez pas de soucis lors de la compilation, bravo, vous avez fait votre premier plugin. (vous pouvez cacher la terminale en survolant le côté droite de la console, pour cliquer sur l'icône `Réduire`)

Mais il est où du coup ? votre plugin compilé se situe dans le nouveau dossier orange `target` sous le doux nom de `Apprendre_intellij-1.0-SNAPSHOT.jar` (nous n'allons pas utiliser le `original`, car c'est plus pour du java pûr).
![[Pasted image 20231112151256.png]]

Mais je le mets où le plugin ? À part la réponse évidente, dans le dossier `plugins` du serveur Minecraft (qui contient déjà d'autres plugins, qui pourront vous être utile) (vous pouvez glisser votre plugin dans votre serveur)
![[Pasted image 20231112151533.png]]

Une fois fait, vous pouvez démarré votre serveur, s'il est déjà démarré, vous pouvez exécuter la commande `plugman load` et appuyez sur la touche tab puis entré, ça devrait sortir le fichier de votre plugin, si vous n'avez pas lignes rouges (autres qu'essentials) dans la console, bien joué, votre plugin n'a pas cassé le serveur !

Pour être sûr qu'il est chargé, faites la commande `plugins`:
![[Pasted image 20231112152327.png]]

Vous pouvez ensuite essayer votre plugin.

Si vous n'avez pas envie de redémarrer tout le serveur à chaque modification de votre plugin, après le remplacer dans le dossier plugin, vous pouvez exécuter la commande `plugman reload ` et appuyez sur tab, ça vous donnera la liste des plugins, tapez le nom de votre plugin et faites entrer : 
![[Pasted image 20231112152352.png]]
</details>

Désormais, tentez, vous-même, de faire en sorte qu'il ne réponde qu'au joueur. (n'y passez pas plus de 3 minutes, vous risquez de ne pas trouver)

<details>
<summary>Spoiler : bloquer la console</summary>

(n'oubliez pas l'autocomplétion pour que les classes soient automatiquement importés)

Ici c'est un peu plus compliqué, ce que nous allons faire, c'est regarder si la classe de `sender` fait partie de la classe `Player`, on peut utiliser la méthode `instanceof` pour le savoir
```java
sender instanceof Player //Player doit être importé ou autocomplétion (`org.bukkit.Entity`)
```

Si ça renvoie true, alors la classe sender contient la classe Player, on peut donc l'encapsuler et l'inverser, pour ensuite savoir si `sender` n'est pas un joueur, pour arrêter la commande avant qu'on envoie le message de ping.

L'inversion+encapsulation ressemble à 
```java
!(sender instanceof Player)
```

Le bloquage ressemble à 
```java
if (!(sender instanceof Player)){
	sender.sendMessage("Vous n'êtes pas un joueur !");
	return false;
}
```
</details>

Dorénavant, essayez, vous-même, de faire en sorte que ça réponde `</nom joueur> !`. (n'y passez pas plus de 10 minutes)

<details>
<summary>Spoiler : répondre `"nom du joueur" !`</summary>

La partie la plus compliquée ici est la Concaténation de chaîne de caractère en Java.
La façon la plus simple est simplement `String + String`, on peut aussi faire `String.concat(String)`, on peut utiliser une classe `StringBuilder`, `StringJoiner`, une `List` etc., la façon que je vais utiliser est le +

La seconde partie compliquée est de récupérer le joueur à partir du `Sender`, ici on fera un cast.
le cast sera simple : `Player p = (Player) sender;`

Si on combine tout, on devrait avoir : 
```java
@Override
public boolean onCommand(@NotNull CommandSender sender,
						 @NotNull Command command,
						 @NotNull String s,
						 @NotNull String[] args) {
	if (!(sender instanceof Player)){
		sender.sendMessage("Vous n'êtes pas un joueur !");
		return false;
	}
	Player p = (Player) sender;
	sender.sendMessage(p.getName() + " !");
	return true;
}
```
</details>

.