# Get Track Workshop List

{% api-method method="get" host="https://api.coretabs.net" path="/api/v1/tracks/<track\_slug>/workshops/" %}
{% api-method-summary %}

{% endapi-method-summary %}

{% api-method-description %}
**Authentication required**
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="track\_slug" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
[
    {
        "title": "Frontend-Workshop",
        "slug": "frontend-workshop",
        "modules": [
            "frontend-module1",
            "frontend-module2"
        ],
        "shown_percentage": 12.0
    }...
]
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

