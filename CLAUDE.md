# Yoga App (P4 OC) — Claude Code

Source canonique partagée : **AGENTS.md** (mission, zones, arbitrages, garde-fou de concentration).

@AGENTS.md

## Briefs et avancement (chargés à chaque session)
@docs/avancement.md
@docs/oc/Etapes_a_suivre_P4_1.md
@docs/oc/Etapes_a_suivre_P4_2.md
@docs/oc/testing_plan_P4.md
@docs/oc/Sous_livrables_du_projet.md
@docs/oc/Fiches_auto-evaluation.md

## Spécifique Claude Code
- Lancer Claude depuis la racine du repo : `.claude/settings.json` n'est lu que depuis le répertoire de lancement.
- Skills globaux réutilisables : `commit-convention`, `spring-boot-patterns` (`@ControllerAdvice`, couches), `jpa-patterns`, `evaluate`, `handoff`, `tdd`, `generate-tests`, `e2e-cypress-writer`.
- Agents globaux : `backend-test-writer`, `angular-test-writer`, `test-reviewer`, `backend-reviewer`, `frontend-angular-reviewer`.
- Réserves :
  - `backend-test-writer` / `generate-tests` / `tdd` : BDD de test = Testcontainers **MySQL** (pas Postgres), pas de Failsafe ; `./mvnw` seulement après A9 ; ≥ 30 % d'intégration ; ne pas tester `dto/`, `payload/`, `*MapperImpl` (A3).
  - `generate-tests` / `test-reviewer` : **sans PITest** (étape sautée, plugin non ajouté).
  - `angular-test-writer` / `frontend-angular-reviewer` / `tdd` : Jest (`npm test` = `jest`) → `jest.fn()`, pas Karma/Jasmine.
  - E2E : `e2e-cypress-writer` en `cy.intercept` + fixtures fidèles (A10), jamais `e2e-playwright-writer`.
