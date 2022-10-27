# Url shortener using Kafka Streams and CQRS pattern

Long URLs can be converted into shorter aliases via URL shortening. These condensed aliases are referred to as "short links." When users click on these short links, they are taken back to the original URL. When displayed, printed in a message, or tweeted, short links take up very little space. Shorter URLs are also less likely to be typed incorrectly by users.

## Prerequisites

This project includes a docker-compose file with zookeeper, three brokers, and a kafka cluster that must be running for it to function (3 brokers are enough to keep the cluster up and running).
## CQRS pattern

CQRS stands for Command and Query Responsibility Segregation, a pattern that separates read and update operations for a data store. Implementing CQRS can maximize performance of the application, scalability, and security. The flexibility created by migrating to CQRS allows a system to better evolve over time and prevents update commands from causing merge conflicts at the domain level.

## Interactive queries

Kafka Streams natively provides all of the required functionality for interactively querying the state of the application. \
A Kafka Streams application typically runs on multiple instances. The state that is locally available on any given instance is only a subset of the application’s entire state. Querying the local stores on an instance will only return data locally available on that particular instance. \

