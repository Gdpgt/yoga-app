# Yoga App — Projet 4 OpenClassrooms (Testez et améliorez une application full-stack)

Source canonique partagée par Claude Code (via `CLAUDE.md`), Codex et Antigravity.

## 1. Démarrage de session

Avant de répondre sur le projet, lis `docs/avancement.md` et les briefs de
`docs/oc/` (`Etapes_a_suivre_P4_1.md`, `Etapes_a_suivre_P4_2.md`,
`testing_plan_P4.md`, `Sous_livrables_du_projet.md`, `Fiches_auto-evaluation.md`).
Les originaux de `docs/oc/` font foi.

## 2. Mission

Reprendre le starter Yoga (front Angular 19 + back Spring Boot 3 / Java 21) :

1. **Exercice 1 — refactoring sans régression.** Front : désabonnement des
   Observables (`takeUntilDestroyed`), typage explicite de toutes les méthodes,
   zéro `any`, `*ngIf`/`*ngFor` → `@if`/`@for`. Back : `@ControllerAdvice` à la
   place des `try/catch` dispersés, chaîne stricte Controller → Service →
   Repository, logique métier déplacée dans les services.
2. **Exercice 2 — tests.** Jest (unitaires + intégration front), Cypress (E2E de
   chaque écran), JUnit 5 + Mockito (unitaires services + intégration
   controllers), rapports de couverture, README.

### Contraintes des briefs (à respecter, pas « non exigé »)

- ≥ 80 % de couverture sur **chaque** indicateur (instructions, branches,
  lignes…) sur **chacune** des parties : front (Jest), E2E (Cypress), back. [BRIEF]
- ≥ 30 % de tests d'intégration, front comme back. [BRIEF]
- **Ne pas tester le package DTO** du back. [BRIEF]
- Outils imposés : Jest, Cypress, JUnit + Mockito ; mode Spring Boot Test pour
  les tests de l'API ; chaque test centré sur un cas du testing plan. [BRIEF]
- Commits atomiques aux messages clairs. [BRIEF]

### Ressources fournies

- `back/postman/yoga.postman_collection.json` : contrat de l'API (re-test des
  endpoints, réponses réelles pour les fixtures Cypress).
- Admin par défaut : `back/src/main/resources/sql/insert_user.sql`, procédure
  dans `back/README.md`.

## 3. Commandes

### Front (`cd front`)

- `npm install`
- `npm run start` — `ng serve` avec proxy vers le back (`proxy.conf.json`).
- `npm test` — Jest ; `npx jest --coverage` → `front/coverage/jest/lcov-report/index.html`.
- `npm run e2e` — Cypress **interactif** (watch) ; puis `npm run e2e:coverage`
  → `front/coverage/lcov-report/index.html`. (`npm run e2e:ci` exige Chrome.)
- `npm run lint` — **non fonctionnel en l'état** (pas de cible `lint` dans
  `angular.json`) et hors périmètre (arbitrage A7).

### Back — après A9 (JDK 21 + wrapper `mvnw` générés) : aucune commande back exécutable avant

`cd back`, Docker démarré (le conteneur MySQL est lancé par
`spring-boot-docker-compose`) :

- `./mvnw spring-boot:run`
- `./mvnw test` — rapport JaCoCo → `back/target/site/jacoco/index.html`
  (une fois A1 fait).
- `./mvnw verify` — déclenche `jacoco-check`.

## 4. Zones

- **Immuable** : `docs/oc/` (briefs OpenClassrooms).
- **Gelé par le brief** : aucun.
- **Config — demander avant de modifier** : `back/pom.xml`, `back/mvnw*`,
  `back/.mvn/**`, `back/compose.yaml`, `back/.env`,
  `back/src/main/resources/application.yml`, `front/package.json` (+ lock),
  `front/angular.json`, `front/tsconfig*.json`, `front/jest.config.js`,
  `front/cypress.config.ts`, `front/nycrc` / `front/.nycrc`,
  `front/proxy.conf.json`, `front/.eslintrc.json`, `front/.browserslistrc`,
  câblage Cypress (`front/cypress/plugins/index.ts`,
  `front/cypress/coverage.webpack.ts`, `front/cypress/tsconfig.json`,
  `front/cypress/support/e2e.ts`), `.gitignore` de `front/` et `back/`.
- **Livrables de l'apprenant** (non verrouillés) : `front/src/**`,
  `front/cypress/e2e/**`, `front/cypress/support/commands.ts`,
  `front/cypress/fixtures/**`, `front/setup-jest.ts`,
  `front/test-config.helper.ts`, `back/src/**`, rapports de couverture, README,
  historique de commits. Hors mode `/tutor`, l'agent les rédige si l'apprenant le
  demande, sans remettre la demande en question ; en mode `/tutor`, il guide sans
  rédiger.

## 5. Non exigé par les briefs

PITest / tests de mutation, Playwright, CI, lint (A7), nouvelles
fonctionnalités, montées de version Angular / Spring / librairies (hors JaCoCo,
A1), signals / NgRx / `OnPush`, remplacement de `@angular/flex-layout`, refonte
de la sécurité JWT, conteneurisation du front, tests de performance ou de
sécurité.

## 6. Arbitrages et divergences ouvertes

Décisions prises par l'apprenant le 2026-11-03. Chaque décision qui implique du
travail figure comme tâche `[DÉCISION]` dans `docs/avancement.md` ; rien n'a été
appliqué au code ni à la config lors du bootstrap.

- **A1** JaCoCo 0.8.5 ↔ Java 21 (support officiel en 0.8.11) → monter JaCoCo
  ≥ 0.8.11. [CODE↔BONNE PRATIQUE]
- **A2** `jacoco-check` LINE ≥ 0,9 par PACKAGE ↔ brief 80 % sur chaque
  indicateur → élément **BUNDLE**, 0,80 sur INSTRUCTION, BRANCH, LINE,
  COMPLEXITY, METHOD, CLASS. [CODE↔BRIEF]
- **A3** Brief « DTO non testés » ↔ rapport JaCoCo → exclure `**/dto/**`,
  `**/payload/**`, `**/*MapperImpl*` dans `report` **et** `check` ; justifier
  dans le README. [BRIEF↔CODE]
- **A4** BDD des tests d'intégration back (brief : H2 ou MySQL) →
  **Testcontainers MySQL**, déjà au pom, aucune dépendance ajoutée. [BRIEF↔CODE]
- **A5** `jest.config.js` seuil `statements` seul → 80 sur statements, branches,
  functions, lines. [CODE↔BRIEF]
- **A6** `front/nycrc` sans point, ignoré par nyc → renommer en `.nycrc`, puis
  relire le rapport E2E. [CODE↔BONNE PRATIQUE]
- **A7** `npm run lint` non fonctionnel → hors périmètre, non réparé. [CODE]
- **A8** `front/README.md` du starter (repo `P5-Full-Stack-testing`, `cd yoga`)
  ↔ brief → corrigé lors de l'étape README. [CODE↔BRIEF]
- **A9** Environnement local (JDK 25 seul, `mvn` absent) → JDK 21 via SDKMAN
  installé par l'apprenant + wrapper `mvnw` (génération : un Maven ponctuel,
  puis `mvn -N wrapper:wrapper`). [CODE]
- **A10** Point de vigilance « intégration front / back en E2E » ↔ starter en
  `cy.intercept` → **`cy.intercept` partout**, fixtures copiées de vraies
  réponses du back (DTO, collection Postman) ; l'intégration réelle du back est
  prouvée par les tests d'intégration Spring Boot / Testcontainers ; choix
  expliqué dans le README. [BRIEF↔CODE]

Divergences ouvertes : aucune.

## Garde-fou de concentration (toujours actif, mode tuteur ou non)

L'apprenant a tendance à creuser chaque concept au lieu d'avancer, et rend ses
projets en retard. Protège son temps, sans jamais bloquer son avancement.

- **Ne s'applique jamais** à une erreur, un bug, une question qui bloque la tâche
  en cours, ni à une demande de faire quelque chose : réponds ou exécute
  normalement.
- Pour une question de compréhension, compare-la à ce qu'exigent l'étape en cours
  (`docs/avancement.md`) et les briefs, puis :
  - **exigé par l'étape en cours** → réponds normalement ;
  - **exigé par une étape ultérieure du projet** → réponse courte, et nomme cette
    étape (telle qu'écrite dans `docs/avancement.md`) ;
  - **non exigé par ce projet** → ne développe pas : dis en une phrase ce que
    l'étape exige concrètement à la place, puis dans quel type de situation le
    sujet deviendra utile. Pas de délai chiffré : tu ne connais pas le parcours
    de l'apprenant. Si tu ne sais pas situer le sujet, dis-le.
- Justifie le classement en une ligne, à partir des briefs ou de l'avancement,
  pas avec une formule toute faite.
- Si la conversation s'éloigne de l'étape à plusieurs reprises, rappelle la tâche
  en cours et ce qu'il reste à faire.
- Si l'apprenant insiste pour creuser, réponds.
