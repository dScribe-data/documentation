# Access Policies



Access Policies are used to implement your metadata governance policies in dScribe. They help define who is able to contribute to the documentation of assets, assign ownership, manage administration activities and gain access to restricted assets.

Each Access Policy exists out of one or more permissions. By assigning an Access Policy to a team, all users in that team are granted these permissions.

Note that no Access Policy is required for the following activities:

* searching for non-restricted assets
* commenting

3 types of Access Policies exist:

#### 1. Discovery Policy

By default, all assets in dScribe are freely discoverable by all users. If you do need to limit the discoverability of select assets, a Discovery Policy can be created. Each Discovery Policy represents one category of restricted assets. For example: 'Highly Sensitive'.

Users who have been assigned the 'Restrict Discovery' permission (see [2. Contribution Policy](access-policies.md#2.-contribution-policy)), will be able to associate assets with Discovery Policies. Users can only associate assets with Discovery Policies that have been assigned to them. Once an assets is associated with a Discovery Policy, it will only be visible to users who have been assigned this Discovery Policy.

Discovery-restricted assets will be indicated via the following icon:&#x20;

![](broken-reference)

{% hint style="info" %}
_dScribe best practice:_ broad discoverability of definitions and data support adoption throughout the organisation and increase value for each user. Since no actual data is exposed in any way, it is recommended to keep your usage of Discovery Policies to a minimum.
{% endhint %}

#### 2. Contribution Policy

This access policy type is used to define who can contribute in what way to the documentation of assets in dScribe. Several permissions can be granted:

* **Create**: the ability to create new assets.
* **Edit**: the ability to edit the description, Properties and Relations of existing assets.
* **Delete**: the ability to delete an asset.
* **Assign Ownership**: the ability to assign the ownership of an asset to one of the Teams in dScribe. Owners of an asset automatically receive edit and delete permissions. (Note that crawled catalog assets cannot be deleted.)
* **Restrict Discovery**: the ability to associate an asset with one of the existing [Discovery Policies](access-policies.md#1.-discovery-policy), thus restricting the asset's free discoverability in dScribe. Users with this permission can only associate assets with Discovery Policies that have also been assigned to them.

The above permissions can be restricted to a specific context, thus only allowing these actions in the appropriate context. The first restriction is based on Asset Type. If Security Properties have been enabled for the selected Asset Types, these can be used to further specify the context of your permissions. An example restricted context could be:\
\- Asset Type = _All Asset Types_\
\- Security Property 'Domain' = "Sales"

{% hint style="info" %}
_Good to know_: contribution permissions cannot be restricted on assets with Security Properties to which no value has been assigned yet. In the above example, users will be able to contribute both to assets with Domain = "Sales" and assets with Domain = _Unassigned_.
{% endhint %}

#### 3. Organisation Policy

This access policy type is used to grant access to the admin portal in dScribe. Via the admin portal, various administration activities can be conducted:

* **Manage Users**: the ability to create new and manage existing users. For users synchronised with an Identity Provider (see [Broken link](broken-reference "mention")), certain fields will be locked.
* **Manage Teams**: the ability to create new and manage existing teams. Includes the ability to manage which users are part of which team.&#x20;
* **Manage Access Policies**: the ability to create new and manage existing access policies. Includes the ability to (un)assign policies to teams.\

* **Manage Properties**: the ability to create new and manage existing properties.     \

* **Manage Sources**: the ability to create new and manage existing sources in dScribe. If a connector is available for this source, the appropriate connection details can be added to enable automatic metadata crawling of the source.
* **Manage Jobs**: the ability to execute ad-hoc or schedule repeated metadata crawling jobs, linked to one of the available sources with connection details setup.
* **Manage API Keys**: the ability to create new or manage existing API Keys, used for custom integrations with dScribe. \

* **View Analytics Dashboard**: access to the analytics dashboard, offering insights into the most active dScribe users, the most popular assets & more.
