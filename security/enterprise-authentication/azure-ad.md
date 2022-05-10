---
description: >-
  This document explains the steps needed to login with Azure AD into the
  dScribe application.
---

# Azure AD

### 1. Go to Azure Active Directory (AAD)

a.     Go to [https://portal.azure.com/#home](https://portal.azure.com/#home)

b.     Select Azure Active Directory:

![](<../../.gitbook/assets/Picture 1.png>)

### 2. Create an app registration

![](../../.gitbook/assets/Picture2.png)

![](../../.gitbook/assets/Picture3.png)

{% hint style="info" %}
remember the name of your application, you will need it later
{% endhint %}

### 3. Go to the newly created application and click on authentication. Select create add a platform.

Select web and enter the following redirect url: [https://dscribedata.eu.auth0.com/login/callback](https://dscribedata.eu.auth0.com/login/callback).

![](../../.gitbook/assets/platformconfig.png)

### 4. API permissions tab&#x20;

and check if the following permissions are granted: **User.Read and Directory.Read.All**

![](../../.gitbook/assets/apipermissions.png)

### **5. Token configuration**

Make sure at least the email is included in the token:

![](../../.gitbook/assets/tokenconfig.png)

### 6. Application

Navigate back to your application via Azure Active Directory > App Registrations > Select your newly created App and copy the **Application (client) ID** somewhere safe. You will need it later.

![](../../.gitbook/assets/appid.png)

### 7. Client Secret

In your application, navigate to 'Certificates & secrets' and create a new client secret:

![](../../.gitbook/assets/createsecret.png)

and copy your client secret (it will not appear again once you navigate away from the page):

![](../../.gitbook/assets/copysecret.png)

### 8. Tenant ID

Go back to Azure Active Directory > Overview and copy the **Tenant ID**

![](../../.gitbook/assets/tenantid.png)
