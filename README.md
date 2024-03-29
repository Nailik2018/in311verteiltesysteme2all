# Quarkus Kafka Blog und Message Servers

## 1. Einleitung
In diesem Projekt wird ein Blog und ein Message Server implementiert. Der Blog ist ein Quarkus Projekt, welches die Posts von einem Kafka Server konsumiert und anzeigt. Der Message Server ist ebenfalls ein Quarkus Projekt, welches die Posts an den Kafka Server sendet.

## 2. Voraussetzungen und Installation
- Docker
- docker-compose up -d

## Verwendete Ports
- 8080: Blog Backend
- 8081: Messenger Backend
- 18081: Redpanda
- 9092: Kafka Server
- 8181: PhpMyAdmin (http://localhost:8181) benutzer: blogger, passwort: travel
- 3306: MySQL

## 3. Blog Backend API über httpie oder swagger
```
http://localhost:8080/q/dev-ui/io.quarkus.quarkus-smallrye-openapi/swagger-ui

Rückgabe aller Posts
http :8080/blog

valid = false
http :8080/blog/validate title=india content=namaste

valid = true
http :8080/blog/validate title=blog content="travel in bangladesch"
http :8080/blog/validate title=bangladesch content="honey hunting"
```

## Bemerkungen
```
Der Webserver funktioniert nur bedingt. Daten von Blog init werden in die DB geschrieben, Webserver aufruf funktioniert aber nicht.
```