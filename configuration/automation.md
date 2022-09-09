---
description: Managing automations in dScribe
---

# Automation

Don't want to manually document every asset in dScribe? We feel you! While some documentation and governance efforts will always require human contributions, you can save yourself from a lot of the manual work by leveraging automations in dScribe.&#x20;

Automations can be used to automatically:

* assign Property values to assets&#x20;
* assign Teams to assets
* restrict the discovery of assets

Automations can be managed in the **Admin Portal > Automation**.

The following video gives a quick introduction into the Automations functionality:

{% embed url="https://www.youtube.com/watch?v=MpFVPd6BhQA" %}
Learning Video: Creating Automations
{% endembed %}

## Defining an automation

### When and Then statements

Each automation includes a when statement and a then statement:

<figure><img src="../.gitbook/assets/image (6) (2).png" alt=""><figcaption></figcaption></figure>

#### When statement

This statement defines the conditions that need to be fulfilled before the execution of an automation is triggered. When defining your initial conditions, more options gradually become available. For example, when you define that an asset is created, coming from a Source of type 'SAP Analytics Cloud', you will be able to use Source Metadata specific to that source type to add additional conditions:

<figure><img src="../.gitbook/assets/image (4) (1).png" alt=""><figcaption></figcaption></figure>

Note also that every circled part of your conditions can be clicked to change its value:&#x20;

<figure><img src="../.gitbook/assets/image (1) (1).png" alt=""><figcaption></figcaption></figure>

#### Then statement

This statement defines what actions should happen if the when statement of an automation is fulfilled. The list of available actions depend on the type of conditions you have included in the when statement.&#x20;

### Key operators

#### Exact match

An exact match will always look for a precise, capital-sensitive text match. Any special characters, for example <mark style="color:orange;">**\***</mark> or <mark style="color:orange;">**%**</mark> will be considered as text. For example, the automation below will execute for all assets stored directly in the Ancester Path "Public / Finance": ![](<../.gitbook/assets/image (9).png>)

#### RegEx match

With a RegEx match, you can determine more complex text matches. For example, a wildcard can be included with the characters <mark style="color:orange;">**.\***</mark>. The automation below will execute for all assets stored under the Ancester Path "Public / Finance" + any subfolders + any other folders under "Public" that start with "Finance":\
![](<../.gitbook/assets/image (3) (2).png>)

RegEx expressions might take some getting used to. A good introduction can be found [here](https://regexone.com/).

## Automation Status

Each automation can be set to State = Active or Inactive. Automations with State = Inactive will not run until they are set to Active.

## Example Automation

The example below shows an automation that will automatically set the Property Domain to 'Finance' for any newly created reports or datasets coming from Source 'SAP Analytics Cloud reporting' and stored in  the folder 'Public / Finance':

<figure><img src="../.gitbook/assets/image (7) (2).png" alt=""><figcaption></figcaption></figure>

&#x20;
