# Get Track Public Info

{% api-method method="get" host="https://api.coretabs.net" path="/api/v1/tracks/<track\_slug>/" %}
{% api-method-summary %}

{% endapi-method-summary %}

{% api-method-description %}

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
    "title": "Backend",
    "slug": "backend",
    "workshops": [
        {
            "title": "Backend-Workshop0",
            "slug": "backend-workshop0",
            "level": "beginner",
            "description": "Think pressure though see hard article read. To someone military whole feel statement owner.\nBack far sister avoid. Local shoulder interest individual.",
            "modules": [
                {
                    "title": "Backend-Module0",
                    "slug": "backend-module0",
                    "created_date": "2019-04-20T18:02:06.525609Z",
                    "last_update_date": "2019-04-20T18:02:06.525609Z",
                    "lessons": [
                        {
                            "title": "Backend-Lesson0",
                            "slug": "backend-lesson0"
                        }...
                    ]
                }...
            ]
        }...
    ]
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

