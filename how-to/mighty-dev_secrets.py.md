# Mighty dev\_secrets.py

### Why This File is IMPORTANT?!

We use this file in settings to add our secrets \(without committing them\).

Please, please, please... **NEVER use dev.py to add custom environment variables because you might commit them by mistake.**

This is where the file should exist \(and your app locally will automatically be loaded with these secrets\):

![](../.gitbook/assets/image%20%281%29.png)

### Connect to DB

Just add these lines \(copy env vars as explained in Manage Environment Variables\)

```text
import dj_database_url


DATABASES = {
   'default': dj_database_url.config(
       default='postgres://USER:PASS@IP:5432/DB'
   )
}
```

### Connect Mailgun

```text
MAILGUN_API_KEY = 'key-YOURKEY'
MAILGUN_LIST_DOMAIN = 'api-dev.coretabs.net'
```

### Connect SQS

```text
from kombu.utils.url import safequote


AWS_ACCESS_KEY_ID = safequote('AWS_ID')
AWS_SECRET_ACCESS_KEY = safequote('AWS_KEY')
CELERY_BROKER_URL = 'sqs://{}:{}@'.format(AWS_ACCESS_KEY_ID, AWS_SECRET_ACCESS_KEY)
CELERY_AWS_REGION = 'us-east-1'
CELERY_AWS_SQS_PREFIX = 'academy-staging-'
CELERY_BROKER_TRANSPORT_OPTIONS = {'region': CELERY_AWS_REGION,
                                   'visibility_timeout': 3600,
                                   'polling_interval': 10,
                                   'queue_name_prefix': CELERY_AWS_SQS_PREFIX,
                                   'CELERYD_PREFETCH_MULTIPLIER': 0,
                                   }
```



