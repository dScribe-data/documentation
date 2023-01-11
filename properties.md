---
description: Before we go on to the actual examples, a note on properties.
---

# Properties

Properties are used within the dScribe application to enrich your objects with extra metadata. Next to that, they are used to control what is visible to users logging in.

### Reading

Take the previous request:

{% swagger src=".gitbook/assets/openapi (7).yaml" path="/report/list" method="post" %}
[openapi (7).yaml](<.gitbook/assets/openapi (7).yaml>)
{% endswagger %}

Notice the PROPERTIES key. This key will be populated with all the readable ids and values of the properties assigned to the object. The readable ids (API handles) can be found in the dScribe application administration portal.

![API Handle found in the dScribe administration portal](<.gitbook/assets/api handle.png>)

### Writing

Take the following request:

{% swagger src=".gitbook/assets/openapi (7).yaml" path="/report/create" method="post" %}
[openapi (7).yaml](<.gitbook/assets/openapi (7).yaml>)
{% endswagger %}

Again notice the PROPERTIES key. In this call you can pass in the same API handles as discussed in the previous section. The properties passed in here **have to exist in the portal.** If you pass in properties that do not exist, the request will fail.

{% hint style="info" %}
You cannot create new properties via the API.
{% endhint %}

The entire properties object will be overwritten when updated this way. If you want to merge with existing properties, you will first have to fetch the existing data via a /list call and afterwards update with the properties you would like to see added.
