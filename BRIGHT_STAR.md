# 🌟 Bright Star — Run Memory

<!-- BRIGHT_STAR_DATA — generated; do not edit -->
```json
{
  "version": 1,
  "generatedAt": "2026-09-05T13:13:32.919Z",
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
    "authObjectId": "1mYFo3ZRLkgbuz391hxgcm",
    "protectedResource": {
      "method": "GET",
      "url": "/api/users/one/bright@test.com/photo"
    }
  },
  "hints": {
    "startup": [
      ".env file exists and provides required DATABASE_*, JWT_*, JWK_*, KEYCLOAK_*, and other config variables. compose.local.yml builds from Dockerfile and runs: Node 18-alpine, npm run build:fast, then npm run start:prod (node dist/main.js).",
      "Successfully started with: docker compose --file=compose.local.yml up -d --build. App serves on localhost:3000. Health check passes at /api/config (returns JSON with config). Swagger UI at /swagger."
    ]
  }
}
```
<!-- BRIGHT_STAR_DATA -->
