# Greetings Micro Service Repository

This repository contains the Greetings micro service.

## Requests

The following HTTP requests are covered:

- GET /greetings/hello - respond with `Hello World!` greeting

- GET /greetings/hello/{name} with `name` as a path variable - respond with `Hello ${name} World!` greeting

- POST /greetings/hello with `name` in the body of the request - respond with `Hello ${name} World!` greeting, if the greetings has NOT yet been created; respond with `Hello ${name} World!  Your name was previously saved.` otherwise.

- GET/POST /greetings/* - respond with a message related to `Status 404 ...`


If you uses greetings:jar image then  you shouldn't use the context /greetings, only /

## Technology

- Java 1.8
- Spring Boot
- Maven - to build only
- Tomcat - Dockerized
- AWS Elastic Beanstalk - buildspec.yml - `ignore for now`

## Build Commands

The following commands build a WAR file to be deployed to a dockerized Tomcat.

### JAR File

```sh

mvn clean package install
```

### Docker Container

```sh

docker build -t greetings:jar -f Dockerfile-jar .

and 

docker run -d -p 8080:8080 --name ms-greetings --restart unless-stopped --log-opt max-size=5m --log-opt max-file=3 --memory 200m --cpus=".3" greetings:jar
```
https://docs.docker.com/config/containers/resource_constraints/

## Integration Tests

## Location

>src/test/postman/  
|-- Autotrader.postman_test_run_2019-11-22.json  
|-- Autotrader.postman_tests_2019-11-21.json  
|-- test_results_screenshot_2019-11-22.jpg  

[Postman](https://www.getpostman.com/) is the tool of choice. You can import the test suite from the following file:

- `/greetings-microservice-repo/src/test/posman/Autotrader.postman_tests_2019-11-21.json`

## Sample Test Run

Here is a screenshot from sample run of this test suite (the JSON is also available alongside the test suite mentioned above):

![Autotrader Integration Tests Run](src/test/postman/test_results_screenshot_2019-11-22.jpg)

## GitHub Automation

_GitHub Webhook_  
![GitHub Webhook](notes/github_webkook.jpg)
Testing GitHub and Jenkins integration
Line 2
Line 3
Multi-branch scan trigger 1
Multi-branch scan trigger 2
Multi-branch scan trigger 3
Multi-branch scan trigger 4

###
Testing a webhook & Jenkins integration..
