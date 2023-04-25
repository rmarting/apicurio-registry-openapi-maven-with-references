# Apicurio Registry - OpenAPI Sample with Schema References

This repo includes a sample to publish and consume an OpenAPI spec with schema references.

## Running Apicurio Service Registry

To run locally a Apicurio Registry using `podman`:

```shell
podman run -it -p 8080:8080 apicurio/apicurio-registry-mem:2.4.2.Final
```

Apicurio Registry will be available at `http://localhost:8080` endpoint.

## Publishing Artifacts

The [openapi-spec-maven-with-references](./openapi-spec-maven-with-references/) folder includes
a OpenAPI spec with a reference of a JSON schema. This project is used to define the API and
publish the artifacts into a Apicurio Registry.

To publish the artifacts, execute this command inside that folder:

```shell
mvn verify
```

To deploy the artifacts into a different Apicurio Registry, the
`apicurio-registry.url` property can be used:

```shell
mvn verify -Dapicurio-registry.url=http://apicurio-registry:8080
```

## Consuming Artifacts

The [openapi-client-maven-with-references](./openapi-client-maven-with-references/) folder
represents a consumer of the OpenAPI spec with a reference. This example download the artifacts
related to the OpenAPI spec published in Apicurio Registry.

To download the artifacts, execute this command inside of that folder:

```shell
mvn verify
```

To download the artifacts from a different Apicurio Registry, the
`apicurio-registry.url` property can be used:

```shell
mvn verify -Dapicurio-registry.url=http://apicurio-registry:8080
```

## References

* [References to other schemas and APIs](https://www.apicur.io/registry/docs/apicurio-registry/2.4.x/getting-started/assembly-intro-to-the-registry.html#_references_to_other_schemas_and_apis)
* [Adding artifact references using the Apicurio Registry Maven plug-in](https://www.apicur.io/registry/docs/apicurio-registry/2.4.x/getting-started/assembly-managing-registry-artifacts-maven.html#adding-artifact-references-using-maven-plugin_registry)
