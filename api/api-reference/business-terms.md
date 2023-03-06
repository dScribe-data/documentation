# Business Terms

Working with business terms, you have the following endpoints. In this chapter we will discuss every endpoint in a bit more detail.



#### Listing Business terms

{% swagger src="../../.gitbook/assets/openapi.yaml" path="/business-term/list" method="post" %}
[openapi.yaml](../../.gitbook/assets/openapi.yaml)
{% endswagger %}

Replace {FIELD} with the field you want to filter on. You can find a list of fields here:

{% content-ref url="../field-reference/business-term-fields.md" %}
[business-term-fields.md](../field-reference/business-term-fields.md)
{% endcontent-ref %}

If you want to filter on for example NAME, you can send the following body with the request

```
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

```
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
