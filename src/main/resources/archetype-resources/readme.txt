#set( $symbol_pound = '#' )
#set( $symbol_dollar = '$' )
#set( $symbol_escape = '\' )
App Application

This project was generated using the `gwt-maven-springboot-archetype`!

======================================================================

To run the examples:

* run in one terminal window:

  - mvn clean package

  - mvn gwt:codeserver -pl *-client -am

Wait until codeserver is startet (it is started, in case you see the codeserver url). after a `mvn clean package` is this necessary because the `launcherdir` has to be created inside the Spring Boot server.

* in another terminal window:

  - mvn spring-boot:run -pl *-server -am

To start the application, call:

http://localhost:8080/index.html
