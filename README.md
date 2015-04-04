# Deploy An edX (Birch) Environment

`heat stack-create -u https://raw.githubusercontent.com/cloud-training/edx-heat-ansible/master/edx-template.yml [-e edx-environment-private.yml] -t 120 <stack-name>`

### Private Environment Settings

Some settings should be private, and may be passed in through the use of a Heat Environment file. Below in an example of passing in SMTP credentials.

**`edx-environment-private.yml`**

```
parameters:
  environment_private: |
    EDXAPP_EMAIL_HOST: 'smtp.example.com'
    EDXAPP_EMAIL_PORT: 587
    EDXAPP_EMAIL_USE_TLS: True
    EDXAPP_EMAIL_HOST_USER: 'user@example.com'
    EDXAPP_EMAIL_HOST_PASSWORD: 'mypassword'
```
