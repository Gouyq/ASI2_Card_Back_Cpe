# Groupe 1
#### GOUY Quentin | PROTIERE Axel | VEBER Vincent | VERGNON Corentin

# ASI2_Card_Back_Cpe
https://github.com/Gouyq/ASI2_Card_Back_Cpe

# ASI2_Card_Front_Cpe
https://github.com/Gouyq/ASI2_Card_Front_Cpe

# ASI2_Card_Node_Cpe
https://github.com/Gouyq/ASI2_Card_Node_Cpe

# Atelier I
## Phase A
### Partie 1.2.

Réaliser un tableau récapitulatif des bus de communication les plus répandus (avantage/ inconvénients).

| Bus de communication | Avantages | Inconvénients |
|--|--|--|
| Interface JMS (Java Message Service) | - Standard Java <br> - Permet d'envoyer et recevoir des messages de manière asynchrone <br> - Permet de s'interfacer avec d'autres applications <br> - Support des modèles publish-subscribe et point-to-point | - Obligation de s'appuyer sur une implémentation (ActiveMQ, RabbitMQ, OpenJMS, jBoss Messaging, etc.) <br> - Ne permet pas les échanges synchrones |
| SOAP (Simple Object Access Protocol), WSDL (Web Services Description Language) | - Permet de transmettre des messages structurés à travers l'implémentation de services web <br> - Forte description / structuration du WebService à travers le WSDL | - Assez lourd à mettre en place (WSDL) <br> - Couplage assez fort entre les applications (une modification de l'API demande une évolution côté client et serveur comparé à REST) <br> - Echanges en XML (assez lourd lui aussi comparé au JSON par exemple) |

Sources : https://fr.wikipedia.org/wiki/Enterprise_service_bus

## Phase B
### Partie 2.1.

Réaliser  un  tableau  comparatif  des  principaux  Framework  FrontEnd  existants dressant les 
avantages et inconvénients de chacun.

| Framework | Avantages | Inconvénients |
|--|--|--|
|  React.JS (bibliothèque et non framework) | - Mise à jour de l'interface sans avoir à récupérer les données ni une nouvelle vue <br> - Grandes performances et rapidité <br> - Manipulation du DOM <br> - Language JavaScript (facile à apprendre et à comprendre) <br> - "Framework" le plus populaire des trois | - Manque de documentation officielle <br> - Difficile à maitriser |
| Angular | - Grande documentation détaillée <br> - Orienté composants <br> - Modèle MVVM (laison de données bidirectionnelle) | - Nombreux problèmes de migrations entre les anciennes versions et celles plus récentes <br> - Syntaxe très complexe pour la première version d'Angular |
| Vue.JS | - Permet de créer des single-pages complexes <br> - Documentation détaillée <br> - Petite taille mais grande vitesse et flexibilité <br> - Facile à apprendre | - Manque de ressources et peu extensible <br> - Communauté restreinte (c'est le framework le plus récent des trois) |

Sources : https://esokia.com/fr/blog/angular-reactjs-vuejs-quelle-technologie-choisir-pour-votre-projet-digital

## Questions

- Qu’est ce que le CROSS ORIGIN  ? En quoi cela est-il dangereux  ?
	- C'est lorsqu'un utilisateur souhaite accéder à des ressources situées sur un serveur d'une autre origine que le site courant.
	- Cela peut être dangereux car la page peut appeler d'autres ressources (JavaScript, CSS, etc.) - qui peuvent être nuisibles - à l'insu de l'utilisateur.
- Comment REACTJS fait-il pour afficher rapidement les modifications sur les composants  ?
	- Il passe par des props ou des states pour détecter les changements et les propager.
- Quelle est la fonction essentielle de REACTJS  ?
	- Tout définir en tant que composants (tout devient réutilisable).
- Quelle est la fonction essentielle de FLUX  ?
	- Permettre de centraliser les actions liées à un changement et de les propager aux vues qui utilisent les stores. C'est le store qui contient toute la logique (quoi mettre à jour, comment le faire).
- Qu’est ce que REDUX ?
	- Similaire à FLUX (notions de store, d'actions, etc.) sauf qu'il n'y a qu'un seul store et la logique est détenue par le reducer.
- Qu’est ce que JMS ? Est-ce spécifique à Springboot ?
	- Il s'agit d'une interface standard Java (Java Message Service) pour envoyer et recevoir des messages asynchrones entre plusieurs composants.
	- Ce n'est donc pas spécifique à Springboot car c'est un standard Java.
- Quelles sont les différents modes de transmissions de JMS ?
	- Il y a deux systèmes : le système publish-subscribe et le système point-to-point. Dans le premier, des services s'inscrivent à un publisher et tous ceux inscrits recoivent le message. Dans le second système, le message est directement adressé à un composant précis.
- Quel est le mode de transmission activé par défaut dans activeMq ?
	- C'est le mode de transmission publish-subscribe qui est activé par défaut.
- Qu’est ce que activeMq ?
	- ActiveMQ est un message broker (agent de message) open source en Java et une implémentation de JMS (Java Message Service). Il s'agit donc d'un ESB (Entreprise Service Bus) qui permet la communication entre plusieurs entités.
- Quels avantages proposent un bus de communication vis-à-vis de requêtes http classiques ?
	- Dans le cas de ActiveMQ, on retrouvera les fonctionnalités suivantes :
		- Supporte de nombreux langages (Java, C, C++, C#, Ruby, Pelr, Python, PHP, etc.).
		- Supporte des fonctionnalités avancées comme les messages groupés (Message Groups), les destinations vituelles (Virtual Destinations (le consumer du message n'est pas forcément une seule machine physique mais peut rediriger vers plusieurs autres machines physiques)).
		- Desination Wildcards (permet de s'inscrire à des chemins "génériques" pour récupérer les messages entrants plutôt que de s'inscrire à chaque endpoint individuellement).
		- Composite Destinations (permet de publier à plusieurs destination à la fois un message en une seule opération logique).
		- Supporte Spring pour facilement s'intégrer avec des applications Spring.
		- Supporte le stockage persistent très rapide à travers JDBC (Java DataBase Connectivity) et un journal de haute performance (chaque opération est inscrite dans une base de données de manière très rapide et persistente).
		- Développé pour permettre le clustering de haute performance, et la communiation client-serveur ou peer-to-peer (chaque client est aussi un serveur).
		- Beaucoup d'autres fonctionnalités (test unitaires, API REST, Ajax, etc.).
		- Sources : https://activemq.apache.org/components/classic/
- Comment faire pour partager des modules Maven avec un partenaire extérieur ?
	- En isolant le code à partager dans son propre module Maven, en le compilant et en partageant le .jar généré. Le projet extérieur devra rajouter le .jar et modifier son pom.xml pour intégrer ce nouveau module.
	- Sources : https://stackoverflow.com/questions/3390346/how-do-you-use-maven-to-share-source-code-for-two-projects
- Comment faire pour exporter un composant REACTJS ?
	- En utilisant la commande suivante à la fin du fichier .js : `export default NAME` (NAME étant le nom de la classe / de la fonction). On l'importera alors à l'aide de la commande `import NAME from PATH`.
	- Sources : https://www.geeksforgeeks.org/reactjs-importing-exporting/
- Quel est le pré-requis pour Springboot afin de pouvoir convertir automatiquement le message reçu 
dans un bus de communication en objet ?
	- TODO
- Comment est réalisée la traduction des messages reçus (bus de communication ou request http) en objet Java ? Quelles sont les prérequis ? Est-ce toujours possible ?
	- On peut utiliser la classe Java SimpleMessageConverter (https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/messaging/converter/SimpleMessageConverter.html) mais il faut s'assurer que le message reçu correspond à la classe cible.
- Quelles sont les fonctionnalités des différentes annotations en Springboot ?
	- @EnableJpaRepositories
		- Permet d'utiliser des repositories JPA (ce qui permet de gérer les données relationnelles dans une application Java (de faire le lien (accès, stockage, persistence, etc.) entre les classes Java et les objets stockés dans la base de données). Attention, il faut aussi rajouter l'annotation `@Configuration` pour que cette annotation fonctionne. On peut d'ailleurs utiliser le paramètre `basePackages` pour définir un package "racine" dans lequel chercher.
		- Sources : https://www.baeldung.com/spring-data-annotations
	- @EntityScan
		- Les "entities" sont les classes annotées avec `@Entity` uniquement.
		- On utilisera l'annotation `@EntityScan("package")` pour spécifier le chemin des ces classes si elles ne sont pas placées dans le package principal de l'application ou dans ses sous-packages.
		- Sources : https://www.baeldung.com/spring-entityscan-vs-componentscan
	- @ComponentScan
		- Les "components" sont les classes annotées avec `@Controller`, `@Service`, `@Repository`, `@Component` ou encore `@Bean`.
		- D'une manière similaire à `@EntityScan`, l'annotation `@ComponentScan` permet de spécifier le package dans lequel chercher les classes avec les annotations précédentes. En revanche, on pourra utiliser cette annotation sans paramètre si l'on veut scanner le package ou les sous-packages courants.
		- Sources : https://www.baeldung.com/spring-entityscan-vs-componentscan
	
