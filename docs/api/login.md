---
sidebar_position: 2
---

# Login

```bash
curl -X POST https://xauth.ru/api/login \
  -H 'Content-Type: application/json' \
  -d '{
    "username": {username},
    "password": {password},
    "hwid": {hwid},
    }'
```