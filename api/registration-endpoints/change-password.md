# Change Password

{% api-method method="post" host="https://api.coretabs.net" path="/api/v1/auth/password/change/" %}
{% api-method-summary %}

{% endapi-method-summary %}

{% api-method-description %}
**Authentication Required**
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="old\_password" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="new\_password1" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="new\_password2" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
"detail": "New password has been saved."
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



