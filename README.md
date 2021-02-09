# Spring-Cloud-Config-Server

The spring-boot project to demonstrate Spring cloud config server by accesing the configuration from a git repo [config-repo](https://github.com/santhoshvernekar/config-repo)

### To Build project:
run mvn clean install

### Steps:
* [optional] To check the service getting registered with service discovery, we need to run the service discovery on our machine, You can find project in my repo [eureka-service-discovery](https://github.com/santoshmv121/eureka-discovery-server)
* Step 1: Launch the service discovery
* Step 2: Update spring.cloud.config.server.git.uri property in properties file/yaml to the git/svn repo from which you want to access the configuration properties (sample: spring.cloud.config.server.git.uri=https://github.com/santhoshvernekar/config-repo.git)
* Step 3: Launch the config-server application
* Step 4: Spring-cloud-config server provides REST based feature to access the configuration,

The request should be in the format of: config-server-URL/app-name/profile/{label}
* app-name: The name of the application (Mandatory)
* profile: The spring-profile set while defining the configuration ex: prod,dev,default, by default we can mention  value as "default" (Mandatory)
* label: An Optional parameter to specify the different labels defined

We can get the configurations in the desired format (Supported formats: json/yaml/properties )

For Example: Config server is running on localhost 8888 port, so we can retrieve the configurations with below requests 
* http://localhost:8888/config-server/prod
* http://localhost:8888/config-server.prod.properties
* http://localhost:8888/config-server.dev.yaml
* http://localhost:8888/config-server/default


Happy Coding!!

### Reference Documentation
For further reference, please consider the following sections:

* [Official Apache Maven documentation](https://maven.apache.org/guides/index.html)
* [Spring Boot Maven Plugin Reference Guide](https://docs.spring.io/spring-boot/docs/2.4.2/maven-plugin/reference/html/)
* [Create an OCI image](https://docs.spring.io/spring-boot/docs/2.4.2/maven-plugin/reference/html/#build-image)
* [Eureka Discovery Client](https://docs.spring.io/spring-cloud-netflix/docs/current/reference/html/#service-discovery-eureka-clients)
* [Spring Boot Actuator](https://docs.spring.io/spring-boot/docs/2.4.2/reference/htmlsingle/#production-ready)
* [Spring Web](https://docs.spring.io/spring-boot/docs/2.4.2/reference/htmlsingle/#boot-features-developing-web-applications)

### Guides
The following guides illustrate how to use some features concretely:

* [Centralized Configuration](https://spring.io/guides/gs/centralized-configuration/)
* [Service Registration and Discovery with Eureka and Spring Cloud](https://spring.io/guides/gs/service-registration-and-discovery/)
* [Building a RESTful Web Service with Spring Boot Actuator](https://spring.io/guides/gs/actuator-service/)
* [Building a RESTful Web Service](https://spring.io/guides/gs/rest-service/)
* [Serving Web Content with Spring MVC](https://spring.io/guides/gs/serving-web-content/)
* [Building REST services with Spring](https://spring.io/guides/tutorials/bookmarks/)

