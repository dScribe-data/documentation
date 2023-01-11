# Datasets

Working with datasets, you have the following endpoints. In this chapter we will discuss every endpoint in a bit more detail.

### Get datasets

{% swagger src="../../.gitbook/assets/openapi (3).yaml" path="/dataset/list" method="post" %}
[openapi (3).yaml](<../../.gitbook/assets/openapi (3).yaml>)
{% endswagger %}

### Create datasets

{% swagger src="../../.gitbook/assets/openapi (2).yaml" path="/dataset/create" method="post" %}
[openapi (2).yaml](<../../.gitbook/assets/openapi (2).yaml>)
{% endswagger %}

### Update datasets

{% swagger src="../../.gitbook/assets/openapi (2).yaml" path="/dataset/update" method="post" %}
[openapi (2).yaml](<../../.gitbook/assets/openapi (2).yaml>)
{% endswagger %}

If you want to update a dataset, the DATASETID is a required field and should be passed along with the body of the request.

### Delete datasets

{% swagger src="../../.gitbook/assets/openapi (2).yaml" path="/dataset/delete" method="post" %}
[openapi (2).yaml](<../../.gitbook/assets/openapi (2).yaml>)
{% endswagger %}

Deleting datasets is straightforward, just pass an array of DATASETIDs to the call and the rest will be done for you:

```javascript
["123", "456"]
```
