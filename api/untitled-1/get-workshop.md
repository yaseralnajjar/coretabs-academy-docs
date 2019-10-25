# Get Workshop

{% api-method method="get" host="https://api.coretabs.net" path="/api/v1/tracks/<track\_slug>/workshops/<workshop\_slug>" %}
{% api-method-summary %}

{% endapi-method-summary %}

{% api-method-description %}
**Authentication required  
Email approved required  
Batch approved required**
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="track\_slug" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="workshop\_slug" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    "title": "Frontend-Workshop",
    "slug": "frontend-workshop",
    "level": "beginner",
    "last_update_date": "1972-10-12T00:00:00Z",
    "duration": "50.2",
    "description": "Understand player key happen federal end. Head every up customer past talk and. Own where before strategy.",
    "used_technologies": "Leader may.",
    "workshop_result_url": "http://www.hansen-ochoa.com/",
    "workshop_forums_url": "https://perez.com/",
    "shown_percentage": 50.0,
    "authors": [
        {
          "name": "John Doe",
          "role": "Tutor",
          "avatar_url": "https://path.to/avatar.png"
        }...
    ],
    "modules": [
        {
            "title": "Frontend-Module",
            "slug": "frontend-module",
            "is_hidden": false,
            "created_date": "2019-04-20T18:02:44.341994Z",
            "last_update_date": "2019-04-20T18:02:44.341994Z"
            "id": 32,
            "lessons": [
                {
                    "title": "Frontend-Lesson",
                    "slug": "frontend-lesson",
                    "type": "2",
                    "markdown_url": "http://taylor-cook.com/",
                    "is_shown": false
                }...
            ]
        }...
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

