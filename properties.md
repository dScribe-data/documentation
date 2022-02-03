---
description: Before we go on to the actual examples, a note on properties.
---

# Properties

Properties are used within the dScribe application to enrich your objects with extra metadata. Next to that, they are used to control what is visible to users logging in.

### Reading

Take the previous request:

{% swagger method="post" path="/report/list" baseUrl="https://your_tenant.dscribedata.com/api" summary="" %}
{% swagger-description %}
This query will return the first 25 results. You can use the skip and limit parameters to build in pagination.
{% endswagger-description %}

{% swagger-parameter in="body" name="body" type="json" %}

{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
  "metadata": {
    "total": 0
  },
  "results": [
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
      }
    }
  ]
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

The response looks something like this:

```json
{
  "metadata": {
    "total": 0
  },
  "results": [
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
      }
    }
  ]
}
```

Notice the PROPERTIES key. This key will be populated with all the readable ids and values of the properties assigned to the object. The readable ids (API handles) can be found in the dScribe application administration portal.

![API Handle found in the dScribe administration portal](<.gitbook/assets/api handle.png>)

### Writing

Take the following request:

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

The body looks something like this:

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

Again notice the PROPERTIES key. In this call you can pass in the same API handles as discussed in the previous section. The properties passed in here **have to exist in the portal.** If you pass in properties that do not exist, the request will fail.

{% hint style="info" %}
You cannot create new properties via the API.
{% endhint %}

The entire properties object will be overwritten when updated this way. If you want to merge with existing properties, you will first have to fetch the existing data via a /list call and afterwards update with the properties you would like to see added.
