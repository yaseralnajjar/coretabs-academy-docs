# Get Current User Details

{% api-method method="get" host="https://api.coretabs.net" path="/api/v1/auth/user/" %}
{% api-method-summary %}

{% endapi-method-summary %}

{% api-method-description %}
**Authentication required**
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
    "username": "example123",
    "email": "example@email.com",
    "name": "John Doe",
    "avatar_url": "https://path.to/avatar.jpg"
    "batch_status": true,
    "account": {
        "track": "backend",
        "last_opened_workshop_slug": "last-workshop",
        "last_opened_module_slug": "last-module",
        "last_opened_lesson_slug": "last-lesson",
        "last_opened_lesson": 52
    }
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

