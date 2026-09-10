# 🌟 Bright Star — Run Memory

<!-- BRIGHT_STAR_DATA — generated; do not edit -->
```json
{
  "version": 1,
  "generatedAt": "2026-09-10T13:40:52.237Z",
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
    "completed": true,
    "credentials": {
      "username": "bright_test",
      "password": "BrightTest123!",
      "email": "bright@test.com"
    }
  },
  "auth": {
    "hasAuth": true,
    "authObjectId": "kKVbVsL1nKT2EifwaSQdYR",
    "protectedResource": {
      "method": "GET",
      "url": "/api/auth/jwt/rsa/signature/validate"
    }
  },
  "hints": {
    "startup": [
      "Broken Crystals is a NestJS application. Start with: docker compose --file=compose.local.yml up -d --build. App runs on port 3000 with healthcheck at /api/config. Depends on PostgreSQL, Keycloak, Mailcatcher, and Ollama services.",
      "Application started successfully using docker compose --file=compose.local.yml up -d --build. All services are healthy and running. App is accessible on port 3000 with health endpoint at /api/config. Swagger API available at /swagger-json."
    ]
  }
}
```
<!-- BRIGHT_STAR_DATA -->
