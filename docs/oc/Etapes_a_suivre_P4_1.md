# Exercice - Améliorez le code existant

## Contexte
Reprise et refactoring d'une application full-stack de réservation pour un studio de yoga (front Angular + back Spring Boot).
L'objectif est d'optimiser le code existant, d'appliquer les bonnes pratiques d'architecture et de typage, sans introduire de régression.

## Ressources du projet
* **Repository GitHub (starter code) :** [Application Full-Stack Yoga Studio](https://github.com/OpenClassrooms-Student-Center/Testez-et-am-liorez-une-application-full-stack)
* **Fiche d'auto-évaluation :** [Fiche d'auto-évaluation P4 (PDF)](https://course.oc-static.com/projects/4080_Testez+et+am%C3%A9liorez+une+application+Full-Stack/Fiche+d'autoe%CC%81valuation+P4+-+Testez+et+ame%CC%81liorez+une+application+full-stack.pdf)
* **Documentation & Guides utiles :**
  * [Angular `takeUntilDestroyed` (RxJS Interop)](https://angular.dev/ecosystem/rxjs-interop/take-until-destroyed)
  * [Guide Angular `@if`](https://blog.angular-university.io/angular-if/)
  * [Guide Angular `@for`](https://blog.angular-university.io/angular-for/)
  * [Baeldung - Centralisation des exceptions REST dans Spring (`@ControllerAdvice`)](https://www.baeldung.com/exception-handling-for-rest-with-spring)

---

## Configuration & Prérequis
* **Front-end :** Angular 19, Angular CLI
* **Back-end :** Java 21, Maven 3.9.3, Spring Boot 3
* **Conteneurisation / BDD :** Docker, Docker Compose, Docker Desktop

---

## Étapes de réalisation

### Étape 1 – Prise en main et analyse du projet

* Cloner et ouvrir le starter code en local.
* Explorer et analyser la structure de l'application :
  * Code TypeScript / Angular (front)
  * Code Java / Spring Boot (back)
* Lancer le front et le back via Docker / CLI et vérifier le bon fonctionnement initial de l'application.

---

### Étape 2 – Refactoring et optimisation Front-end (Angular 19)

#### Objectifs
Mettre aux normes le code front-end selon les bonnes pratiques modernes d'Angular.

#### Consignes de refactoring
1. **Gestion de la mémoire & Observables :**
   * Gérer systématiquement le désabonnement des Observables RxJS pour éviter les fuites de mémoire (ex: `takeUntilDestroyed`).
2. **Typage strict TypeScript :**
   * Typer explicitement toutes les méthodes (indiquer le type de retour précis ou `void`).
   * Éliminer **tous** les types `any` du projet.
3. **Migration de la syntaxe de templates :**
   * Remplacer les directives structurelles obsolètes (`*ngIf`, `*ngFor`) par le nouveau contrôle de flux natif d'Angular (`@if`, `@for`).
4. **Validation :**
   * Tester chaque modification au fur et à mesure pour éviter toute régression.
   * Valider le build et l'exécution avec `ng serve`.
   * Réaliser des commits Git atomiques au fur et à mesure de l'avancement.

---

### Étape 3 – Refactoring et architecture Back-end (Java 21 / Spring Boot 3)

#### Objectifs
Assainir l'architecture back-end, éliminer le code dupliqué et respecter la séparation des responsabilités.

#### Consignes de refactoring
1. **Centralisation de la gestion des exceptions :**
   * Supprimer les multiples blocs `try-catch` dispersés dans les controllers (ex: `NumberFormatException`).
   * Centraliser la gestion globale des erreurs via un `@ControllerAdvice` avec méthodes `@ExceptionHandler`.
2. **Respect du pattern en couches (`Controller` -> `Service` -> `Repository`) :**
   * Identifier et corriger les controllers qui appellent directement les repositories JPA.
   * Rétablir la chaîne d'appel stricte : le Controller appelle le Service, qui interagit avec le Repository.
3. **Déport de la logique métier :**
   * Extraire les traitements métiers présents dans les controllers (ex: vérification de l'existence d'un utilisateur, recherche/suppression de session) et les déplacer dans les classes `@Service`.
4. **Validation :**
   * Vérifier l'absence de régression sur les endpoints REST après chaque modification d'architecture.