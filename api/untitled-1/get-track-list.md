# Get Track List

{% api-method method="get" host="https://api.coretabs.net" path="/api/v1/tracks/" %}
{% api-method-summary %}

{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
[
    {
        "id": 1,
        "workshops": [
            "backend-workshop0",
            "backend-workshop1",
            "backend-workshop2"
        ],
        "title": "Backend",
        "slug": "backend"
    },
    {
        "id": 2,
        "workshops": [
            "frontend-workshop0",
            "frontend-workshop1",
            "frontend-workshop2"
        ],
        "title": "Frontend",
        "slug": "frontend"
    }
]
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

