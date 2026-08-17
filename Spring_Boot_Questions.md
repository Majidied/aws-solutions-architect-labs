# Spring Boot – Questions d'entretien

## Concepts fondamentaux

### Question : Qu'est-ce que Spring Boot ?

**Réponse :** Spring Boot est un projet de l'écosystème Spring qui permet de créer rapidement des applications Spring autonomes (stand-alone), souvent des microservices, avec peu de configuration. Il fournit :
- L'auto-configuration
- Des dépendances "starters"
- Un serveur embarqué (Tomcat/Jetty/Undertow) pour lancer l'app "comme un simple main()"

---

### Question : Quelles fonctionnalités rendent Spring Boot différent ?

**Réponse :**
- **Auto-configuration** : configure automatiquement l'application selon les dépendances présentes
- **Starters** : dépendances prêtes à l'emploi (ex. spring-boot-starter-web)
- **Serveur embarqué** : exécutable sans déploiement externe (Tomcat/Jetty…)
- **Actuator** : endpoints de monitoring (health, metrics…)
- **Configuration externalisée** : application.properties / application.yml, profils, variables d'environnement
- **Très peu (voire pas) de XML** : configuration via annotations et conventions

---

## Niveau débutant

### Question : Quels sont les avantages de Spring Boot ?

**Réponse :** 
- Développement plus rapide
- Productivité accrue
- Configuration minimale
- Démarrage simple (stand-alone)
- Intégration facilitée (starters)
- Fonctionnalités "production-ready" (monitoring via Actuator)

---

### Question : Quels sont les composants clés de Spring Boot ?

**Réponse :**
- Auto-configuration
- Spring Boot CLI
- Starter POMs
- Spring Boot Actuator

---

### Question : Pourquoi choisir Spring Boot plutôt que Spring "classique" ?

**Réponse :** Spring Boot ajoute :
- Starters + gestion de versions
- Auto-configuration
- Scanning simplifié
- Serveur embarqué
- Configuration externalisée
- Actuator (observabilité)

Il réduit fortement le temps de setup.

---

### Question : Donne des exemples de "starter dependencies" courants.

**Réponse :**
- `spring-boot-starter-web`
- `spring-boot-starter-data-jpa`
- `spring-boot-starter-security`
- `spring-boot-starter-test`
- `spring-boot-starter-mail`
- `spring-boot-starter-thymeleaf`

---

### Question : Comment Spring Boot fonctionne-t-il ?

**Réponse :** Il démarre via une classe principale annotée `@SpringBootApplication`, puis Spring :
1. Charge le contexte
2. Scanne les composants
3. Applique l'auto-configuration selon le classpath et les propriétés

---

### Question : Que fait @SpringBootApplication en interne ?

**Réponse :** C'est un raccourci équivalent à :
- `@Configuration`
- `@EnableAutoConfiguration`
- `@ComponentScan`

---

### Question : À quoi sert @ComponentScan ?

**Réponse :** À scanner les packages pour détecter et enregistrer les beans (classes annotées `@Component`, `@Service`, `@Repository`, `@Controller`, etc.).

---

### Question : Comment démarre une application Spring Boot ?

**Réponse :** Avec une méthode `main()` qui appelle `SpringApplication.run(...)`

---

### Question : C'est quoi Spring Boot CLI et ses avantages ?

**Réponse :** Une interface en ligne de commande (souvent avec Groovy) pour prototyper rapidement sans boilerplate.

---

### Question : Qu'est-ce que Spring Initializr ?

**Réponse :** Un générateur de projet (structure + dépendances Maven/Gradle) pour démarrer rapidement un projet Spring Boot.

---

### Question : Que sont les "starter dependencies" ?

**Réponse :** Des dépendances Maven/Gradle "packs" qui tirent automatiquement les dépendances transverses nécessaires à une fonctionnalité (web, JPA, sécurité, etc.).

---

## Niveau intermédiaire

### Question : Quelle est la différence entre application.properties et application.yml ?

**Réponse :** 
- **application.yml** : plus lisible et hiérarchique
- **application.properties** : format clé/valeur simple

Les deux servent à configurer l'application.

---

### Question : Qu'est-ce que @Autowired ?

**Réponse :** C'est une annotation qui permet à Spring d'injecter automatiquement une dépendance (bean) dans une classe.

---

### Question : Quelle est la meilleure injection : constructeur ou champ ?

**Réponse :** L'injection par **constructeur** est recommandée car elle :
- Rend les dépendances obligatoires
- Facilite les tests
- Améliore la maintenabilité

---

### Question : À quoi sert @Configuration ?

**Réponse :** Elle indique que la classe contient des beans Spring (via `@Bean`) et sert à configurer l'application.

---

### Question : Quelle est la différence entre @Component, @Service, @Repository ?

**Réponse :** Elles font toutes enregistrer un bean, mais :
- **@Component** : général
- **@Service** : couche service (métier)
- **@Repository** : couche DAO (accès BD), gère aussi les exceptions SQL

---

### Question : Qu'est-ce que @Bean ?

**Réponse :** Il permet de déclarer manuellement un objet comme bean Spring dans une classe `@Configuration`.

---

## Niveau avancé

### Question : Différence entre @RestController et @Controller ?

**Réponse :**
- **@Controller** : renvoie généralement une vue (template)
- **@RestController** : renvoie directement les données (JSON/XML) dans la réponse HTTP (équivaut à `@Controller` + `@ResponseBody`)

---

### Question : Qu'est-ce qu'un conteneur IoC ?

**Réponse :** Le conteneur IoC gère :
- La création des objets (beans)
- Leur cycle de vie
- L'injection de dépendances (DI)

---

### Question : Différence entre @RequestMapping et @GetMapping ?

**Réponse :**
- **@RequestMapping** : peut gérer plusieurs verbes HTTP (GET/POST/PUT…) via `method=...`
- **@GetMapping** : raccourci dédié uniquement à GET

---

### Question : À quoi servent les profils (Profiles) ?

**Réponse :** À charger des configurations différentes selon l'environnement (dev/QA/prod), ex. base H2 en dev et Oracle en prod.

---

### Question : Qu'est-ce que Spring Actuator et ses avantages ?

**Réponse :** Un module qui expose des endpoints de supervision/gestion :
- Santé
- Métriques
- Infos
- Beans
- Env…

Utile en production.

---

### Question : Comment activer Actuator ?

**Réponse :** En ajoutant la dépendance `spring-boot-starter-actuator`.

---

### Question : Quels endpoints Actuator sont courants ?

**Réponse :**
- `health`
- `info`
- `beans`
- `mappings`
- `configprops`
- `env`
- `heapdump`
- `threaddump`
- `shutdown` (souvent sécurisé/désactivé)

---

### Question : Comment lister tous les beans ?

**Réponse :** Via l'endpoint Actuator `/beans` (si exposé).

---

### Question : Comment voir les propriétés d'environnement ?

**Réponse :** Via `/env` (si exposé).

---

### Question : Comment activer les logs debug ?

**Réponse :**
- `--debug` au lancement
- Ou `logging.level.root=debug`
- Ou config logger via fichier de logging

---

### Question : Où définit-on les propriétés Spring Boot ?

**Réponse :** Dans `application.properties` ou `application.yml` (chargés automatiquement s'ils sont dans le classpath), avec variantes par profil.

---

### Question : Qu'est-ce que l'injection de dépendances (DI) ?

**Réponse :** Injection des dépendances d'un bean vers un autre :
- Par constructeur
- Par setter
- Par champ (field injection, généralement moins recommandée)

---

### Question : Comment désactiver une auto-configuration spécifique ?

**Réponse :** En utilisant `exclude` sur `@EnableAutoConfiguration` (ou sur `@SpringBootApplication` selon le cas).

---

### Question : Peut-on désactiver le serveur web par défaut ?

**Réponse :** Oui, via `spring.main.web-application-type=none`.

---

### Question : Peut-on remplacer Tomcat embarqué ?

**Réponse :** Oui, en changeant de starter (ex. `spring-boot-starter-jetty`).

---

### Question : Quel est le port par défaut ? Peut-on le changer ?

**Réponse :** Par défaut `8080`, modifiable via `server.port`.

---

### Question : Peut-on faire une application non-web avec Spring Boot ?

**Réponse :** Oui, en retirant les dépendances web et/ou en configurant le type d'application (`none`).

---

### Question : Qu'est-ce que le "dependency management" de Spring Boot ?

**Réponse :** Boot gère des versions compatibles de dépendances (via BOM/parent), évitant de préciser chaque version manuellement.

---

### Question : Quelles annotations de base Spring Boot sont importantes ?

**Réponse :**
- `@EnableAutoConfiguration`
- `@SpringBootApplication`

Côté composants :
- `@Component`
- `@Service`
- `@Repository`
- `@Controller`
- `@RestController`

---

## Spring Boot REST API

### Question : Quelle est la différence entre @PathVariable et @RequestParam ?

**Réponse :**
- **@PathVariable** : récupère une valeur dans l'URL (`/users/10`)
- **@RequestParam** : récupère une valeur en paramètre (`/users?id=10`)

---

### Question : Quelle est la différence entre POST et PUT ?

**Réponse :**
- **POST** : créer une ressource
- **PUT** : modifier/remplacer une ressource existante

---

### Question : À quoi sert @RequestBody ?

**Réponse :** Elle permet de récupérer un objet JSON envoyé dans la requête HTTP et de le convertir en objet Java.

---

### Question : Qu'est-ce qu'un DTO ?

**Réponse :** Un DTO (Data Transfer Object) est un objet utilisé pour transférer les données entre client et serveur sans exposer directement les entités.

---

### Question : Comment gérer les exceptions globalement dans Spring Boot ?

**Réponse :** Avec `@ControllerAdvice` + `@ExceptionHandler` pour centraliser la gestion des erreurs.

---

## Spring Boot + Base de données

### Question : Quelle est la différence entre JPA et Hibernate ?

**Réponse :**
- **JPA** : une spécification
- **Hibernate** : une implémentation de JPA

---

### Question : À quoi sert @Entity ?

**Réponse :** Elle indique qu'une classe représente une table de base de données.

---

### Question : C'est quoi un Repository dans Spring Data JPA ?

**Réponse :** C'est une interface qui permet d'effectuer des opérations CRUD sans écrire de requêtes SQL.

---

### Question : À quoi sert @Transactional ?

**Réponse :** Elle permet de gérer une transaction (commit/rollback) automatiquement.

---

### Question : Différence entre JpaRepository et CrudRepository ?

**Réponse :**
- **CrudRepository** : fournit le CRUD de base
- **JpaRepository** : ajoute pagination, tri et fonctionnalités JPA avancées

---

## Sécurité Spring Boot (Spring Security)

### Question : Qu'est-ce que Spring Security ?

**Réponse :** Un framework qui permet de sécuriser une application :
- Authentification
- Autorisation

---

### Question : Quelle est la différence entre Authentication et Authorization ?

**Réponse :**
- **Authentication** : vérifier l'identité (login/password)
- **Authorization** : vérifier les droits (roles/permissions)

---

### Question : C'est quoi JWT ?

**Réponse :** JWT (JSON Web Token) est un token signé utilisé pour l'authentification stateless dans les API REST.

---

## Performance et architecture

### Question : Qu'est-ce que le caching dans Spring Boot ?

**Réponse :** C'est une technique pour stocker temporairement des résultats afin d'éviter des appels répétitifs (BD/API). Exemple : `@Cacheable`.

---

### Question : Qu'est-ce que @Async ?

**Réponse :** Elle permet d'exécuter une méthode de façon asynchrone (en arrière-plan).

---

### Question : Qu'est-ce qu'un microservice ?

**Réponse :** Une architecture où une application est divisée en petits services indépendants, chacun déployable séparément.

---

## Actuator / Monitoring

### Question : Comment sécuriser les endpoints Actuator ?

**Réponse :** En configurant Spring Security + limitant les endpoints exposés via `management.endpoints.web.exposure.include`.

---

### Question : À quoi sert l'endpoint /health ?

**Réponse :** Il indique l'état de l'application (UP/DOWN) et parfois l'état de la base de données ou des dépendances.

---
