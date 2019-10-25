# Get Certificate

{% api-method method="get" host="https://api.coretabs.net" path="/api/v1/certificates/<uid>/" %}
{% api-method-summary %}

{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="uid" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    "full_name": "John Doe",
    "date": "2019-03-28",
    "heading": "Heading For Certificate",
    "body": "Body For Certificate.",
    "signature": {
        "name": "John",
        "url": "https://path.to/signature.jpg"
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

