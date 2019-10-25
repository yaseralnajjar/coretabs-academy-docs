# Get My Profile

{% api-method method="get" host="https://api.coretabs.net" path="/api/v1/profile/" %}
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
{
  "username": "example123",
  "name": "John Doe",
  "role": "Student",
  "level": "Beginner",
  "description": "Some Description",
  "country": {
    "text": "أروبا",
    "value": "aw"
  },
  "bio": "",
  "skills": [
    {
      "text": "HTML",
      "value": "html"
    }...
  ],
  "projects": [
    {
      "id": 14,
      "description": "My Project",
      "photo": "https://some_project.jpg",
      "github_link": "github.com",
      "live_demo_link": "something.com"
    }
  ],
  "certificates": [
        {
            "id": "1b9ab187-4215-499a-af99-9d46abf1da44",
            "date": "2019-03-28",
            "heading": "Heading For Certificate"
        }...
  ],
  "avatar_url": "https://path.to/avatar.jpg",
  "facebook_link": "",
  "twitter_link": "",
  "linkedin_link": "",
  "github_link": "",
  "website_link": "",
  "date_joined": "2018-07-19T00:22:37Z"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

