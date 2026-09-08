# 🌟 Bright Star — Run Memory

<!-- BRIGHT_STAR_DATA — generated; do not edit -->
```json
{
  "version": 1,
  "generatedAt": "2026-09-08T13:36:24.574Z",
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
    "completed": false
  },
  "auth": {
    "hasAuth": true,
    "authObjectId": "1tHe52EAsXV7TooUfpDord",
    "registration": {
      "baseUrl": "http://localhost:3000",
      "endpoint": "/api/users/basic",
      "method": "POST",
      "body": "{\"email\":\"testuser@example.com\",\"firstName\":\"Test\",\"lastName\":\"User\",\"password\":\"TestPass123!\",\"company\":\"Test\",\"cardNumber\":\"1234567890123456\",\"phoneNumber\":\"+1234567890\",\"op\":\"basic\"}",
      "contentType": "json"
    },
    "protectedResource": {
      "method": "GET",
      "url": "/api/products"
    }
  },
  "hints": {
    "startup": [
      ".env already configured for local development with database credentials (DATABASE_USER=bc, DATABASE_PASSWORD=bc). Node 18, build uses nest-cli.fast.json, start:prod runs 'node dist/main.js'. Dockerfile multi-stage: build then production.",
      ".dockerignore needed to include .data directory to prevent permission errors during Docker build context loading. App successfully runs on port 3000 with compose.local.yml."
    ]
  }
}
```
<!-- BRIGHT_STAR_DATA -->
