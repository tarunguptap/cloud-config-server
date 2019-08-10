## Lab 3 - Create a Spring Cloud Config Server and Client

**Part 1 - Config Server:**

1. Create a new Spring Boot application.  Name the project "cloud-config-server”, and use this value for the Artifact.  Use Jar packaging and the latest versions of Java.  Use a version of Boot > 2.0.x.   select Cloud Config dependency.

1. Add a dependency for group "org.springframework.cloud" and artifact "spring-cloud-config-server".  You do not need to specify a version -- this is already defined in the spring-cloud-dependencies BOM.

1. Edit the main Application class (probably named Lab3ServerApplication).  Add the @EnableConfigServer to this class.

1. Create a new repository on GitHub to hold your application configuration data.  Call the repository "cloud-config-repo" or a name of your choosing.  Note the full URI of the repository, you will need this in a following step.

1. Add a new file to your GitHub repository called "cloud-config-client.yml”.  Add a key called "lucky-word" and a value "Tarun", or any other value of your choosing.

1. Back in your project, create an application.yml (or application.properties) file in the root of your classpath (src/main/resources).  Add the key "spring.cloud.config.server.git.uri" and the value "https://github.com/tarunguptap/config-server-repo"  

1. Also within application.yml (or application.properties), set the “server.port” to 8001.

8. Run the application.  Open the URL [http://localhost:8001/cloud-config-client/default/].  You should see the JSON result that will actually be used by Spring.  If the server is not working, review the prior steps to find the issue before moving on.