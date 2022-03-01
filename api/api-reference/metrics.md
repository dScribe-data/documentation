# Metrics

Working with metrics, you have the following endpoints. In this chapter we will discuss every endpoint in a bit more detail.

#### Listing Metrics

{% swagger method="post" path="/metrics/list" baseUrl="https://{your_tenant}.dscribedata.com/api" summary="List all the metrics stored in the dScribe platform" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="where" type="object" %}
Look at the swagger file 

[here](https://dscribe-prod-i-app-customerapi.azurewebsites.net/v1/docs/#/Metric/post_metric_list)

 for more info. 
{% endswagger-parameter %}

{% swagger-parameter in="body" name="limit" type="number" %}
Used together with offset to control pagination. Defaults to 100.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="offset" type="number" %}
Used together with limit to control pagination. This specifies how many metrics the request should skip. Defaults to 0.
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="List of metrics" %}
```javascript
{
  "metadata": {
    "total": 0
  },
  "results": [
    {
      "KPIID": "string",
      "NAME": "string",
      "DESC": "string",
      "DESCFULLTEXT": "string",
      "DESCHTML": "string",
      "INTERPRETATION": "string",
      "CALC_FORMULA": "string",
      "CALC_FORMULAHTML": "string",
      "CALC_FORMULAFULLTEXT": "string",
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

{% swagger-response status="400: Bad Request" description="Request is badly formatted" %}
```javascript
{
  "code": "string",
  "message": "string"
}
```
{% endswagger-response %}
{% endswagger %}

When listing metrics, you can pass a where object to filter your results. As specified in the swagger docs, the shape of the where object is as follows:

```json
  "where": {
    "{TAG}ID": "string",
    "{TAG}ID_NOT": "string",
    "{TAG}ID_IN": [
      "string"
    ],
    "{TAG}ID_NOT_IN": [
      "string"
    ],
    "{TAG}ID_CONTAINS": "string",
    "{TAG}ID_NOT_CONTAINS": "string",
    "{FIELD}": "string",
    "{FIELD}_NOT": "string",
    "{FIELD}_IN": [
      "string"
    ],
    "{FIELD}_NOT_IN": [
      "string"
    ],
    "{FIELD}_CONTAINS": "string",
    "{FIELD}_NOT_CONTAINS": "string"
  }
```

{% hint style="info" %}
The {TAG} can be replaced with **KPI.** Because of legacy reasons this is not yet METRIC..
{% endhint %}

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
    "KPIID": "string",
    // or
    "KPIID_NOT": "string",
    // or
    "KPIID_IN": [
      "string"
    ],
    // or
    "KPIID_CONTAINS": "string",
  }
}
```

#### Creating Metrics

{% swagger method="post" path="/metrics/create" baseUrl="https://{your_tenant}.dscribedata.com/api" summary="Create new metrics in the dScribe platform" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="body" type="array" required="true" %}
List of metrics to be stored in dScribe. See more details 

[here](https://dscribe-prod-i-app-customerapi.azurewebsites.net/v1/docs/#/Metric/post_metric_create)

.
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Metadata response" %}
```javascript
{
  "total": 0,
  "failed": 0,
  "retry": 0,
  "successful": 0,
  "time": 0
}
```
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="Request is badly formatted" %}
```javascript
{
  "code": "string",
  "message": "string"
}
```
{% endswagger-response %}
{% endswagger %}

Creating metrics is done by sending an array of metrics in the following shape:

```json
[
  {
    "NAME": "string",
    "DESC": "string",
    "DESCFULLTEXT": "string",
    "DESCHTML": "string",
    "REPORT": {
      "connect": [
        {
          "where": {
            "node": {
              "{TAG}ID": "string",
              "{TAG}ID_NOT": "string",
              "{TAG}ID_IN": [
                "string"
              ],
              "{TAG}ID_NOT_IN": [
                "string"
              ],
              "{TAG}ID_CONTAINS": "string",
              "{TAG}ID_NOT_CONTAINS": "string",
              "{FIELD}": "string",
              "{FIELD}_NOT": "string",
              "{FIELD}_IN": [
                "string"
              ],
              "{FIELD}_NOT_IN": [
                "string"
              ],
              "{FIELD}_CONTAINS": "string",
              "{FIELD}_NOT_CONTAINS": "string"
            }
          }
        }
      ]
    },
    "VIEW": {
      "connect": [
        {
          "where": {
            "node": {
              "{TAG}ID": "string",
              "{TAG}ID_NOT": "string",
              "{TAG}ID_IN": [
                "string"
              ],
              "{TAG}ID_NOT_IN": [
                "string"
              ],
              "{TAG}ID_CONTAINS": "string",
              "{TAG}ID_NOT_CONTAINS": "string",
              "{FIELD}": "string",
              "{FIELD}_NOT": "string",
              "{FIELD}_IN": [
                "string"
              ],
              "{FIELD}_NOT_IN": [
                "string"
              ],
              "{FIELD}_CONTAINS": "string",
              "{FIELD}_NOT_CONTAINS": "string"
            }
          }
        }
      ]
    }
  }
]
```

You can create up to 100 metrics in one go. Notice that the KPIID will be generated for you. You can get the ID by listing.

The REPORT and VIEW keys are meant to link the KPI you just created to already existing reports or datasets. These relations will be visible in the relations tab of the portal. If you want to link your metric to a report with the name "Test Report", you can send the following request:

```json
[
  {
    "NAME": "New Metric",
    "DESC": "This is a desc.",
    "DESCHTML": "<a>This is some href</a>",
    "REPORT": {
      "connect": [
        {
          "where": {
            "node": {
              "NAME": "Test Report",
              // or if you know the ID
              "REPORTID": "123"
            }
          }
        }
      ]
    }
  }
]
```

#### Updating Metrics

{% swagger method="post" path="/metrics/update" baseUrl="https://{your_tenant}.dscribedata.com/api" summary="Update existing metrics stored in the dScribe platform" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="body" type="array" required="true" %}
List of metrics that should be updated. Look at the swagger file 

[here](https://dscribe-prod-i-app-customerapi.azurewebsites.net/v1/docs/#/Metric/post_metric_update)

 for more info. 
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Metadata response" %}
```javascript
{
  "total": 0,
  "failed": 0,
  "retry": 0,
  "successful": 0,
  "time": 0
}
```
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="Request is badly formatted" %}
```javascript
{
  "code": "string",
  "message": "string"
}
```
{% endswagger-response %}
{% endswagger %}

Updating works the same way as creating, with the only exception that you have to pass in a KPIID for every item in the array together with the fields you want to update like so:

```json
[
  {
    "KPIID": "123",
    "NAME": "New Name",
    "REPORT": {
      "connect": [
        {
          "where": {
            "node": {
              "NAME": "Test Report",
              // or if you know the ID
              "REPORTID": "123"
            }
          }
        }
      ]
    }
  }
]
```

#### Deleting Metrics

{% swagger method="post" path="/metrics/list" baseUrl="https://{your_tenant}.dscribedata.com/api" summary="Delete metrics from the dScribe platform" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="body" type="string[]" required="true" %}
An array of IDs that have to be removed.
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="List of metrics" %}
```javascript
{
  "total": 0,
  "failed": 0,
  "retry": 0,
  "successful": 0,
  "time": 0
}
```
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="Request is badly formatted" %}
```javascript
{
  "code": "string",
  "message": "string"
}
```
{% endswagger-response %}
{% endswagger %}

Deleting metrics is straightforward, just pass an array of ids to the call and the rest will be done for you:

```javascript
["123", "456"]
```
