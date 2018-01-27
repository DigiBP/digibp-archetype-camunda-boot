# DigiBP Camunda Boot Archetype

## Summary
These archetypes can be used to create a fresh Camunda Spring Boot project.

## New Project Creation
Create a new project using the archetype published here: https://digibp.github.io/digibp-archetype-camunda-boot

### Creating a Project in Maven
```text
mvn archetype:generate -DarchetypeCatalog=https://digibp.github.io/digibp-archetype-camunda-boot/archetype-catalog.xml
```

### Creating a Project in Eclipse

#### Add a Remote Archetype Catalog 
- Open `Window > Preferences`
- Go to `Maven > Archetypes` and select `Add Remote Catalog...`
- Set `Catalog File` to `https://digibp.github.io/digibp-archetype-camunda-boot/archetype-catalog.xml`
- Click `OK` so the Archetype catalog is added to the list

#### Creating a Project in Eclipse using the Catalog
- Create new project `File > New > Maven Project`
- Make sure `Create a simple project` option is not selected
- Click `Next` to navigate to `Select an Archetype` screen
- Select the `Remote https://digibp...` catalog from the `Catalog` dropdown 
- Select the latest archetype `digibp-archetype-camunda-boot` from the appearing list
- Click `Next` and create the project
> Note: How to build and run a Spring Boot application in Eclipse: (1) In Eclipse Project Explorer, right click the project name > select `Run As` > `Maven Build...` (2) In the goals, enter: `spring-boot:run`

### Creating a Project in IntelliJ
- Create new project `File > New > Project`
- Click Maven on the left hand side of the new project dialog
- Check `Create from archetype`
- Note: If you are using the IntelliJ [Maven Archetype Catalogs](https://plugins.jetbrains.com/plugin/7965-maven-archetype-catalogs) plugin and adding the `Catalog File` `https://digibp.github.io/digibp-archetype-camunda-boot/archetype-catalog.xml`, the following steps can be avoided: 
    - Click the `Add Archetype` button
        - Set `Group Id` to `ch.fhnw.digibp.archetype`
        - Set `Artifact Id` to `digibp-archetype-camunda-boot`
        - Set `Version` to `<the latest release version>`
        - Set `Repository` to `https://digibp.github.io/digibp-archetype-camunda-boot`
- Select the latest archetype `digibp-archetype-camunda-boot` from the appearing list
- Click next, and specify GroupId, ArtefactId and Version
- Click next and select a user settings file with the following content:
    ```xml
    <settings xmlns="http://maven.apache.org/SETTINGS/1.0.0"
        xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
        xsi:schemaLocation="http://maven.apache.org/SETTINGS/1.0.0
                            https://maven.apache.org/xsd/settings-1.0.0.xsd">
        <profiles>
            <profile>
                <activation>
                    <activeByDefault>true</activeByDefault>
                </activation>
                <repositories>
                    <repository>
                        <id>archetype</id>
                        <url>https://digibp.github.io/digibp-archetype-camunda-boot</url>
                    </repository>
                </repositories>
            </profile>
        </profiles>
    </settings>
    ```
 - Click next and create the project

## Project Profiles
1. Camunda-Spring-Boot-JAR
2. Camunda-Spring-Boot-WAR
3. Camunda-Enterprise-Edition

### Camunda Enterprise Edition
1. Select the `Camunda-Enterprise-Edition` maven profile.
2. Create a `maven-user-settings.xml` file containing Camunda Maven repsository's username and password:
    ```xml
    <settings xmlns="http://maven.apache.org/SETTINGS/1.0.0"
              xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
              xsi:schemaLocation="http://maven.apache.org/SETTINGS/1.0.0
                          https://maven.apache.org/xsd/settings-1.0.0.xsd">
        <servers>
            <server>
                <id>camunda-bpm-ee</id>
                <username></username>
                <password></password>
            </server>
        </servers>
    </settings>
    ```
3. Add the `maven-user-settings.xml` to the IntelliJ or Eclipse project settings.
4. Create a `camunda-license.txt` file under `src > main > resources` and paste your Camunda BPM license key:
    ```text
    --------------- BEGIN CAMUNDA BPM LICENSE KEY ---------------
    
    ---------------  END CAMUNDA BPM LICENSE KEY  ---------------
    ```
5. Important: Add to `maven-user-settings.xml` and `camunda-license.txt` to `.gitignore`

## Releases

### 1.0.6

- Updating Camunda Spring Boot to 2.1.0
- Updating Spring Boot to 1.5.3.RELEASE
- Adding to application.yaml: `camunda:bpm:authorization:enabled:true`

### 1.0.5

- Updating Camunda Enterprise Edition to 7.6.4
- Uncommenting Camunda REST API
- Adding (uncommented) Spring Boot Data
- Adding (uncommented) Hibernate configuration to application.yaml

### 1.0.4

- Adding Camunda Enterprise Edition

### 1.0.3

- Fixing the Maven issue

### 1.0.2

- Fixing the Eclipse issue

### 1.0.1

- Fixing the basic package

### 1.0.0

- Initial version

## Maintainer
- [Andreas Martin](https://github.com/andreasmartin)

## License

- [Apache License, Version 2.0](https://github.com/DigiBP/digibp-archetype-camunda-boot/blob/master/LICENSE)
