Story: As a potential adopter, I want to retrieve full details of a pet so that I can decide if it’s a good match for me.

Rules:
- Rule: A pet’s full details can be retrieved using its unique petId (UUID).
  Examples:
  - Jane accesses /pets/92b68c58-25ea-4f4e-a17b-c145c82e394a → The full pet record is returned, including name, category, breed, location, and status.

- Rule: If a pet with the specified petId does not exist, return a 404 Not Found.
  Examples:
  - Joe tries to access /pets/ffffffff-ffff-ffff-ffff-ffffffffffff → A 404 Not Found response is returned.

- Rule: This operation does not require authentication.
  Examples:
  - Jane accesses /pets/abc123 (valid format UUID) without credentials → The pet details are still returned.

- Rule: The response must include all available metadata about the pet.
  Examples:
  - Jane accesses /pets/1b2c3d4e-5f6a-789b-0c1d-2e3f4a5b6c7d → The response includes name, category, breed, location, status, description, and tags.

- Rule: Error responses must conform to RFC 9457.
  Examples:
  - Invalid UUID format (e.g. /pets/12345) → A 400 Bad Request is returned using ProblemDetails format.
  - Nonexistent petId → A 404 Not Found ProblemDetails response is returned.

Assumptions:
- The `petId` is a UUID (RFC 4122 format), provided as a path parameter.
- No authentication or authorization is required to retrieve pet details.
- A 200 OK is returned with a complete pet resource if the ID is valid and found.
- Standard RFC 9457-compliant error responses (400, 404) must be used for failures.