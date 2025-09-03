# API World 2025 (Santa Clara, CA)

This repo contains _exercises_ and _materials_ for the **"API Management in Practice: Delivering at Scale with OpenAPI and Arazzo"** Workshop at API World 2025 Conference in Santa Clara.

## Schedule

### 12:00-1:50: Part I

- 12.00-12.20: [Workshop Introduction](http://dret.net/lectures/api-world-2025/workshop-introduction)
- 12.20-12.50: [Introduction to APIs and API Descriptions](http://dret.net/lectures/api-world-2025/workshop-api-description)
- 12.50-1.20: [Capturing API Requirements using Example Mapping](http://dret.net/lectures/api-world-2025/workshop-api-requirements-example-mapping)
- 1.20-1.50: [Exercise 1](./exercise-1)


### 2:00-3:50: Part II

- 2.00-2.30: [Introduction to OpenAPI](http://dret.net/lectures/api-world-2025/workshop-openapi-introduction)
- 2.30-3.00: [The Art of Good API Documentation](http://dret.net/lectures/api-world-2025/workshop-api-documentation)
- 3.00-3.30: [Exercise 2](./exercise-2)
- 3.30-3.50: [API Design and OpenAPI Linting](http://dret.net/lectures/api-world-2025/workshop-design-linting)


### 4:20-6:00: Part III

- 4.20-4.45: [Exercise 3](./exercise-3)
- 4.45-5.05: [Introduction to API Mocking](http://dret.net/lectures/api-world-2025/workshop-mocking)
- 5.05-5.15: [Exercise 4](./exercise-4)
- 5.15-5.45: [Introduction to Arazzo](http://dret.net/lectures/api-world-2025/workshop-arazzo)
- 5.45-6.00: Certificates & Wrap-up


### 6:00: End of Workshop


## Slides

The slides presented during the workshop are available at [http://dret.net/lectures/api-world-2025/](http://dret.net/lectures/api-world-2025/).

For reference, the following parts make up the workshop:

- [Workshop Introduction](http://dret.net/lectures/api-world-2025/workshop-introduction)
- [Introduction to APIs and OpenAPI](http://dret.net/lectures/api-world-2025/workshop-api-description)
- [API Requirements and Example Mapping](http://dret.net/lectures/api-world-2025/workshop-api-requirements-example-mapping)
- [Introduction to OpenAPI](http://dret.net/lectures/api-world-2025/workshop-openapi-introduction)
- [The Art of Good API Documentation](http://dret.net/lectures/api-world-2025/workshop-api-documentation)
- [API Design and OpenAPI Linting](http://dret.net/lectures/api-world-2025/workshop-design-linting)
- [Intro to API Mocking](http://dret.net/lectures/api-world-2025/workshop-api-mocking)
- [Intro to the Arazzo Specification](http://dret.net/lectures/api-world-2025/workshop-arazzo)

## Tools

The following tools are either required or recommended as part of the exercises:

- [Swagger Editor](https://editor-next.swagger.io/)
- [Visual Studio Code](https://code.visualstudio.com/)
- [Docker](https://docs.docker.com/engine/install/)
- [Spectral](https://github.com/stoplightio/spectral)
- [Spectral VSCode Extension](https://marketplace.visualstudio.com/items?itemName=stoplight.spectral)
- [Prism](https://github.com/stoplightio/prism)
- [Arazzo Specification GPT](https://chatgpt.com/g/g-673339c216648190a97a5fa3d8258769-arazzo-specification)
- [Arazzo Editor](https://arazzo-editor.symplr.io/)

## Prerequisites

Set up the tools above and/or accounts where required.

## Exercises

### Exercise 1

Given a "Retrieve Pet Details" user story, break into groups and carry out an Example Mapping session as outlined in the [API Requirements and Example Mapping](http://dret.net/lectures/api-world-2025/workshop-api-requirements-example-mapping) module.

This is a practical session and the appropriate equipment will be provided (cards, pens, etc.). The expected and/or sample outputs are available in the [exercise-1](./exercise-1/) folder.

### Exercise 2

Using the _Example Mapping_ output for "Retrieve Pet Details" from exercise 1 to create an OpenAPI Description that exposes the capability as an endpoint.

Tooling of your choice:

- https://editor-next.swagger.io
- VS Code (or your IDE of choice)
- ChatGPT or any other AI assistant

Expected output is an OpenAPI Description in either YAML or JSON format!

The expected and/or sample outputs are available in the [exercise-2](./exercise-2/) folder.

### Exercise 3

Create a spectral file to validate the OpenAPI description created in exercise 2. Ensure that you can address any issues such that your OpenAPI description is valid with the core ruleset.

Disable certain rules and revalidate.

Create a custom rule to ensure that path parameters are "snake_case"

### Exercise 4

Using the OpenAPI descriptions from previous exercises (or as listed in [exercise-4](./exercise-4/)), use prism to mock the endpoints.

This can be done using Docker or on the participates local device.

Use the commands laid out in the [Make file](./exercise-4/Makefile) and validate that the mocks are running.

Send `curl` requests to exercise the mocks.

### Exercise 5

Generate an Arazzo Document to specify the following workflow:

**Workflow Steps**:

1. Search for pets matching user-defined criteria (e.g., breed = boxer, status = available).
2. Initiate an adoption request for a selected pet.
3. Confirm adoption by updating the pet's status.
4. Retrieve the pet again and verify it is marked as adopted.

The following APIs should act as the source descriptions:

**OpenAPI sources**:

- Pets Catalog API (name: PetsAPI): https://api.swaggerhub.com/apis/frank-kilcommins/Pets-Catalog-API/1.0.0/swagger.json
- Adoptions API (name: AdoptionsAPI): https://api.swaggerhub.com/apis/frank-kilcommins/Adoptions-API/1.0.0/swagger.json

You can generate by hand using an [Arazzo Editor](https://arazzo-editor.symplr.io/) or use the [Arazzo Specification GPT](https://chatgpt.com/g/g-673339c216648190a97a5fa3d8258769-arazzo-specification), or indeed any LLM of choice.

Once generated, lint the Arazzo document using Spectral, and also validate that it renders in [Arazzo Editor](https://arazzo-editor.symplr.io/).
