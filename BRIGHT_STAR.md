# 🌟 Bright Star — Run Memory

<!-- BRIGHT_STAR_DATA — generated; do not edit -->
```json
{
  "version": 1,
  "generatedAt": "2026-09-09T13:41:15.456Z",
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
      "username": "bright@test.com",
      "password": "BrightTest123!",
      "email": "bright@test.com"
    }
  },
  "auth": {
    "hasAuth": true,
    "authObjectId": "5h87LvRHwmoHpkvoRbebj1",
    "registration": {
      "baseUrl": "http://localhost:3000",
      "endpoint": "/api/users/basic",
      "method": "POST",
      "body": "{\"email\":\"test@test.com\",\"firstName\":\"Test\",\"lastName\":\"User\",\"company\":\"Test Company\",\"cardNumber\":\"1234567890123456\",\"phoneNumber\":\"1234567890\",\"password\":\"Test123!\",\"op\":\"basic\"}",
      "contentType": "json"
    },
    "protectedResource": {
      "method": "GET",
      "url": "/api/auth/jwt/rsa/signature/validate"
    }
  },
  "hints": {
    "startup": [
      "NestJS app (Broken Crystals) - Node.js 18, builds from Dockerfile, runs on port 3000. Uses compose.local.yml for local dev with PostgreSQL, Keycloak, Mailcatcher, and Ollama. Start command: docker compose --file=compose.local.yml up -d --build. Health check: GET /api/config returns 200."
    ]
  }
}
```
<!-- BRIGHT_STAR_DATA -->
