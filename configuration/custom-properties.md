---
description: Configuring custom properties in dScribe
---

# Custom Properties

Custom properties can be used to introduce concepts specific to your organization into dScribe. They are used to further enrich the documentation of assets, facilitate filtering and support granular access policies.

Custom properties can be managed via the **Admin Portal > Properties**.

## Property Types

Each property is of a specific type, defining its behaviour and available options. &#x20;

### Properties of type Dropdown

Includes the following property types:

* **Dropdown list - single select**\
  A list of values from which one value can be selected per asset.&#x20;
* **Dropdown list - multiple select**\
  A list of values from which multiple values can be selected per asset.&#x20;
* **Dropdown hierarchical - multiple select**\
  A hierarchical list of values from which multiple values can be selected per asset. Only leaf nodes (= the values without child values) can be selected from the list.

Properties of any of these types can be used to document assets, filter search results, define the context of Contribution Access Policies.

### Properties of type Text

Includes the following property types:

* **Single Line Text**\
  ****A simple text field without formatting options.
* **Rich Text Editor**\
  A text field with formatting options, the ability to add Mentions to assets or users and the ability to upload images.&#x20;

Properties of any of these types can be used to document assets.&#x20;

## Mandatory Properties

By setting a property as required, this input field will always need to be filled in on asset types where the property is present. Specifically:

* when creating a new asset
* when editing a crawled asset where the property is not yet filled in

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption><p>Setting a custom property as mandatory</p></figcaption></figure>

{% hint style="warning" %}
We of course want the documentation on each asset in dScribe to be as complete as possible. However, it is often a bad idea to force properties to be filled in via this setting for the following two reasons:

* It increases the hurdle for users to contribute to your documentation. The more mandatory input fields, the more work it becomes to add something to dScribe.
* It increases the risk of inaccurate documentation. Users who do not know the correct value for a mandatory input field will often pick a wrong value to be able to continue.   &#x20;
{% endhint %}

## Security-enabled Properties

If you would like to use a custom property as context for your authorization model, you can set that property as security enabled:

<figure><img src="../.gitbook/assets/image (5) (2).png" alt=""><figcaption><p>Setting a property as security-enabled</p></figcaption></figure>

&#x20;Doing so will make that property available when defining Contribution Policies:

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption><p>Using a security-enabled property to define the context of a Contribution Policy</p></figcaption></figure>

In the example above, users receive Create+Edit+Delete permissions on all asset types where Subject Area = _Unassigned_ or 'Sales'.

Note that only properties of type dropdown can be security-enabled.

## Rearranging custom properties per Asset Type&#x20;

Each custom property can be linked to any of the asset types in dScribe. Once they have been linked to an asset type, they can be rearranged in that asset type's layout. See [#layout](asset-types.md#layout "mention").
