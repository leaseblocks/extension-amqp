# AMQP extension agent instructions

- This is the LeaseBlocks fork; use local [pom.xml](pom.xml) versions rather than copying dependency versions from sibling extensions.
- Keep event conversion and transport in [amqp](amqp/), and Spring Boot wiring in [amqp-spring-boot-autoconfigure](amqp-spring-boot-autoconfigure/).
- Honor module compiler settings: the core inherits Java 8 source/target; the Boot integration modules declare their own Java settings.
- When changing publishing, review `SpringAMQPPublisher` transaction, confirm, rollback, and channel cleanup paths, including execution with and without an Axon Unit of Work.
- Review message conversion and routing keys on both publisher and consumer paths; this extension transports events and does not provide an event store.
- Validate Spring Boot wiring in the Boot 3 and Boot 4 integration modules activated by `java17-modules` on JDK 17+. RabbitMQ integration checks use Testcontainers and require Docker.
- Keep upstream license notices and attribution. Build commands and the example application are linked in [README.md](README.md).
