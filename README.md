# Proyecto base con Cucumber

Este proyecto cuenta con el sistema de dependencias en ```gradle``` y ```maven``` para poder contar con un ambiente en el cual se pueda ejecutar el ciclo de ATDD.

# Como configuro el proyecto utilando IntelliJ como IDE

Instalar el gestor de dependencias (gradle o maven).

- Instalación de [Gradle][1]
- Instalación de [Maven][2]

# Verificando herramientas:

## Gradle

Deberían poder ejecutar el comando ```./gradlew cucumber``` obteniendo una salida similar a la siguiente:

```cucumber
Starting a Gradle Daemon (subsequent builds will be faster)

> Task :cucumber
Feature: Gradle-Cucumber integration

  Scenario: Just a failing scenario # src/test/resources/gradle/cucumber/gradle.feature:3
    When I run a failing step       # BasicStepdefs.I_run_a_failing_step()

Feature: Sell Content

  Scenario: Set cell content with number # src/test/resources/gradle/cucumber/spreadsheet.feature:3
    Given Empty spreadsheet              # SpreadsheetStepdefs.iEmptySpreadSheet()
    When I set "a1" content with "1"     # SpreadsheetStepdefs.iSetContentWith(String,String)
    Then The cell "a1" has value "1"     # SpreadsheetStepdefs.iGetContent(String,String)

  Scenario: Set cell content with label        # src/test/resources/gradle/cucumber/spreadsheet.feature:8
    Given Empty spreadsheet                    # SpreadsheetStepdefs.iEmptySpreadSheet()
    When I set "a2" content with label "label" # SpreadsheetStepdefs.iSetContentWithLabel(String,String)
    Then The cell "a2" has value label "label" # SpreadsheetStepdefs.the_cell_has_value_label(String,String)

3 Scenarios (3 passed)
7 Steps (7 passed)
0m0.201s
```

## Maven

Deberían poder ejecutar el comando ```mvn test``` obteniendo una salida similar a la siguiente:

```cucumber
-------------------------------------------------------
 T E S T S
-------------------------------------------------------
Running gradle.cucumber.RunCukesTest
Feature: Gradle-Cucumber integration

  Scenario: Just a failing scenario # gradle/cucumber/gradle.feature:3
    When I run a failing step       # BasicStepdefs.I_run_a_failing_step()

Feature: Sell Content

  Scenario: Set cell content with number # gradle/cucumber/spreadsheet.feature:3
    Given Empty spreadsheet              # SpreadsheetStepdefs.iEmptySpreadSheet()
    When I set "a1" content with "1"     # SpreadsheetStepdefs.iSetContentWith(String,String)
    Then The cell "a1" has value "1"     # SpreadsheetStepdefs.iGetContent(String,String)

  Scenario: Set cell content with label        # gradle/cucumber/spreadsheet.feature:8
    Given Empty spreadsheet                    # SpreadsheetStepdefs.iEmptySpreadSheet()
    When I set "a2" content with label "label" # SpreadsheetStepdefs.iSetContentWithLabel(String,String)
    Then The cell "a2" has value label "label" # SpreadsheetStepdefs.the_cell_has_value_label(String,String)

3 Scenarios (3 passed)
7 Steps (7 passed)
0m0.247s

Tests run: 3, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.765 sec

Results :

Tests run: 3, Failures: 0, Errors: 0, Skipped: 0
```


[1]: https://gradle.org/install/#with-a-package-manager
[2]: http://maven.apache.org/install.html
