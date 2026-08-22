# REST Assured

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
