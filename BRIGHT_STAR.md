# 🌟 Bright Star — Run Memory

<!-- BRIGHT_STAR_DATA — generated; do not edit -->
```json
{
  "version": 1,
  "generatedAt": "2026-09-04T13:32:48.001Z",
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
    "authObjectId": "2dCUiTLRvKSi5uhBmuKhSs",
    "registration": {
      "baseUrl": "http://localhost:3000",
      "endpoint": "/api/users/basic",
      "method": "POST",
      "body": "{\"email\": \"testuser@example.com\", \"password\": \"TestPassword123!\", \"firstName\": \"Test\", \"lastName\": \"User\", \"company\": \"TestCorp\", \"cardNumber\": \"1234567890123456\", \"phoneNumber\": \"+1234567890\", \"op\": \"basic\"}",
      "contentType": "json"
    },
    "protectedResource": {
      "method": "GET",
      "url": "/api/auth/jwt/rsa/signature/validate"
    }
  },
  "hints": {
    "startup": [
      "Use compose.local.yml to run app locally. Node.js 18 Alpine, builds with npm ci and npm run build:fast. Health check: wget http://nodejs:3000/api/config. Requires .env vars: DATABASE_HOST=db, KEYCLOAK_SERVER_URI=http://keycloak:8080, etc. See .env for full config with defaults.",
      "Successfully started with: docker compose -f compose.local.yml up -d --build. App runs on localhost:3000. Health check via curl http://localhost:3000/api/config returns 200. All services healthy: nodejs, db, keycloak, keycloak-db, mailcatcher, ollama, grpcwebproxy."
    ]
  }
}
```
<!-- BRIGHT_STAR_DATA -->
