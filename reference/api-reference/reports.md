# Reports

Working with reports, you have the following endpoints. In this chapter we will discuss every endpoint in a bit more detail.

### Get Reports

{% swagger src="../../.gitbook/assets/openapi (3).yaml" path="/report/list" method="post" %}
[openapi (3).yaml](<../../.gitbook/assets/openapi (3).yaml>)
{% endswagger %}

### Create Reports

{% swagger src="../../.gitbook/assets/openapi (3).yaml" path="/report/create" method="post" %}
[openapi (3).yaml](<../../.gitbook/assets/openapi (3).yaml>)
{% endswagger %}

### Update Reports

{% swagger src="../../.gitbook/assets/openapi (3).yaml" path="/report/update" method="post" %}
[openapi (3).yaml](<../../.gitbook/assets/openapi (3).yaml>)
{% endswagger %}

If you want to update a report, the REPORTID is a required field and should be passed along with the body of the request.

### Delete Reports

{% swagger src="../../.gitbook/assets/openapi (3).yaml" path="/report/delete" method="post" %}
[openapi (3).yaml](<../../.gitbook/assets/openapi (3).yaml>)
{% endswagger %}

Deleting reports is straightforward, just pass an array of REPORTIDs to the call and the rest will be done for you:

```javascript
["123", "456"]
```
