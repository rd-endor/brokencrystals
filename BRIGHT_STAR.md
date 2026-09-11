# 🌟 Bright Star — Run Memory

<!-- BRIGHT_STAR_DATA — generated; do not edit -->
```json
{
  "version": 1,
  "generatedAt": "2026-09-11T11:02:29.736Z",
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
    "command": "docker compose -f compose.local.yml --env-file .env up -d --build",
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
    "authObjectId": "1WfSrZiv1uaHuC2iiDBkrP",
    "protectedResource": {
      "method": "GET",
      "url": "/api/users/one/bright@test.com/photo"
    }
  },
  "hints": {
    "startup": [
      "brokencrystals app: use compose.local.yml (docker compose -f compose.local.yml --env-file .env up -d --build) which builds nodejs service from local Dockerfile plus db, keycloak, mailcatcher, ollama, grpcwebproxy. nodejs container listens on 0.0.0.0:3000, healthcheck/readiness path is GET /api/config (returns 200). No extra env vars needed beyond repo's .env."
    ]
  }
}
```
<!-- BRIGHT_STAR_DATA -->
