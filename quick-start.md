# Quick Start

## Get your API keys

The first thing you have to do is get an API key. Go to the dScribe Portal and navigate to the admin section. Find the API keys menu item and click on it. You should see something like this:

![The dScribe API keys page](<.gitbook/assets/apikeys (1).png>)

Create a key with the following settings:

![A superuser token](<.gitbook/assets/create key.png>)

{% hint style="info" %}
**Good to know**: here we are creating a superuser token. This means it will have permissions to do everything within the app. If you want to create a restricted token, look at our guides around security and add the necessary permissionsets to the token.
{% endhint %}

Copy the token by clicking on the copy icon:

![](.gitbook/assets/copy.png)

This token can now be exchanged for an access\_token _to make authenticated requests. To get_ an access_\__token, make the following request (in postman or in the browser):&#x20;

{% swagger method="get" path="/api/api-token" baseUrl="https://{your_tenant}.dscribedata.com" summary="Exchange your API key for an access_token" %}
{% swagger-description %}
The token will be valid for 24 hours
{% endswagger-description %}

{% swagger-parameter in="query" name="api_key" required="true" %}
The API key you obtained above
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Will return an access_token" %}
```javascript
{
    access_token: "eyJhbGciOiJSUzI1NiIsInR5cCI..."
}
```
{% endswagger-response %}
{% endswagger %}

{% hint style="info" %}
**Good to know:** As mentioned above, restrict access to your resources by applying permission sets to your API keys.
{% endhint %}

## Make your first request

Lets start by getting listing all the reports stored in the dScribe graph.

{% swagger src=".gitbook/assets/openapi.yaml" path="/report/list" method="post" %}
[openapi.yaml](.gitbook/assets/openapi.yaml)
{% endswagger %}

{% hint style="info" %}
**Good to know:** Listing of objects from the graph will always be paginated.&#x20;
{% endhint %}

Take a look at how you might call this method using our official libraries, or via `curl`:

{% tabs %}
{% tab title="curl" %}
```
curl https://{your_tenant}.dscribedata.com/api/report/list
    -H "Authorization: Bearer ${INSERT ACCESS_TOKEN}" 
```
{% endtab %}
{% endtabs %}
