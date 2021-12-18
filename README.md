# Kubernetes And Spring Boot

Steps

* clone the project
* Build The Image: ./mvnw spring-boot:build-image -Dspring-boot.build-image.imageName=${docker_reg_username}/${project_name}
* [Create an OCI image](https://docs.spring.io/spring-boot/docs/2.6.1/maven-plugin/reference/html/#build-image)
* [Spring Boot Actuator](https://docs.spring.io/spring-boot/docs/2.6.1/reference/htmlsingle/#production-ready)

### Guides
The following guides illustrate how to use some features concretely:

* [Building a RESTful Web Service with Spring Boot Actuator](https://spring.io/guides/gs/actuator-service/)

