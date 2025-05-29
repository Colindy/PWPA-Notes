### Broken Access Control

Quick note on this.  It appears in the video that you're to go to Auth 0x05 and it gives you some creds to work with but when I opened mine via docker, it did not have that info so I pulled it from the video.

POST /login.php

`curl -X POST -H "Content-Type: application/json" -d '{"username": "admin", "password": "password123"}' http://localhost/labs/api/login.php`

Credentials - jeremy:cheesecake, jessamy:tiramisu

GET /account.php

`curl -X GET "http://localhost/labs/api/account.php?token=JWT"`

PUT /account.php

`curl -X PUT -H "Content-Type: application/json" -d '{"token": "JWT", "username":"username", "bio": "New bio information."}' http://localhost/labs/api/account.php`