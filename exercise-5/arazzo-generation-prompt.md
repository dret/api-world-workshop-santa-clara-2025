Please generate a valid Arazzo 1.0.1 document for the following use case:

**Workflow**: "Adopting a pet matching specific criteria"

**OpenAPI sources**:

- Pets Catalog API (name: PetsAPI): https://api.swaggerhub.com/apis/frank-kilcommins/Pets-Catalog-API/1.0.0/swagger.json
- Adoptions API (name: AdoptionsAPI): https://api.swaggerhub.com/apis/frank-kilcommins/Adoptions-API/1.0.0/swagger.json

**Workflow Steps**:

1. Search for pets matching user-defined criteria (e.g., breed = boxer, status = available).
2. Initiate an adoption request for a selected pet.
3. Confirm adoption by updating the pet's status.
4. Retrieve the pet again and verify it is marked as adopted.

Notes:

- Be detailed and precise.
- If a specific response structure is referenced, extract the necessary property (e.g., `adoptionId`, `petId`) for use in later steps.
- Ensure each step uses realistic runtime expressions in `requestBody` and `successCriteria`.