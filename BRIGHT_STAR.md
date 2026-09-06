# 🌟 Bright Star — Run Memory

<!-- BRIGHT_STAR_DATA — generated; do not edit -->
```json
{
  "version": 1,
  "generatedAt": "2026-09-06T13:26:07.230Z",
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
    "command": "docker compose --file=compose.local.yml up -d --build",
    "port": 3000,
    "prerequisites": [],
    "envVars": {},
    "healthCheckPath": "/api/config"
  },
  "setup": {
    "completed": false
  },
  "auth": {
    "hasAuth": true,
    "authObjectId": "ovd1o6RXqcbDdzMR6AC6fE",
    "registration": {
      "baseUrl": "http://localhost:3000",
      "endpoint": "/api/users/basic",
      "method": "POST",
      "body": "{\"email\":\"testuser@example.com\",\"firstName\":\"Test\",\"lastName\":\"User\",\"password\":\"TestPassword123\",\"company\":\"Test Co\",\"cardNumber\":\"1234567890123456\",\"phoneNumber\":\"555-1234\",\"op\":\"basic\"}",
      "contentType": "json"
    },
    "protectedResource": {
      "method": "GET",
      "url": "/api/users/me"
    }
  },
  "hints": {
    "startup": [
      "Successfully started with: docker compose --file=compose.local.yml up -d --build. All services (db, keycloak, ollama, mailcatcher, nodejs) are healthy. App serves on http://localhost:3000 with REST API, GraphQL, and Swagger UI all functional. Health check endpoint: /api/config returns 200."
    ]
  }
}
```
<!-- BRIGHT_STAR_DATA -->
