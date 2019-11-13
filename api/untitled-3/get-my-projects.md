# CRUD My Projects

{% api-method method="post" host="https://api.coretabs.net" path="/api/v1/profile/projects" %}
{% api-method-summary %}
Create Project
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to create project.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="description" type="string" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="photo" type="string" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="github\_link" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="live\_demo\_link" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=201 %}
{% api-method-response-example-description %}
Project successfully created.
{% endapi-method-response-example-description %}

```javascript
{
    "id": 1,
    "description": "this is a chat api",
    "photo": null,
    "github_link": "https://github.com/user/chat-api",
    "live_demo_link": "https://api.chat.com"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="delete" host="https://api.coretabs.net" path="/api/v1/profile/projects/<pk>" %}
{% api-method-summary %}
DELETE My Project
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=204 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="patch" host="https://api.coretabs.net" path="/api/v1/profile/projects/<pk>" %}
{% api-method-summary %}
Update MY Project
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="description" type="string" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="photo" type="string" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="github\_link" type="string" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="live\_demo\_link" type="string" required=false %}

{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    "id": 2,
    "description": "",
    "photo": null,
    "github_link": "https://github.com/ahmedalrifai/chat-with-groups-api",
    "live_demo_link": "https://api.chat.com"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

