# Deploy An edX (Birch) Environment

`heat stack-create -u https://raw.githubusercontent.com/cloud-training/edx-heat-ansible/master/edx-template.yml [-e edx-environment-private.yml] -t 120 <stack-name>`

### Private Environment Settings

Some settings should be private, and may be passed in through the use of a Heat Environment file. Below in an example of passing in SMTP, Memcached and MongoDB settings.

**`edx-environment-private.yml`**

```
parameters:
  environment_private: |
    EDXAPP_EMAIL_HOST: 'smtp.example.com'
    EDXAPP_EMAIL_PORT: 587
    EDXAPP_EMAIL_USE_TLS: True
    EDXAPP_EMAIL_HOST_USER: 'user@example.com'
    EDXAPP_EMAIL_HOST_PASSWORD: 'mypassword'
    
    EDXAPP_MEMCACHE:
      - 'memcached.example.com:11211'
    
    EDXAPP_MONGO_HOSTS:
      - 'mongo.example.com'
    EDXAPP_MONGO_PORT: 27017
    EDXAPP_MONGO_DB_NAME: 'edxapp'
    EDXAPP_MONGO_USER: 'edxapp'
    EDXAPP_MONGO_PASSWORD: 'mypassword'
    
    FORUM_MONGO_HOSTS:
      - 'mongo.example.com'
    FORUM_MONGO_PORT: 27017
    FORUM_MONGO_DATABASE: 'cs_comments_service'
    FORUM_MONGO_USER: 'cs_comments_service'
    FORUM_MONGO_PASSWORD: 'mypassword'
```
