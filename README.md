# gwt-maven-sogis-archetype

This project contains a Maven archetype for modular GWT projects using Spring Boot. The repo is based on the implementation of NanuKit's [gwt-maven-springboot-archetype](https://github.com/NaluKit/gwt-maven-springboot-archetype) and Thomas Broyer's [gwt-maven-archetypes](https://github.com/tbroyer/gwt-maven-archetypes).

If you are looking for the original archetype creator or would prefer another backend/implementation, please visit:  [gwt-maven-archetypes](https://github.com/tbroyer/gwt-maven-archetypes).


## How to use

### Generate a project
Until the archetype is released/published, you have to check it out from the github repository:

```
git clone https://github.com/edigonzales/gwt-maven-sogis-archetype.git
cd gwt-maven-sogis-archetype && mvn clean install
```

You'll then use the `mvn archetype:generate` command:

```
mvn org.apache.maven.plugins:maven-archetype-plugin:2.2:generate \
   -DarchetypeGroupId=com.github.sogis.archetype \
   -DarchetypeVersion=HEAD-SNAPSHOT \
   -DarchetypeArtifactId=modular-springboot-webapp
```

### Develop
First terminal:
```
mvn spring-boot:run -Penv-dev -pl *-server -am
```

Second terminal:
```
mvn gwt:codeserver -pl *-client -am
```

Or without downloading all the snapshots again:

```
mvn gwt:codeserver -pl *-client -am -nsu
```

## Build
TODO

## Compatibility

To use variable interpolation in parameters during `mvn archetype:generate`, you need at least version 2.2 of the maven-archetype-plugin. Archetypes use `${module.toLowerCase()}` as the default value for the `module-short-name` parameter, so if you don't use version 2.2 or above of the maven-archetype-plugin, make sure you provide a value and do not use the default one for that parameter. You can also make sure you use version 2.2 of the plugin by using `mvn org.apache.maven.plugins:maven-archetype-plugin:2.2:generate` instead of `mvn archetype:generate`. It should be noted that variable interpolation also does not work in M2Eclipse's wizard, despite using recent versions of Maven thus (probably) a recent-enough version of the maven-archetype-plugin.

## todo
- Funktionert das Entpacken beim Builden?
  * ${module-short-name} im Profile
- Dockerfiles parametrisieren
- GraalVM
  * v0.8.5 ist für v2.4.1
  * Funktioniert Parametrisierung von main class?
- Div-Element (Platzhalter für Suche) in Karte.
- maven-surefire-plugin: Braucht es das noch, falls es von Beginn weg einen Test gibt?
- Docs
  * docker build