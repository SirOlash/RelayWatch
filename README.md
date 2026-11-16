# RelayWatch

RelayWatch backend bootstrap using Java 21 and Spring Boot 4.1.2.

## Prerequisites

- JDK 21, with `JAVA_HOME` pointing to it and its `bin` directory on `PATH` in the terminal running Maven.
- Internet access for the initial download of Maven and dependencies.

The Maven Wrapper is included, so a separate Maven installation is unnecessary.

## Run locally

Run these commands from the repository root using Windows PowerShell:

```powershell
.\mvnw.cmd spring-boot:run
```

The application starts on port 8080. Stop it with Ctrl + C.

## Run tests

```powershell
.\mvnw.cmd test
```

This runs the application-context smoke test.

## Check health

With the application running, open another PowerShell terminal:

```powershell
Invoke-WebRequest -Uri 'http://localhost:8080/actuator/health' -UseBasicParsing |
  Select-Object StatusCode, Content
```

Expected HTTP status: `200`

Expected response:

```json
{"status":"UP"}
```
