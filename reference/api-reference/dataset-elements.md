# Dataset Elements

### Get datasets elements

{% swagger src="../../.gitbook/assets/openapi (2).yaml" path="/dse/list" method="post" %}
[openapi (2).yaml](<../../.gitbook/assets/openapi (2).yaml>)
{% endswagger %}

### Create datasets elements

{% swagger src="../../.gitbook/assets/openapi (2).yaml" path="/dse/create" method="post" %}
[openapi (2).yaml](<../../.gitbook/assets/openapi (2).yaml>)
{% endswagger %}

### Update datasets elements

{% swagger src="../../.gitbook/assets/openapi (2).yaml" path="/dse/update" method="post" %}
[openapi (2).yaml](<../../.gitbook/assets/openapi (2).yaml>)
{% endswagger %}

If you want to update a dse, the DSEID is a required field and should be passed along with the body of the request.

### Delete datasets elements

{% swagger src="../../.gitbook/assets/openapi (2).yaml" path="/dse/delete" method="post" %}
[openapi (2).yaml](<../../.gitbook/assets/openapi (2).yaml>)
{% endswagger %}

Deleting dses is straightforward, just pass an array of DSEIDs to the call and the rest will be done for you:

```javascript
["123", "456"]
```
