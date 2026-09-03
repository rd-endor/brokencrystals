# 🌟 Bright Star — Run Memory

<!-- BRIGHT_STAR_DATA — generated; do not edit -->
```json
{
  "version": 1,
  "generatedAt": "2026-09-03T18:48:07.223Z",
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
    "authObjectId": "6zFt7rsD2WwCJPa2Ca8kdv",
    "registration": {
      "baseUrl": "http://localhost:3000",
      "endpoint": "/api/users/basic",
      "method": "POST",
      "body": "{\"email\":\"bright@test.com\",\"firstName\":\"Bright\",\"lastName\":\"Test\",\"company\":\"Test\",\"cardNumber\":\"123\",\"phoneNumber\":\"555-1234\",\"password\":\"BrightTest123!\",\"op\":\"basic\"}",
      "contentType": "json"
    },
    "protectedResource": {
      "method": "GET",
      "url": "/api/users/me"
    }
  },
  "hints": {
    "startup": [
      "BrokenCrystals (NestJS) repo: use `docker compose -f compose.local.yml up -d --build` (builds nodejs from local Dockerfile, unlike compose.yml which pulls prebuilt image 'brightsec/brokencrystals'). Starts db, keycloak(+db), mailcatcher, ollama, grpcwebproxy, and nodejs app. App listens on port 3000, health/readiness check: GET /api/config returns 200 JSON. Full stack takes ~1-2 min to become healthy."
    ]
  }
}
```
<!-- BRIGHT_STAR_DATA -->
