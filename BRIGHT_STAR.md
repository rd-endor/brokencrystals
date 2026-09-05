# 🌟 Bright Star — Run Memory

<!-- BRIGHT_STAR_DATA — generated; do not edit -->
```json
{
  "version": 1,
  "generatedAt": "2026-09-05T07:19:02.851Z",
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
    "authObjectId": "rtqMZA8pwzdpXdodVZjiQK",
    "registration": {
      "baseUrl": "http://localhost:3000",
      "endpoint": "/api/users/basic",
      "method": "POST",
      "body": "{\"email\":\"bright@test.com\",\"firstName\":\"Bright\",\"lastName\":\"Test\",\"company\":\"Test\",\"cardNumber\":\"123\",\"phoneNumber\":\"555-1234\",\"password\":\"BrightTest123!\",\"op\":\"basic\"}",
      "contentType": "json"
    },
    "protectedResource": {
      "method": "GET",
      "url": "/api/users/one/bright@test.com/photo"
    }
  },
  "hints": {
    "startup": [
      "BrokenCrystals (NestJS+React) app: use `docker compose -f compose.local.yml up -d --build` which builds nodejs from source Dockerfile and starts db, keycloak(+db), mailcatcher, ollama, grpcwebproxy. App serves on host port 3000, readiness path /api/config returns 200. .env in repo root already has working boot secrets (JWT, keycloak client ids/secrets, etc.) - no changes needed. Full startup (build+all healthchecks) takes ~1-2 min."
    ]
  }
}
```
<!-- BRIGHT_STAR_DATA -->
