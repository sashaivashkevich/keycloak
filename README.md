# Keycloak. How to expand jwt token 

Example Custom protocol mapper 
==============================
You can add custom dynamic user attributes to the JWT tokens. Example, you can expan jwt token by querying your custom database.

Deploy
------

To run, deploy as a module by running:

$KEYCLOAK_HOME/bin/jboss-cli.bat --command="module add --name=org.keycloak.examples.custom-protocol-mapper --resources=target/custom-protocol-mapper.jar --dependencies=org.keycloak.keycloak-core,org.keycloak.keycloak-services,org.keycloak.keycloak-model-jpa,org.keycloak.keycloak-server-spi,org.keycloak.keycloak-server-spi-private,javax.ws.rs.api,javax.persistence.api,org.hibernate,org.javassist,org.liquibase"


Then registering the provider by editing `standalone/configuration/standalone.xml` and adding the module to the providers element:

    <providers>
        ...
        <provider>module:org.keycloak.examples.custom-protocol-mapper</provider>
    </providers>

Then start (or restart) the server.

Testing
-------