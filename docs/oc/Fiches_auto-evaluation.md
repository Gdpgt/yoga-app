# Fiches d'Auto-évaluation

## Partie 1 - Améliorez le code existant

### Étape 1 - Lancez le projet et prenez la connaissance
- [ ] Le projet a été téléchargé et importé avec succès dans mon IDE.
- [ ] J'ai installé tous les outils et les technologies nécessaires pour ce projet.
- [ ] J'ai parcouru le code existant pour en comprendre la structure.

### Étape 2 - Améliorez le code du front
- [ ] J'ai identifié les observables qui ne sont pas désabonnés et j'ai apporté les améliorations nécessaires pour gérer leur désabonnement.
- [ ] J'ai typé les méthodes qui ne l'étaient pas.
- [ ] J'ai supprimé tous les types "any".
- [ ] J'ai supprimé les anciennes directives structurelles `*ngIf` et `*ngFor` et je les ai remplacées par les contrôles de flux tels que `@if`, `@for`.
- [ ] J'ai testé que le build est OK avec `ng serve`.
- [ ] J'ai fait des commits atomiques et des messages clairs.

### Étape 3 - Améliorez le code du back
- [ ] J'ai amélioré le découpage des couches :
  - [ ] Aucun controller n'appelle plus de repository.
  - [ ] Désormais, les controllers appellent les services qui appellent eux-mêmes les repositories.
- [ ] J'ai réussi à gérer les exceptions :
  - [ ] J'ai identifié les `try {} catch {}` redondantes (gestion des exceptions).
  - [ ] J'ai utilisé une autre méthode (`@ControllerAdvice` par exemple) pour centraliser la gestion des exceptions et réduire la duplication de code.
- [ ] J'ai déplacé les traitements métier des classes de controllers vers les classes de service.
- [ ] J'ai testé toutes les APIs pour m'assurer qu'il n'y a pas de régression.

---

## Partie 2 - Implémentez les tests unitaires et d'intégration

### Étape 1 - Implémentez les tests unitaires et d'intégration du front avec Jest
- [ ] Les tests s'exécutent sans erreur :
  - [ ] Les tests unitaires sur le front.
  - [ ] Les tests d'intégration sur le front.
- [ ] Les tests d'intégration représentent au minimum 30% des tests parmi tous les tests réalisés.
- [ ] J'ai généré les rapports de couverture de code.
- [ ] Les rapports de couverture des tests (front-end) démontrent 80% de couverture minimum pour tous les indicateurs, y compris les instructions, les branches, les lignes, etc.

### Étape 2 - Implémentez les tests E2E du front avec Cypress
- [ ] Les tests end-to-end de chaque écran du front s'exécutent sans erreur.
- [ ] J'ai généré les rapports de couverture de code.
- [ ] Les rapports de couverture des tests (e2e) démontrent 80% de couverture minimum pour tous les indicateurs, y compris les instructions, les branches, les lignes, etc.

### Étape 3 - Implémentez les tests unitaires et d'intégration du back avec Mockito et JUnit
- [ ] Les tests s'exécutent sans erreur :
  - [ ] Les tests unitaires sur le back.
  - [ ] Les tests d'intégration sur le back.
- [ ] Le package DTO n'a pas été testé.
- [ ] Les tests d'intégration représentent au minimum 30% des tests parmi tous les tests réalisés.
- [ ] J'ai généré les rapports de couverture de code.
- [ ] Les rapports de couverture des tests unitaires et d'intégration (back-end) démontrent 80% de couverture minimum pour tous les indicateurs, y compris les instructions, les branches, les lignes, etc.

### Étape 4 - Écrivez la documentation README
- [ ] Le README décrit les procédures pour :
  - [ ] Installer et utiliser l'application.
  - [ ] Lancer les tests.
  - [ ] Générer les rapports de couverture.