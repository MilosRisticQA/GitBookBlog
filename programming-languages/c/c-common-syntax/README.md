# C\#: Common Syntax

ess

{% api-method method="get" host="https://petstore.swagger.io" path="/v2/pet/88" %}
{% api-method-summary %}
Find pet by ID
{% endapi-method-summary %}

{% api-method-description %}
Returns a single pet
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="petId" type="integer" required=true %}
ID of pet to return
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Successful operation
{% endapi-method-response-example-description %}

```css
{
  "id": 0,
  "category": {
    "id": 0,
    "name": "string"
  },
  "name": "doggie",
  "photoUrls": [
    "string"
  ],
  "tags": [
    {
      "id": 0,
      "name": "string"
    }
  ],
  "status": "available"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
Invalid ID supplied
{% endapi-method-response-example-description %}

{% tabs %}
{% tab title="Response body" %}
```
{
  "code": 1,
  "type": "error",
  "message": "Pet not found"
}
```
{% endtab %}

{% tab title="Response Headers" %}
```
 access-control-allow-headers: Content-Type, api_key, Authorization 
access-control-allow-methods: GET, POST, DELETE, PUT 
access-control-allow-origin: * 
connection: close 
content-type: application/json 
date: Sun, 29 Mar 2020 14:39:01 GMT 
server: Jetty(9.2.9.v20150224) 
```
{% endtab %}
{% endtabs %}
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



