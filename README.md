## Un projet Maven
- (Objigatoire) Un projet contenant un fichier `pom.xml`
- (optionel mais conseillé) respectant une structure du type 
<pre>
    racine
      |-src
      |   | - main
      |   |     | - java
      |   |     | - resources
      |   | - test
      |   |     | - java
      |   |     | - resources
      |-pom.xml
</pre>

## Goals
Ensemble des tâches executées pour réaliser votre projet.
Un ou plusieurs Goals peuvent être lancé via la commande mvn. 

`````shell
mvn clean compile
`````

### Compilation 

`````shell
mvn compile
`````

### Executer les tests

`````shell
mvn test
`````

### Un cycle de vie predefinie
La commande `mvn test` va lancer plusieurs goals à la suite.
   
    1. process-resources
    2. compile
    3. process-test-resources
    4. test-compile
    5. test

Voir [cycle de vie](https://maven.apache.org/guides/introduction/introduction-to-the-lifecycle.html)