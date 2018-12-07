# DigiBP Camunda Boot Archetype

## Summary
These archetypes can be used to create a fresh Camunda Spring Boot project.

## New Project Creation
Create a new project using the archetype published here: [https://digibp.github.io/digibp-archetype-camunda-boot](https://digibp.github.io/digibp-archetype-camunda-boot)

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

## Procedure for creating an updated archetype
1. Clone the master branch of [digibp-camunda-template](https://github.com/DigiBP/digibp-camunda-template) and make your changes.
2. Make sure that you increase the version in the Maven `pom.xml`.
3. Generate the archetype from the project `clean archetype:create-from-project -Darchetype.properties=archetype.properties`.
4. Clone the master branch of [digibp-archetype-camunda-boot](https://github.com/DigiBP/digibp-archetype-camunda-boot) and copy your generated archetype files `target\generated-sources\archetype\src\main\resources` to the gh-pages branch under `src\main\resources`. 
5. Copy a `.gitignore` file to `src\main\resources\archetype-resources`.
6. Make sure that you increase the version in the Maven `pom.xml`.
7. Update the entries in `archetype-catalog.xml` (optional: `clean install archetype:update-local-catalog` and copy the entries).
8. Deploy the artifacts to the main folder of the gh-pages branch using `deploy -DaltDeploymentRepository=internal.repo::file://${basedir}`
9. Commit and push the gh-pages branch.

## Releases

### 3.2.0
- Updating Camunda Spring Boot to 3.2.0
- Updating Spring Boot to 2.1.1.RELEASE

### 3.1.0
- Updating Camunda to 7.10.0
- Updating Camunda Spring Boot to 3.1.0

### 3.0.0
- Updating Camunda to 7.9.0
- Updating Camunda Spring Boot to 3.0.0
- Updating Spring Boot to 2.0.2.RELEASE

### 2.0.7
- Default Maven goal `clean spring-boot:run`
- Camunda Modeler Element Template (not in archetype)

### 2.0.6
- A much nicer `deploy to Heroku` shield.

### 2.0.5
- Adding 'authorization: enabled: false' to application.yaml

### 2.0.4
- Adding application-local.yaml to .gitignore
- Updating application.yaml and application-heroku.yaml

### 2.0.3
- Adding a README.md file

### 2.0.2
- Adding a .gitignore file

### 2.0.1
- Adding a .gitignore template file

### 2.0.0
- Updating Camunda Spring Boot to 2.3.0
- Updating Spring Boot to 1.5.8.RELEASE

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
