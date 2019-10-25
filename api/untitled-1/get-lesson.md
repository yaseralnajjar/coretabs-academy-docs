# Get Lesson

{% api-method method="get" host="https://api.coretabs.net" path="/api/v1/tracks/<track\_slug>/workshops/<workshop\_slug>/modules/<module\_slug>/lessons/<lesson\_slug>" %}
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

{% api-method-parameter name="module\_slug" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="lesson\_slug" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
# For Youtube Video Lesson

        {
          "title": "Lesson Title",
          "slug": "lesson-title",
          "type": "0",
          "video_url": "https://www.youtube.com/watch?something",
          "markdown_url": "https://path.to/markdown.md",
          "is_shown": true
        }

# For Scrimba Video Lesson
 
        {
          "title": "Lesson Title",
          "slug": "lesson-title",
          "type": "1",
          "video_url": "https://scrimba.com/c/something",
          "markdown_url": "https://path.to/markdown.md",
          "is_shown": true
        }

# For Markdown Lesson

        {
          "title": "Lesson Title",
          "slug": "lesson-title",
          "type": "2",
          "markdown_url": "https://path.to/markdown.md",
          "is_shown": true
        }

# For Quiz Lesson

        {
          "title": "Lesson Title",
          "slug": "lesson-title",
          "type": "3",
          "markdown_url": "https://path.to/markdown.md",
          "is_shown": true
        }

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

