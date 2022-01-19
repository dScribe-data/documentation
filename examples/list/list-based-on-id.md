# List based on ID

In the following example, we will do a request to the following endpoints:

{% swagger src="../../.gitbook/assets/openapi.yaml" path="/dataset/list" method="post" %}
[openapi.yaml](../../.gitbook/assets/openapi.yaml)
{% endswagger %}

{% hint style="info" %}
The same request will work for the REPORTS and DATASET ELEMENTS as well.
{% endhint %}

To get a single ID, you can use the following request:

```json
{
  "where": {
    "VIEWID": "ID1",
    # OR
    "VIEWID_IN": [
      "ID1"
    ]
  }
}
```

To get multiple IDs, do the following:

```json
{
  "limit": 50,
  "skip": 0,
  "where": {
    "VIEWID_NOT": "ID1", # list all IDs except this one
    # OR
    "VIEWID_NOT_IN": ["ID1", "ID2"], # list all IDs except these
    # OR
    "VIEWID_IN": [
      "ID1",
      "ID2"
    ]
  }
}
```

The \__IN and \_NOT\_IN_ can also be used for all the fields listed here:

{% content-ref url="../../reference/field-reference/datasets-fields.md" %}
[datasets-fields.md](../../reference/field-reference/datasets-fields.md)
{% endcontent-ref %}
