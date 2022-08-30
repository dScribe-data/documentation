---
description: Configuring asset types in dScribe
---

# Asset Types

Each asset in dScribe is of a specific type. The asset type indicates the purpose of the asset and comes with its own properties and layout settings.

Asset Types can be managed in the **Admin Portal > Asset Types**.

## Asset Properties

Each asset comes with various properties to provide users with more information on that asset. There are 3 categories of properties:

<details>

<summary>Standard Properties</summary>

These properties are available by default and cannot be changed. They include the following information:

* **Name**\
  ****The name of the asset. If the asset was crawled from a source system, the name cannot be changed.
* **Description**\
  ****A rich text field which can be used to describe the asset. Can include links, images & more.
* **Status**\
  ****The validation status of the asset.
* **Created On Date**\
  When the asset was created or loaded for the first time in dScribe.
* **Created By Date** \
  If the asset was manually registered: who created the asset in dScribe.
* **Last Changed On Date**\
  When the asset was last changed in dScribe.
* **Last Changed By Date** \
  Who last changed the asset in dScribe.
* **Source**\
  If crawled via a connector, the name of the source.&#x20;

</details>

<details>

<summary>Source Properties</summary>

These Properties available by default for assets that were automatically crawled from a source system. They include additional information retrieved from the source:

* **Category**  \
  The object type according to the terminology used in the source system. For example: 'SAP Analytics Cloud - Story'.
* **Created On Date** \
  When the asset was created in the source system.
* **Created By Date**\
  Who created the asset in the source system.
* **Last Changed On Date**\
  When the asset was last changed in the source system.
* **Last Changed By Date**\
  Who last changed the asset in the source system.
* **Additional source-specific properties**\
  For example: 'Workspace' for Power BI assets, 'Schema' for SQL Server assets, etc.

</details>

<details>

<summary>Custom Properties</summary>

Additional custom properties can be added to each asset type to further enrich the type of information you can document.

Custom properties are created and linked to specific asset types via the Properties page. For more information, see [custom-properties.md](custom-properties.md "mention").

</details>

## Layout

Each asset detail page includes a General tab, on which the description of the asset and some key information such as the asset's status is displayed. Below the description field, the Custom Properties configured for the asset type are listed. Custom Properties are always grouped in **Sections**.

Administrators can create additional sections and rearrange the linked Custom Properties as desired. For more information, watch the video below:

{% embed url="https://dscribevault.sharepoint.com/:v:/s/TheVault-SupportDesk/ETNyAQ52H5NBuu-FZc5Jm6kBXlN4f2_RYRIYykEajyIrkg?e=exnjUJ" %}
Learning Video: Configuring the layout of asset types
{% endembed %}
