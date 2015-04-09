# Deploy An edX (Birch) Environment

`heat stack-create -f edx-template.yml [-e edx-environment.yml] -t 120 <stack-name>`

### Environment Settings

Some settings should be private, and may be passed in through the use of a Heat Environment file. Below is an example of passing in SMTP settings.

**`edx-environment.yml`**

```
parameters:
  environment: |
    EDXAPP_EMAIL_HOST: 'smtp.example.com'
    EDXAPP_EMAIL_PORT: 587
    EDXAPP_EMAIL_USE_TLS: True
    EDXAPP_EMAIL_HOST_USER: 'user@example.com'
    EDXAPP_EMAIL_HOST_PASSWORD: 'mypassword'
```
