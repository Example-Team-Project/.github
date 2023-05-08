# Quarkus with Reactive and Native Image

[Quarkus](https://quarkus.io/) is a framework built on [Microprofile](https://microprofile.io/) standards. It is a Kubernetes-native Java framework tailored for GraalVM and HotSpot.

It aims to enable Java developers to create applications for a modern, cloud-native world.

## The setup

The services use the `quarkus-resteasy-reactive-jackson` dependency (which loads `quarkus-resteasy-reactive` transitively) for creating a reactive web service with JSON responses. The best source to create such a service is [the Quarkus guide](https://quarkus.io/guides/rest-json).

The services use specific port for local running which can be set by: `quarkus.http.port` setting.

## Using yaml for properties

Quarkus uses application.properties file by default. To support yaml file instead. With including the `io.quarkus:quarkus-config-yaml` dependency, the service is able to use `application.yaml`

## Base path setup

If the service requires a global prefix in the request URI (eg: every URI start with `/api`) there are 2 ways to set it.

1. Create a class extending the `jakarta.ws.rs.core.Application` then add the `@ApplicationPath("/api")` annotation
2. set the `quarkus.resteasy-reactive.path: /api` property.

