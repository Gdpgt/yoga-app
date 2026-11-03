**![](https://user.oc-static.com/upload/2023/10/09/16968382727551_Section%20exercice.png)  
**

#### [#](#pret-a-resoudre-lexercice)**Prêt à résoudre l’exercice ?**

![Barres titres](https://user.oc-static.com/upload/2023/09/19/16951295813132_Barre%20titres.png)

Dans cet exercice, vous allez implémenter des tests sur l’application du studio yoga afin d’assurer la qualité du code que vous avez déjà amélioré lors de l’exercice précédent.

Votre responsable, Adrianne, vous transmet [ce plan du testing](https://course.oc-static.com/projects/4080_Testez+et+am%C3%A9liorez+une+application+Full-Stack/Testing+plan+-+P4+DFSJA.pdf) préparé par votre collègue avant qu’il soit parti en congé parental.

Vous allez mettre en œuvre ce plan avec l’aide des outils de test suivants : 

*   **Jest** pour les tests unitaires et d’intégration du front Angular
    
*   **Cypress** pour les tests end-to-end (e2e) du front Angular
    
*   **Mockito** et **JUnit** pour tester le code back en Java
    

Vous devrez assurer une couverture de 80 % minimum du code, pour chaque indicateur (instructions, branches, etc.) sur chacune des parties. En revanche, il faut que vous ne testiez pas le package DTO sur le back-end.

Adrianne vous demande de fournir : 

*   le **code complet d’application**, y compris les tests ;
    
*   les **rapports de couverture des tests** qui indiquent le seuil de 80 % minimum pour les instructions et les branches sur chacune des parties ;
    
*   un **README** qui explique comment installer le projet, le lancer et exécuter les tests.
    

Cet exercice est entièrement guidé.

Vous pouvez suivre les étapes ci-dessous.

### Étapes

### 

#### Étape 1 –​ Implémentez les tests unitaires et d’intégration du front avec Jest

**Prérequis**

*   Avoir :
    *   Monté en compétences sur Jest pour les tests unitaires et d’intégration
        
    *   Connaissance du plan de testing fourni et comment de le mettre en œuvre
        
    *   Si nécessaire, avoir revisité le code et le README dans le front de l’application.
        

**Résultat attendu**

*   Avoir implémenté les tests suivants :
    
    *   les tests unitaires sur le front ;
        
    *   les tests d'intégration sur le front.
        
*   Avoir généré les rapports de tests qui indiquent un seuil de 80 % minimum pour chaque indicateur (instructions, branches, etc.) sur le front-end, indiqué par des rapports de test générés.
    

**Recommandations**

*   Prenez un temps pour monter en compétences sur Jest en lisant attentivement les ressources fournies.
    

*   N’hésitez pas à revenir aux ressources si vous vous trouvez bloqué.
    

*   Testez d’abord les composants les plus simples avant d’aborder les composants les plus avancés.
    
*   Réalisez les tests des services.
    

**Points de vigilance**

*   Au moins 30 % de vos tests doivent être des tests d'intégration.
    
*   Assurez-vous de comprendre comment vos tests correspondent au plan de testing.
    

**Ressources**

*   Cours OpenClassrooms **
    
    [
    
    DéveloppementTestez vos applications Angular
    
    Moyenne
    
    Maîtrisez les tests Angular pour sécuriser vos projets : unitaires, intégration, mocks, CI, tout y est pour un code stable et prêt pour la production.
    
    
    
    
    
    
    
    ](https://openclassrooms.com/fr/courses/8717256-testez-vos-applications-angular)
    
    **(bien que le cours utilise Jasmine, les tests sont très facilement transposables sous le framework Jest)
*   Chapitre du cours OpenClassrooms 'Testez vos applications Front End avec JavaScript' : “[Réalisez vos premiers tests unitaires avec Jest](/fr/courses/7159306-testez-vos-applications-front-end-avec-javascript/7332796-realisez-vos-premiers-tests-unitaires-avec-jest)”
    
*   Documentation officielle Jest : “[Premiers pas](https://jestjs.io/fr/docs/getting-started)”
    
*   [Unit Testing with Mocks and Spies](https://codecraft.tv/courses/angular/unit-testing/mocks-and-spies/)
    
*   [How to mock an API response using cy.intercept() - TestersDock](https://testersdock.com/cypress-mock-api-intercept/)
    

### 

#### Étape 2 –​ Implémentez les tests E2E du front avec Cypress

**Prérequis**

*   Avoir :
    
    *   monté en compétences sur Cypress pour les tests end-to-end (du bout au bout)
        
    *   connaissance du plan de testing fourni et comment de le mettre en œuvre
        
    *   Si nécessaire, avoir revisité le code et le README dans le front de l’application.
        

**Résultat attendu**

*   Avoir implémenté les tests suivants les tests end-to-end de chaque écran du front.
    
*   Avoir une couverture de test de 80 % minimum pour chaque indicateur (instructions, branches, etc.) sur le front-end et E2E, indiqué par des rapports de test générés.
    

**Recommandations**

*   Si vous en avez besoin, lisez les ressources sur Cypress pour monter en compétences ou si vous vous trouvez bloqué.
*   Pour les tests E2E avec Cypress : 
    

*   Commencez les tests E2E par les formulaires les plus simples tels que la création de compte et la connexion.
    
*   Évoluez ensuite vers les pages plus complexes.
    

**Points de vigilance**

*   Attention à l'intégration front / back durant les tests E2E.

**Ressources**

*   Le cours OpenClassrooms [**Automatisez des tests fonctionnels pour le web avec Cypress**](/fr/courses/8157231-automatisez-des-tests-fonctionnels-pour-le-web-avec-cypress), en particulier les chapitres [Installez et prenez en main Cypress](/fr/courses/8157231-automatisez-des-tests-fonctionnels-pour-le-web-avec-cypress/8315806-installez-et-prenez-en-main-cypress) et [Rédigez des cas de test fonctionnel](/fr/courses/8157231-automatisez-des-tests-fonctionnels-pour-le-web-avec-cypress/8317166-redigez-des-cas-de-test-fonctionnel)
    
*   Ces ressources rédigées en anglais :
    

*   [End-to-end testing with Cypress – Testing Angular](https://testing-angular.com/end-to-end-testing/)
    
*   [Cypress Documentation](https://docs.cypress.io/app/get-started/why-cypress#5-Todo-item-behavior)
    

### 

#### Étape 3 –​​ Implémentez les tests unitaires et d’intégration du back avec Mockito et JUnit

**Prérequis**

*   Avoir :
    *   monté en compétences sur Mockito et JUnit en lisant les ressources
        
    *   Si nécessaire, avoir revisité le code et le README dans le back de l’application.
        

**Résultat attendu**

*   Avoir implémenté les tests unitaires et d’intégration du back.
    
*   Avoir une couverture de test de 80 % minimum pour chaque indicateur (instructions, branches, etc.) sur le back, indiqué par des rapports de test générés.
    

**Recommandations**

*   Lisez attentivement les ressources sur Mockito et sur JUnit si vous y avez des questions ou des doutes.
    
*   Implémentez les tests unitaires sur les services :
    
    *   Identifiez les services les plus simples et y ajouter les cas de test.
        
    *   Ensuite, testez les services les plus complexes.
        
    *   Pour chaque service testé, pensez à ajouter assez de tests pour couvrir le plus grand nombre de cas possibles. 
        
*   Implémentez les tests d’intégration sur les controllers :
    
    *   Pour les BDD de tests d’intégration, vous pouvez utiliser H2 ou MySQL.
        
    *   Identifiez les controllers les plus simples et commencer à les tester
        
    *   Ensuite, passez aux controllers les plus complexes.
        

**Points de vigilance**

*   Il faut que chaque test se focalise sur un cas particulier dans le plan de testing.
    
*   Au moins 30 % de vos tests doivent être des tests d'intégration.
    
*   Gardez en tête que vous ne devez pas tester les packages contenant du code de type DTO.
    
*   Prenez bien en compte le mode Spring Boot Test pour les tests de l'API.

**Ressources**

*   Le cours OpenClassrooms [Testez votre code Java pour réaliser des applications de qualité](/fr/courses/6100311-testez-votre-code-java-pour-realiser-des-applications-de-qualite), en particulier le chapitre [Utilisez les fonctions avancées de Mockito](/fr/courses/6100311-testez-votre-code-java-pour-realiser-des-applications-de-qualite/6441161-utilisez-les-fonctions-avancees-de-mockito).
    
*   Le chapitre [Testez votre API avec Spring Boot](/fr/courses/6900101-creez-une-application-spring-boot/7078023-testez-votre-api-avec-spring-boot) du cours OpenClassrooms [Créez une application Java avec Spring Boot](/fr/courses/6900101-creez-une-application-spring-boot).
    
*   Ces ressources rédigées en anglais : 
    
    *   [Mockito Series | Baeldung](https://www.baeldung.com/mockito-series)
        
    *   [Getting Started with Mockito @Mock, @Spy, @Captor and @InjectMocks | Baeldung](https://www.baeldung.com/mockito-annotations)
        
    *   [Test JUnit avec une base de données H2](https://www.baeldung.com/spring-jpa-test-in-memory-database)
        
    *   [Test d’intégration avec MySQL TestContainer](https://medium.com/@Lakshitha_Fernando/integration-testing-bb31676915ae)
        

### 

#### Étape 4 –​ Écrivez la documentation README

**Prérequis**

*   Avoir implémenté les tests unitaires et d’intégration du front et du back et les tests E2E.
    
*   Avoir généré les rapports de tests qui vérifient le seuil de couverture du code au moins 80 %.
    

**Résultat attendu**

*   Avoir rédigé le README pour documenter le projet et les tests.
    

**Recommandations**

*   Le README doit expliquer : 
    

*   comment installer et lancer l’application ;
    
*   comment lancer et exécuter les différents tests ;
    
*   comment générer les rapports de couverture.
    

*   Assurez-vous que le seuil 80 % de couverture du code est pour chaque indicateur (instructions, branches, etc.) sur chacune des parties.
    

### 

#### Vérifiez votre travail et faites le point avec votre mentor

Pour vérifier que vous n’avez rien oublié dans la réalisation de votre exercice, téléchargez et complétez la [fiche d’autoévaluation](https://course.oc-static.com/projects/4080_Testez+et+am%C3%A9liorez+une+application+Full-Stack/Fiche+d'autoe%CC%81valuation+P4+-+Testez+et+ame%CC%81liorez+une+application+full-stack.pdf).

Parlez-en avec votre mentor durant votre dernière session de mentorat.

[Avez-vous une suggestion pour nous ?](https://openclassrooms.tfaforms.net/4984649?tfa_19=13845563&tfa_13=2460&tfa_15=4080&tfa_17=9051)