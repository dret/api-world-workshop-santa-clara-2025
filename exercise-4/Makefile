OAS_PETS_FILE?=pets-catalog.openapi.yaml
OAS_ADOPTIONS_FILE?=pet-adoptions.openapi.yaml


provider_mock_pets: ## Runs a mock server with Prism, generated from the OpenAPI specification
	docker run --add-host=host.docker.internal:host-gateway -d --init --rm --name prismPets -v ${PWD}:/specs -p 8084:4010 stoplight/prism:latest mock -h 0.0.0.0 "/specs/${OAS_PETS_FILE}"

request-pets:
	curl localhost:8084/pets --header "Accept: application/json"

provider_mock_adoptions: ## Runs a mock server with Prism, generated from the OpenAPI specification
	docker run --add-host=host.docker.internal:host-gateway -d --init --rm --name prismAdoptions -v ${PWD}:/specs -p 8085:4010 stoplight/prism:latest mock -h 0.0.0.0 "/specs/${OAS_ADOPTIONS_FILE}"

request-adoptions:
	curl localhost:8085/adoptions --header "Accept: application/json"

prism-pets-logs:
	docker logs --tail 10 -f prismPets

request-post-pet:
	curl -X POST localhost:8084/pets \
	-H "Content-Type: application/json" \
	-H "Accept: application/json" \
	-H "Authorization: secretKey" \
	-d '{
		"name": "Buddy",
		"category": "dog",
		"breed": "boxer",
		"location": "Galway"
	}'

request-post-pet-bad:
	curl -X POST localhost:8084/pets \
	-H "Content-Type: application/json" \
	-H "Accept: application/json" \
	-H "Authorization: secretKey" \
	-d '{
		"petId": "1"
	}'	

