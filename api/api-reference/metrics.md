# Metrics

Working with metrics, you have the following endpoints. In this chapter we will discuss every endpoint in a bit more detail.

#### Listing Metrics

{% swagger src="../../.gitbook/assets/openapi (3).yaml" path="/metric/list" method="post" %}
[openapi (3).yaml](<../../.gitbook/assets/openapi (3).yaml>)
{% endswagger %}

Replace {FIELD} with the field you want to filter on. You can find a list of fields here:

{% content-ref url="../field-reference/metric-fields.md" %}
[metric-fields.md](../field-reference/metric-fields.md)
{% endcontent-ref %}

If you want to filter on for example NAME, you can send the following body with the request

```json
{
  "where": {
    "NAME": "string",
    // or
    "NAME_NOT": "string",
    // or
    "NAME_IN": [
      "string"
    ],
    // or
    "NAME_CONTAINS": "string",
  }
}
```

Filtering on ID works the same way:

```json
{
  "where": {
    "METRICID": "string",
    // or
    "METRICID_NOT": "string",
    // or
    "METRICID_IN": [
      "string"
    ],
    // or
    "METRICID_CONTAINS": "string",
  }
}
```

#### Creating Metrics

{% swagger src="../../.gitbook/assets/openapi (3).yaml" path="/metric/create" method="post" %}
[openapi (3).yaml](<../../.gitbook/assets/openapi (3).yaml>)
{% endswagger %}

You can create up to 100 metrics in one go. Notice that the METRICID will be generated for you. You can get the ID by listing.

#### Updating Metrics

{% swagger src="../../.gitbook/assets/openapi (3).yaml" path="/metric/update" method="post" %}
[openapi (3).yaml](<../../.gitbook/assets/openapi (3).yaml>)
{% endswagger %}

#### Deleting Metrics

{% swagger src="../../.gitbook/assets/openapi (3).yaml" path="/metric/delete" method="post" %}
[openapi (3).yaml](<../../.gitbook/assets/openapi (3).yaml>)
{% endswagger %}

Deleting metrics is straightforward, just pass an array of METRICIDS to the call and the rest will be done for you:

```javascript
["123", "456"]
```
