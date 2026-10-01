# medicore-service-registry

Netflix **Eureka** service discovery server for the **MediCore** healthcare platform
([monorepo](https://github.com/Vamshikrishna720/medicore) · Spring Boot 3 microservices + React).

All MediCore services register here; the API gateway and Feign clients resolve them
by name (`lb://AUTH-SERVICE`, …) instead of hard-coded hosts.

## Run

```bash
mvn spring-boot:run
# Dashboard: http://localhost:8761
```

## Configuration

| Env var | Default | Purpose |
|---|---|---|
| `SERVER_PORT` | 8761 | Registry port |

Start this **first** — every other MediCore service expects `EUREKA_URI`
(default `http://localhost:8761/eureka`) at startup.
