# Spring boot micro-service example with secure ssl layer
This is the spring boot micro service example project with https
# Getting started / Usage Guide
- Clone the source code from the git repo.
- Navigate to resouce directory and generate keystore.jsk file using below keytool command in commond prompt and provide neccessary information
```sh
       > keytool -genkey -alias https-example -storetype JKS -keyalg RSA -keysize 2048 -validity 365 -key-store keystore.jks
```
[Make sure the key-store file with name keystore.jks in the resource directory]
- Update application.yml file accordingly for example,
>server:
>  port: 9090
>  ssl:
>    key-alias: https-example
>    key-store-type: JKS
>    key-store-password: Keystore@123
>    key-store: classpath:keystore.jks
>
- Run below mvn command to run the application
```sh
       > mvn clean install
       > mvn spring-boot:run
```
- Access the application by clicking [here](https://localhost:9090/actuator/health)