# Axon Framework — AMQP Extension

Axon event publishing and consumption over AMQP, including RabbitMQ integration. This extension handles event transport; it does not provide an event store.

This is the LeaseBlocks fork of [AxonFramework/extension-amqp](https://github.com/AxonFramework/extension-amqp), included as a submodule in the LeaseBlocks workspace. [pom.xml](pom.xml) defines this checkout's artifact and dependency versions.

## Build and test

Use JDK 17 or later and the checked-in Maven wrapper from this directory:

```sh
./mvnw clean verify
./mvnw -Dcoverage clean verify
```

On JDK 17+, the `java17-modules` profile automatically includes the Spring Boot 3 and Spring Boot 4 integration-test modules. The `coverage` property adds the aggregate coverage module. Dependency and plugin versions are maintained in the parent and module POMs.

Integration tests use Testcontainers and require Docker.

## Modules

- [amqp](amqp/): core extension.
- [amqp-spring-boot-autoconfigure](amqp-spring-boot-autoconfigure/): Spring Boot configuration.
- [amqp-spring-boot-starter](amqp-spring-boot-starter/): starter dependency bundle.
- [amqp-spring-boot-3-integrationtests](amqp-spring-boot-3-integrationtests/) and [amqp-spring-boot-4-integrationtests](amqp-spring-boot-4-integrationtests/): framework integration checks.
- [coverage-report](coverage-report/): aggregate coverage reports.
- [amqp-axon-example](amqp-axon-example/README.md): example application.

## Documentation and license

See the [local documentation](docs/README.md) and [upstream reference guide](https://docs.axoniq.io/amqp-extension-reference/latest/). The upstream guide follows its own release; check this checkout's source and POMs when behavior differs.

Upstream support: [AxonIQ forum](https://discuss.axoniq.io/) and [issue tracker](https://github.com/AxonFramework/extension-amqp/issues).

Licensed under [Apache 2.0](LICENSE.txt).
