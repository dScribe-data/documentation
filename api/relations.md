---
description: Before we go on to the actual examples, a note on relations.
---

# Relations

The metadata stored within dScribe is represented as a graph. This means relations between the different nodes are treated as a first class citizen. The API supports connecting and disconnecting nodes.

The relations can be found in the dScribe application under the relation tab:

![Relations tab within the dScribe portal](../.gitbook/assets/relations.png)

Let us take the same example as before:

{% swagger method="post" path="/report/update" baseUrl="https://your_tenant.dscribedata.com/api" summary="" %}
{% swagger-description %}
This query will update the reports passed in. 
{% endswagger-description %}

{% swagger-parameter in="body" name="body" type="json" %}

{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
  "failed": 0,
  "retry": 0,
  "successful": 0,
  "time": 0,
  "total": 0
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

The request body looks like this:

```json
[
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
    },
    "REPORT": {
      "connect": [
        {
          "where": {
            "node": {
              "{FIELD}": "string",
              "{FIELD}_CONTAINS": "string",
              "{FIELD}_IN": [
                "string"
              ],
              "{FIELD}_NOT": "string",
              "{FIELD}_NOT_CONTAINS": "string",
              "{FIELD}_NOT_IN": [
                "string"
              ]
            }
          }
        }
      ],
      "disconnect": [
        {
          "where": {
            "node": {
              "{FIELD}": "string",
              "{FIELD}_CONTAINS": "string",
              "{FIELD}_IN": [
                "string"
              ],
              "{FIELD}_NOT": "string",
              "{FIELD}_NOT_CONTAINS": "string",
              "{FIELD}_NOT_IN": [
                "string"
              ]
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
              "{FIELD}": "string",
              "{FIELD}_CONTAINS": "string",
              "{FIELD}_IN": [
                "string"
              ],
              "{FIELD}_NOT": "string",
              "{FIELD}_NOT_CONTAINS": "string",
              "{FIELD}_NOT_IN": [
                "string"
              ]
            }
          }
        }
      ],
      "disconnect": [
        {
          "where": {
            "node": {
              "{FIELD}": "string",
              "{FIELD}_CONTAINS": "string",
              "{FIELD}_IN": [
                "string"
              ],
              "{FIELD}_NOT": "string",
              "{FIELD}_NOT_CONTAINS": "string",
              "{FIELD}_NOT_IN": [
                "string"
              ]
            }
          }
        }
      ]
    }
  }
]
```

Notice the keys REPORT and VIEW? This means that a REPORT can be linked to other REPORTs and VIEWs.

{% hint style="info" %}
The relations the API supports right now are: **REPORT, VIEW, COLUMN**
{% endhint %}

Connecting and disconnecting can be controlled via the connect and disconnect key. Sending a body like this will connect REPORT 1 with REPORT 2.

{% hint style="danger" %}
Only one type of connection can be made at any given time. In other words, you can only connect a REPORT with another REPORT or a VIEW. You cannot connect a REPORT with another REPORT and VIEW **in one call**. You will have to split them up.
{% endhint %}

```json
[
  {
    "REPORTID": "REPORT 1",
    "REPORT": {
      "connect": [
        {
          "where": {
            "node": {
              "REPORTID": "REPORT 2"
            }
          }
        }
      ]
    }
  }
]
```

Look at the fields reference to see what fields you can use within the API.

{% content-ref url="field-reference/reports-fields.md" %}
[reports-fields.md](field-reference/reports-fields.md)
{% endcontent-ref %}
