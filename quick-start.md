# Quick Start

## Get your API keys

The first thing you have to do is get an API key. Go to the dScribe Portal and navigate to the admin section. Find the API keys menu item and click on it. You should see something like this:

<figure><img src=".gitbook/assets/image (15).png" alt=""><figcaption><p>The API Keys screen in the dScribe application</p></figcaption></figure>

Create a key:

<figure><img src=".gitbook/assets/Screenshot 2022-12-20 at 14.16.49.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Good to know**: here we are creating a superuser token. This means it will have permissions to do everything within the app.
{% endhint %}

You will see a popup that will show you your secret. **This will only be shown once, store it somewhere safe.**

<figure><img src=".gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

The client\_id and client\_secret can now be exchanged for an access\_token _to make authenticated requests. To get_ an access_\__token, make the following request (in postman or in the browser):&#x20;

{% swagger method="post" path="/api/api-token" baseUrl="https://{your_tenant}.dscribedata.com" summary="Exchange your client_id and client_secret for an access_token" %}
{% swagger-description %}
The token will be valid for 24 hours
{% endswagger-description %}

{% swagger-parameter in="body" required="true" name="client_id" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="client_secret" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="header" name="Content-Type" required="true" %}
application/x-www-form-urlencoded
{% endswagger-parameter %}

{% swagger-parameter in="body" name="scope" required="true" %}
default
{% endswagger-parameter %}

{% swagger-parameter in="body" name="grant_type" required="true" %}
client_credentials
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Will return an access_token" %}
```javascript
{
    access_token: "eyJhbGciOiJSUzI1NiIsInR5cCI..."
}
```
{% endswagger-response %}
{% endswagger %}

## Make your first request

Lets start by listing all the reports stored in the dScribe graph.

{% swagger method="post" path="/report/list" baseUrl="https://your_tenant.dscribedata.com/api" summary="" %}
{% swagger-description %}
This query will return the first 25 results. You can use the skip and limit parameters to build in pagination.
{% endswagger-description %}

{% swagger-parameter in="body" name="body" type="json" required="false" %}

{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
  "metadata": {
    "total": 0
  },
  "results": [
    {
      "REPORTID": "string",
      "CALC_FORMULA": "string",
      "CALC_FORMULAFULLTEXT": "string",
      "CALC_FORMULAHTML": "string",
      "DESC": "string",
      "DESCFULLTEXT": "string",
      "DESCHTML": "string",
      "INTERPRETATION": "string",
      "NAME": "string",
      "PROPERTIES": {
        "{readable_id}": [
          "string"
        ]
      }
    }
  ]
}
```
{% endswagger-response %}

{% swagger-response status="401: Unauthorized" description="" %}
```javascript
{
  "code": "string",
  "message": "string"
}
```
{% endswagger-response %}

{% swagger-response status="404: Not Found" description="" %}
```javascript
{
  "code": "string",
  "message": "string"
}
```
{% endswagger-response %}

{% swagger-response status="500: Internal Server Error" description="" %}
```javascript
{
  "code": "string",
  "message": "string"
}
```
{% endswagger-response %}
{% endswagger %}

{% hint style="info" %}
**Good to know:** Listing of objects from the graph will always be paginated.&#x20;
{% endhint %}

Take a look at how you might call this method via `curl`:

{% tabs %}
{% tab title="curl" %}
```
curl https://{your_tenant}.dscribedata.com/api/report/list
    -H "Authorization: Bearer ${INSERT ACCESS_TOKEN}" 
```
{% endtab %}
{% endtabs %}

```
const myHeaders = new Headers();
myHeaders.append("Authorization", "Bearer ACCES TOKEN");

const requestOptions = {
  method: 'GET',
  headers: myHeaders,
};

fetch("https://{your_tenant}.dscribedata.com/api/report/list", requestOptions)
  .then(response => response.json())
  .then(result => console.log(result))
  .catch(error => console.log('error', error));
```
