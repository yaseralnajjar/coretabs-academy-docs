# Change Current User Details

{% api-method method="patch" host="https://api.coretabs.net" path="/api/v1/auth/user/" %}
{% api-method-summary %}

{% endapi-method-summary %}

{% api-method-description %}
**Authentication required**
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="username" type="string" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="email" type="string" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="name" type="string" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="avatar" type="object" required=false %}
Upload new avatar image
{% endapi-method-parameter %}

{% api-method-parameter name="track" type="string" required=false %}
Must be inside account object
{% endapi-method-parameter %}

{% api-method-parameter name="last-opened-lesson" type="string" required=false %}
Must be inside account object
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Returns updated user data
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

