# 🌟 Bright Star — Run Memory

<!-- BRIGHT_STAR_DATA — generated; do not edit -->
```json
{
  "version": 1,
  "generatedAt": "2026-09-07T13:42:31.877Z",
  "techStack": {
    "languages": [
      "JavaScript",
      "TypeScript"
    ],
    "frameworks": [
      "NestJS"
    ],
    "databases": [
      "PostgreSQL"
    ]
  },
  "startup": {
    "command": "docker compose -f compose.local.yml up -d --build",
    "port": 3000,
    "prerequisites": [],
    "envVars": {},
    "healthCheckPath": "/api/config"
  },
  "setup": {
    "completed": true,
    "credentials": {
      "username": "bright_test",
      "password": "BrightTest123!",
      "email": "bright@test.com"
    }
  },
  "auth": {
    "hasAuth": true,
    "authObjectId": "f3A4SZkpYGWk3HnkBxh3zm",
    "registration": {
      "baseUrl": "http://localhost:3000",
      "endpoint": "/api/users/basic",
      "method": "POST",
      "body": "{\"email\":\"bright@test.com\",\"password\":\"BrightTest123!\",\"firstName\":\"Bright\",\"lastName\":\"Test\",\"company\":\"BrightSec\",\"cardNumber\":\"1234567890123456\",\"phoneNumber\":\"+1234567890\",\"op\":\"basic\"}",
      "contentType": "json"
    },
    "protectedResource": {
      "method": "GET",
      "url": "/api/users/one/bright@test.com/info"
    }
  },
  "limits": {
    "scanPrepReplayCommands": [
      {
        "container": "brokencrystals-keycloak-db-1",
        "command": "psql -U keycloak -d keycloak -c \"SELECT username, email, enabled FROM user_entity LIMIT 10;\""
      }
    ]
  },
  "hints": {
    "startup": [
      "NestJS app with React client, runs on port 3000. Uses Postgres DB (bc:bc@db:5432), Keycloak auth (port 8080), and Ollama (port 11434). Start with: docker compose --file=compose.local.yml up -d --build. Healthcheck: GET /api/config on localhost:3000.",
      "Successfully started Broken Crystals with docker compose -f compose.local.yml up -d --build. App serves on http://localhost:3000. All dependencies (PostgreSQL, Keycloak, Ollama, MailCatcher) are healthy. Verified endpoints: GET /api/config, GET /, GET /swagger all responding 200."
    ]
  }
}
```
<!-- BRIGHT_STAR_DATA -->
