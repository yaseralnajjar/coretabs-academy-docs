# Social Login

{% api-method method="post" host="https://api.coretabs.net" path="/api/v1/auth/social/login/" %}
{% api-method-summary %}

{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="access\_token" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="provider" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
In case of already registered user
{% endapi-method-response-example-description %}

```javascript
    "key": "Token Key",
    "user": {
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
    }
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=201 %}
{% api-method-response-example-description %}
In case of a new user
{% endapi-method-response-example-description %}

```javascript
    "key": "Token Key",
    "user": {
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
    }
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

