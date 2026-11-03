# Avancement — Projet 4 OC (Yoga App)

> **Règle** : l'agent ne coche une case **que** sur déclaration de l'apprenant
> (ou sur une proposition qu'il a confirmée). Il ne remplit jamais la fiche
> d'auto-évaluation elle-même.
>
> Étiquettes : `[BRIEF]` briefs `docs/oc/`, `[FICHE]` fiche d'auto-évaluation,
> `[DÉCISION Ax]` arbitrage de l'apprenant (cf. `AGENTS.md` §6).

## Partie 1 — Améliorez le code existant

### Étape 1 — Prise en main et analyse du projet [BRIEF P4_1] [FICHE]
- [x] Projet téléchargé et importé dans l'IDE (déclaré le 2026-11-03)
- [ ] Outils et technologies nécessaires installés
- [ ] Code existant parcouru (structure front et back comprise)
- [ ] Front et back lancés (Docker / CLI), fonctionnement initial vérifié
- [ ] [DÉCISION A9] JDK 21 installé via SDKMAN + wrapper `mvnw` généré dans `back/`

### Étape 2 — Refactoring front (Angular 19) [BRIEF P4_1] [FICHE]
- [ ] Observables non désabonnés identifiés et désabonnement géré (`takeUntilDestroyed`)
- [ ] Toutes les méthodes typées (type de retour précis ou `void`)
- [ ] Tous les types `any` supprimés
- [ ] `*ngIf` / `*ngFor` remplacés par `@if` / `@for`
- [ ] Chaque modification testée au fil de l'eau (pas de régression)
- [ ] Build OK avec `ng serve`
- [ ] Commits atomiques aux messages clairs

### Étape 3 — Refactoring back (Java 21 / Spring Boot 3) [BRIEF P4_1] [FICHE]
- [ ] Aucun controller n'appelle plus de repository
- [ ] Les controllers appellent les services, qui appellent les repositories
- [ ] `try/catch` redondants identifiés (ex. `NumberFormatException`)
- [ ] Gestion des exceptions centralisée (`@ControllerAdvice` + `@ExceptionHandler`)
- [ ] Traitements métier déplacés des controllers vers les services
- [ ] Toutes les APIs re-testées, sans régression (collection Postman)

## Partie 2 — Implémentez les tests

### Étape 1 — Tests unitaires et d'intégration front (Jest) [BRIEF P4_2] [FICHE]
- [ ] Tests unitaires front OK, sans erreur
- [ ] Tests d'intégration front OK, sans erreur
- [ ] Tests d'intégration ≥ 30 % de l'ensemble des tests
- [ ] Rapport de couverture généré
- [ ] Couverture ≥ 80 % sur tous les indicateurs (instructions, branches, lignes…)
- [ ] [DÉCISION A5] `coverageThreshold` Jest à 80 sur statements, branches, functions, lines

### Étape 2 — Tests E2E (Cypress) [BRIEF P4_2] [FICHE]
- [ ] Tests E2E de chaque écran OK, sans erreur
- [ ] Rapport de couverture généré
- [ ] Couverture E2E ≥ 80 % sur tous les indicateurs
- [ ] [DÉCISION A6] `front/nycrc` renommé en `.nycrc`, rapport E2E relu
- [ ] [DÉCISION A10] Tout en `cy.intercept`, fixtures copiées de vraies réponses du back (DTO, Postman)

### Étape 3 — Tests unitaires et d'intégration back (JUnit + Mockito) [BRIEF P4_2] [FICHE]
- [ ] Tests unitaires back (services) OK, sans erreur
- [ ] Tests d'intégration back (controllers, mode Spring Boot Test, Testcontainers MySQL — A4) OK, sans erreur
- [ ] Package DTO non testé
- [ ] Tests d'intégration ≥ 30 % de l'ensemble des tests
- [ ] Chaque test centré sur un cas particulier du testing plan
- [ ] Rapport de couverture généré
- [ ] Couverture ≥ 80 % sur tous les indicateurs
- [ ] [DÉCISION A1] JaCoCo monté en ≥ 0.8.11
- [ ] [DÉCISION A2] `jacoco-check` en BUNDLE, 0,80 sur INSTRUCTION, BRANCH, LINE, COMPLEXITY, METHOD, CLASS
- [ ] [DÉCISION A3] Exclusions `**/dto/**`, `**/payload/**`, `**/*MapperImpl*` dans `report` et `check`

### Étape 4 — README [BRIEF P4_2] [FICHE]
- [ ] Installer et lancer l'application
- [ ] Lancer les différents tests
- [ ] Générer les rapports de couverture
- [ ] [DÉCISION A8] Repo et dossier du README front du starter corrigés
- [ ] [DÉCISION A3/A10] Exclusions JaCoCo et stratégie E2E justifiées

## Couverture du testing plan [BRIEF testing_plan]
- [ ] Login : connexion ; erreurs mauvais login / password ; erreur champ obligatoire manquant
- [ ] Register : création de compte ; erreur champ obligatoire manquant
- [ ] Sessions : affichage de la liste ; boutons Create et Detail si admin
- [ ] Informations session : informations affichées ; bouton Delete si admin
- [ ] Création session : session créée ; erreur champ obligatoire manquant
- [ ] Suppression session : session supprimée
- [ ] Modification session : session modifiée ; erreur champ obligatoire manquant
- [ ] Account : informations de l'utilisateur affichées
- [ ] Logout : déconnexion de l'utilisateur

## Livrables [BRIEF Sous-livrables]
- [ ] Code front et back optimisé, historique de commits structuré
- [ ] Code de tous les tests (unitaires, intégration front et back, E2E)
- [ ] Rapports de couverture front, back et E2E (≥ 80 % sur chaque indicateur)
- [ ] `README.md` : installation, lancement, exécution des tests

## Fin de projet [BRIEF P4_2]
- [ ] Fiche d'auto-évaluation complétée par l'apprenant
- [ ] Point avec le mentor
