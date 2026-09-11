# 🌟 Bright Star — Run Memory

<!-- BRIGHT_STAR_DATA — generated; do not edit -->
```json
{
  "version": 1,
  "generatedAt": "2026-09-11T00:17:59.489Z",
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
    "command": "docker compose -f compose.yml -f compose.local.yml up -d --build",
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
    "authObjectId": "gmk1WCUSXie45E9gTqsrYT",
    "registration": {
      "baseUrl": "http://localhost:3000",
      "endpoint": "/api/users/basic",
      "method": "POST",
      "body": "{\"email\":\"bright@test.com\",\"password\":\"BrightTest123!\",\"firstName\":\"bright_test\",\"lastName\":\"admin\",\"company\":\"Brightsec\",\"cardNumber\":\"4111111111111111\",\"phoneNumber\":\"+1 234 567 890\",\"op\":\"basic\"}",
      "contentType": "json"
    },
    "seedCommands": [
      {
        "type": "host",
        "command": "docker ps --format '{{.ID}} {{.Names}} {{.Image}}'"
      },
      {
        "type": "host",
        "command": "docker exec brokencrystals-db-1 env | grep -i POSTGRES; docker exec brokencrystals-db-1 psql -U postgres -l 2>&1 | head -20"
      },
      {
        "type": "host",
        "command": "docker exec brokencrystals-db-1 psql -U bc -d bc -c \"\\dt\""
      },
      {
        "type": "host",
        "command": "docker exec brokencrystals-db-1 psql -U bc -d bc -c \"SELECT id, email, \\\"firstName\\\", \\\"lastName\\\", \\\"isAdmin\\\", \\\"isBasic\\\", password FROM \\\"user\\\" WHERE email='bright@test.com';\""
      },
      {
        "type": "host",
        "command": "docker exec brokencrystals-db-1 psql -U bc -d bc -c \"\\d \\\"user\\\"\""
      },
      {
        "type": "host",
        "command": "docker exec brokencrystals-db-1 psql -U bc -d bc -c \"SELECT id, email, first_name, last_name, is_admin, is_basic, password FROM \\\"user\\\" WHERE email='bright@test.com';\""
      },
      {
        "type": "host",
        "command": "docker exec brokencrystals-db-1 psql -U bc -d bc -c \"DELETE FROM \\\"user\\\" WHERE email='bright@test.com';\""
      },
      {
        "type": "host",
        "command": "docker exec brokencrystals-db-1 psql -U bc -d bc -c \"UPDATE \\\"user\\\" SET is_admin=true, first_name='bright_test' WHERE email='bright@test.com'; SELECT id,email,first_name,last_name,is_admin,is_basic FROM \\\"user\\\" WHERE email='bright@test.com';\""
      },
      {
        "type": "host",
        "command": "curl -s -D - -o /tmp/body.json -X POST http://localhost:3000/api/auth/login -H \"Content-Type: application/json\" -d '{\"user\":\"bright@test.com\",\"password\":\"BrightTest123!\",\"op\":\"basic\"}'; echo; cat /tmp/body.json"
      },
      {
        "type": "host",
        "command": "TOKEN=$(curl -s -D - -o /tmp/body.json -X POST http://localhost:3000/api/auth/login -H \"Content-Type: application/json\" -d '{\"user\":\"bright@test.com\",\"password\":\"BrightTest123!\",\"op\":\"basic\"}' | grep -i '^authorization' | sed 's/authorization: //I' | tr -d '\\r')\necho \"TOKEN=$TOKEN\"\ncurl -s -D - -o /tmp/me.json http://localhost:3000/api/users/me -H \"Authorization: $TOKEN\"\necho; cat /tmp/me.json\necho\ncurl -s -D - -o /tmp/admin.json \"http://localhost:3000/api/users/one/bright@test.com/adminpermission\" -H \"Authorization: $TOKEN\"\necho; cat /tmp/admin.json"
      },
      {
        "type": "host",
        "command": "curl -s -D /tmp/headers.txt -o /tmp/body.json -X POST http://localhost:3000/api/auth/login -H \"Content-Type: application/json\" -d '{\"user\":\"bright@test.com\",\"password\":\"BrightTest123!\",\"op\":\"basic\"}'\ngrep -i '^authorization' /tmp/headers.txt"
      },
      {
        "type": "host",
        "command": "TOKEN=$(grep -i '^authorization' /tmp/headers.txt | sed 's/authorization: //I' | tr -d '\\r')\ncurl -s -D /tmp/me_headers.txt -o /tmp/me.json http://localhost:3000/api/users/me -H \"Authorization: $TOKEN\"\necho \"---ME---\"; cat /tmp/me.json; echo\ncurl -s -D /tmp/admin_headers.txt -o /tmp/admin.json \"http://localhost:3000/api/users/one/bright@test.com/adminpermission\" -H \"Authorization: $TOKEN\"\necho \"---ADMIN---\"; cat /tmp/admin.json; echo"
      },
      {
        "type": "host",
        "command": "cat > /tmp/test.sh << 'EOF'\n#!/bin/bash\nTOKEN=$(grep -i '^authorization' /tmp/headers.txt | sed 's/authorization: //I' | tr -d '\\r')\ncurl -s -D /tmp/me_headers.txt -o /tmp/me.json http://localhost:3000/api/users/me -H \"Authorization: $TOKEN\"\necho \"---ME---\"; cat /tmp/me.json; echo\ncurl -s -D /tmp/admin_headers.txt -o /tmp/admin.json \"http://localhost:3000/api/users/one/bright@test.com/adminpermission\" -H \"Authorization: $TOKEN\"\necho \"---ADMIN---\"; cat /tmp/admin.json; echo\nEOF\nbash /tmp/test.sh"
      },
      {
        "type": "host",
        "command": "curl -s http://localhost:3000/api/users/me -H \"Authorization: `cat /tmp/headers.txt | grep -i authorization | cut -d' ' -f2- | tr -d '\\r'`\""
      },
      {
        "type": "host",
        "command": "python3 - <<'PYEOF'\nimport re\nheaders = open('/tmp/headers.txt').read()\nm = re.search(r'(?im)^authorization:\\s*(\\S+)', headers)\ntoken = m.group(1)\nprint(\"TOKEN:\", token[:20], \"...\")\nimport urllib.request\nreq = urllib.request.Request(\"http://localhost:3000/api/users/me\", headers={\"Authorization\": token})\ntry:\n    resp = urllib.request.urlopen(req)\n    print(resp.status, resp.read())\nexcept Exception as e:\n    print(\"ERR\", e, e.read() if hasattr(e,'read') else '')\n\nreq2 = urllib.request.Request(\"http://localhost:3000/api/users/one/bright@test.com/adminpermission\", headers={\"Authorization\": token})\ntry:\n    resp2 = urllib.request.urlopen(req2)\n    print(resp2.status, resp2.read())\nexcept Exception as e:\n    print(\"ERR2\", e, e.read() if hasattr(e,'read') else '')\nPYEOF"
      },
      {
        "type": "host",
        "command": "python3 -c \"import re; h=open('/tmp/headers.txt').read(); m=re.search(r'(?im)^authorization:\\s*(\\S+)', h); print(m.group(1))\" > /tmp/token.txt; cat /tmp/token.txt"
      },
      {
        "type": "host",
        "command": "curl -s -o /dev/null -w \"%{http_code}\\n\" http://localhost:3000/api/users/one/bright@test.com; curl -s http://localhost:3000/api/users/one/bright@test.com"
      },
      {
        "type": "host",
        "command": "curl -s -o /dev/null -w \"%{http_code}\\n\" http://localhost:3000/api/users/me\ncurl -s http://localhost:3000/api/users/me"
      },
      {
        "type": "host",
        "command": "curl -s http://localhost:3000/api-json | python3 -c \"import json,sys; d=json.load(sys.stdin); print('\\n'.join(p for p in d['paths'] if 'users' in p))\""
      },
      {
        "type": "host",
        "command": "curl -s -o /tmp/apijson.txt -w \"%{http_code}\\n\" http://localhost:3000/api-json; head -c 300 /tmp/apijson.txt"
      },
      {
        "type": "docker",
        "command": "grep -rn \"'/me'\" /var/www/dist/users/ 2>/dev/null; grep -rn \"getAuthenticatedUser\" /var/www/dist -l",
        "container": "brokencrystals-nodejs-1"
      },
      {
        "type": "docker",
        "command": "find /var/www/dist -iname \"users.controller.js\"",
        "container": "brokencrystals-nodejs-1"
      },
      {
        "type": "docker",
        "command": "grep -n \"Get\\|Post\\|Put\\|Delete\\|Controller\" /var/www/dist/users/users.controller.js | head -60",
        "container": "brokencrystals-nodejs-1"
      }
    ],
    "protectedResource": {
      "method": "GET",
      "url": "/api/auth/jwt/rsa/signature/validate"
    }
  },
  "limits": {
    "scanPrepReplayCommands": [
      {
        "container": "brokencrystals-nodejs-1",
        "command": "node -e \"const {verify}=require('argon2'); verify('\\$argon2id\\$v=19\\$m=65536,t=3,p=4\\$jmtTCTEcjngErif00RfYAg\\$biS59Ixnrz+dHeJrJ91ybmHt+4wrVgcH3RXvfaqZtNI','admin').then(r=>console.log('match:',r)).catch(e=>console.log('err',e.message))\""
      },
      {
        "container": "brokencrystals-nodejs-1",
        "command": "cd /var/www && node -e \"const {verify}=require('argon2'); verify(process.argv[1],'admin').then(r=>console.log('match:',r)).catch(e=>console.log('err',e.message))\" '$argon2id$v=19$m=65536,t=3,p=4$jmtTCTEcjngErif00RfYAg$biS59Ixnrz+dHeJrJ91ybmHt+4wrVgcH3RXvfaqZtNI'"
      }
    ]
  },
  "hints": {
    "startup": [
      "brokencrystals app: use `docker compose -f compose.yml -f compose.local.yml up -d --build` to build nodejs from local Dockerfile source and start all deps (db, keycloak, mailcatcher, ollama, grpcwebproxy). Base compose.yml sets nodejs NODE_ENV=production, which makes src/main.ts try to load TLS certs from /etc/letsencrypt/live/brokencrystals.com/ (not present) causing crash loop. Fix: add `NODE_ENV: development` to nodejs environment in compose.local.yml override so it runs plain HTTP. App listens on 0.0.0.0:3000, health/readiness at GET /api/config (returns 200). Healthcheck also uses this path."
    ]
  }
}
```
<!-- BRIGHT_STAR_DATA -->
