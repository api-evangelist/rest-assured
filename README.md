# REST Assured

REST Assured is a Java library for simplifying the testing and validation of RESTful APIs. It provides a fluent domain-specific language (DSL) built on the given-when-then BDD pattern, making it easy to write readable and maintainable API tests. REST Assured supports HTTP methods GET, POST, PUT, DELETE, OPTIONS, PATCH, and HEAD, along with JSON and XML response validation, JSONPath and XmlPath parsing, multiple authentication schemes, Spring MockMvc integration, and full request/response logging. Version 6.0.0 (December 2025) requires Java 17+ and integrates with Groovy 5, Spring 7, and Jackson 3.

**Website:** [rest-assured.io](https://rest-assured.io)  
**GitHub:** [github.com/rest-assured/rest-assured](https://github.com/rest-assured/rest-assured)  
**Maven Central:** `io.rest-assured:rest-assured`

## Tags

`Functional Testing` `Testing` `Java` `API Testing` `Automation` `BDD` `DSL`

## Timestamps

- **Created:** 2026-03-25
- **Modified:** 2026-05-02

## APIs

| Name | Description | URL |
|---|---|---|
| REST Assured | Java DSL for testing and validating RESTful APIs | [rest-assured.io](https://rest-assured.io) |

## Artifacts

| Type | Name | Link |
|---|---|---|
| Documentation | Official Docs | [rest-assured.io/#docs](https://rest-assured.io/#docs) |
| Getting Started | Wiki — GettingStarted | [GitHub Wiki](https://github.com/rest-assured/rest-assured/wiki/GettingStarted) |
| Usage Guide | Wiki — Usage | [GitHub Wiki](https://github.com/rest-assured/rest-assured/wiki/Usage) |
| JSON Schema | Request Specification Schema | [json-schema/rest-assured-request-schema.json](json-schema/rest-assured-request-schema.json) |
| JSON Schema | Response Specification Schema | [json-schema/rest-assured-response-schema.json](json-schema/rest-assured-response-schema.json) |
| JSON Structure | Request Structure | [json-structure/rest-assured-request-structure.json](json-structure/rest-assured-request-structure.json) |
| JSON-LD Context | REST Assured Context | [json-ld/rest-assured-context.jsonld](json-ld/rest-assured-context.jsonld) |
| Vocabulary | REST Assured Vocabulary | [vocabulary/rest-assured-vocabulary.yml](vocabulary/rest-assured-vocabulary.yml) |
| Example | GET Request Example | [examples/rest-assured-get-user-example.json](examples/rest-assured-get-user-example.json) |
| Example | POST Request Example | [examples/rest-assured-post-user-example.json](examples/rest-assured-post-user-example.json) |

## Quick Example

```java
import static io.restassured.RestAssured.*;
import static org.hamcrest.Matchers.*;

given()
    .baseUri("https://api.example.com")
    .header("Authorization", "Bearer " + token)
    .pathParam("id", 42)
.when()
    .get("/v1/users/{id}")
.then()
    .statusCode(200)
    .body("name", equalTo("Jane Doe"))
    .body("email", notNullValue());
```

## Key Features

- **Given-When-Then BDD pattern** for readable test structure
- **JSONPath and XmlPath** for response parsing and assertion
- **Spring MockMvc integration** for testing without an HTTP server
- **Multiple authentication schemes** — Basic, Digest, OAuth2, Certificate
- **Request/Response logging** for debugging
- **Hamcrest matchers** for expressive assertions
- **RequestSpecBuilder and ResponseSpecBuilder** for reusable specifications

## Maven Dependency

```xml
<dependency>
    <groupId>io.rest-assured</groupId>
    <artifactId>rest-assured</artifactId>
    <version>6.0.0</version>
    <scope>test</scope>
</dependency>
```

## Maintainers

**Kin Lane** — kin@apievangelist.com
