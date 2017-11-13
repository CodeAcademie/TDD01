# Les Tests Unitaires, les tests fonctionnels et les tests graphiques

Une [URL](http://blog.xebia.fr/2008/04/11/les-10-commandements-des-tests-unitaires/) certes, un peu veille, mais toujours d'actualité. 

Les tests servent à garantir le bon fonctionnement de votre application. Mais aussi à garantir le fait que vous ne fassiez pas de [régressions](https://fr.wikipedia.org/wiki/Test_de_r%C3%A9gression). 

En effet, l'application que vous développez est vouée à évoluer. Une fois la première version livrée à votre client, il est probable et souhaité qu'il revienne vers vous pour une amélioration de certaines fonctionnalités. Mais comment vous assurer que les nouvelles fonctionnalités ne viennent pas perturber l'existant? 

Pour se faire, il existe les tests. Plusieurs types de tests existent, les tests fonctionnels et les tests unitaires. 

## Les tests unitaires

Les tests unitaires sont définis par les développeurs. Et vous aurez les bonnes pratiques mentionnées dans le tout premier lien de ce document. 

Il est conseillé de dérouler des tests à chaque commit pour voir si vous n'avez pas rajouté d'anomalie lors de votre développement.  Et de dérouler l'ensemble des tests avant toute livraison. Par contre les tests eux-mêmes ne sont pas interessant à livrer au client. 

Des logiciels, tels que [Jenkins](https://jenkins.io/) ou encore [Sonar](https://www.sonarqube.org) permettent d'automatiser les tests ainsi que les rapports générés.

Une bonne pratique étant de définir les tests en amont du développement. 
Idem, lors d'échanges avec des clients pour un bug constaté. Une bonne approche est de commencer par un test unitaire reprisduisant l'erreur. Avant de la corriger.

## Les tests fonctionnels

Les tests fonctionnels sont des tests textuels. Pouvant être redigés en consertation avec votre client, les tests fonctionnels sont lisibles par une personne eloignée de la technique. 

Ex : 
> Feature: User trades stocks
>  Scenario: User requests a sell before close of trading
>    Given I have 100 shares of MSFT stock
>       And I have 150 shares of APPL stock
>       And the time is before close of trading
>
>   When I ask to sell 20 shares of MSFT stock
>    
>     Then I should have 80 shares of MSFT stock
>      And I should have 150 shares of APPL stock
>      And a sell order for 20 shares of MSFT stock should have been executed

Ces tests sont basés sur un language nommé le Gherkin. Des bibliothèques, spécifiques à un language, comme Behat pour PHP ou Cucumber pour le JS, interprètent le gherkin et déclenchent des tests en conséquence.

## Les tests graphiques
Les tests mentionnés ci-dessus ne permettent pas pour autant de valider le graphisme d'un site internet, de valider le bon support des navigateurs ni même le côté responsive d'un site. 

Pour se faire il existe des tests automatiques du type de [Selenium](http://www.seleniumhq.org/docs/01_introducing_selenium.jsp).

## Liens Test Unitaire
* Jasmine
* PHPUnit
* PyUnit


## Exercice

Après vous être documenté sur les technologies, réaliser des tests unitaires pour votre application de Pomodoro.

Une fois celà réalisé, montrez le aux formateurs pour correction puis amorcez la même démarche mais pour l'application Reminder.