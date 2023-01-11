# List based on filters

In the following example, we will do a request to the following endpoints:

{% swagger src="../../.gitbook/assets/openapi (7).yaml" path="/dataset/list" method="post" %}
[openapi (7).yaml](<../../.gitbook/assets/openapi (7).yaml>)
{% endswagger %}

{% hint style="info" %}
The same request will work for the REPORTS and DATASET ELEMENTS as well.
{% endhint %}

The body of the request can be build up as follows:

```json
{
  "limit": 50,
  "skip": 0,
  "where": {
    "NAME_CONTAINS": "Important"
}
```

To get the next page, you can use this:

```json
{
  "limit": 50,
  "skip": 1,
  "where": {
    "NAME_CONTAINS": "Important"
}
```

And so on.

You can do this for every field listed here:

{% content-ref url="../../reference/field-reference/datasets-fields.md" %}
[datasets-fields.md](../../reference/field-reference/datasets-fields.md)
{% endcontent-ref %}
