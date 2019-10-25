# Verify Email

{% api-method method="post" host="https://api.coretabs.net" path="/api/v1/auth/registration/verify-email/" %}
{% api-method-summary %}

{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="uid" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="key" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
In case of an already registered user \(email changed\)
{% endapi-method-response-example-description %}

```javascript
{
    "email": "mynewemail@gmail.com"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=201 %}
{% api-method-response-example-description %}
In case of a new user registration
{% endapi-method-response-example-description %}

```javascript

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



