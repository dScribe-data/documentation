---
description: Preparing Power BI for a dScribe connection
---

# Microsoft Power BI

### Summary

This document explains the steps needed to prepare your Power BI environment for setting up a dScribe connection.

For the official documentation by Microsoft, see [here](https://docs.microsoft.com/en-us/power-bi/admin/service-admin-metadata-scanning-setup).

### Step-by-step guide

1.  Go to Azure Active Directory (AAD)

    a.     Go to [https://portal.azure.com/#home](https://portal.azure.com/#home)

    b.     Select Azure Active Directory:\
    &#x20;       ![](<../../.gitbook/assets/image (9).png>)\

2.  Create an app registration\
    ![](<../../.gitbook/assets/image (13).png>)\
    \
    ![](<../../.gitbook/assets/image (12).png>)\
    \
    TIP 1: remember the name of your application, you will need it later

    &#x20;

    TIP 2: (important!) Make sure there are no Power BI admin-consent-required permissions set on this application.\

3. Navigate back to your application via Azure Active Directory > App Registrations > Select your newly created App and copy the **Application (client) ID** somewhere safe. You will need it later.\
   ![](<../../.gitbook/assets/image (5).png>)\

4. In your application, navigate to 'Certificates & secrets' and create a new client secret:\
   ![](<../../.gitbook/assets/image (2).png>)\

5. Copy the client secret **value**\
   ****![](<../../.gitbook/assets/image (4).png>)\

6. Go back to Azure Active Directory > Overview and copy the **Tenant ID**\
   ****![](../../.gitbook/assets/image.png)\

7. Create a new Security Group via Azure portal > Azure Active Directory > Groups (optional: you can choose to reuse an existing group)\
   ![](<../../.gitbook/assets/image (14).png>)\

8. Add your App (see Step 2) as a member of the security group you created\
   ![](<../../.gitbook/assets/image (8).png>)\

9. Navigate to PowerBI via app.powerbi.com and log in with a user with administrator authorizations\

10. Go to Admin portal > Tenant settings > Admin API settings

    a.     Set 'Allow service principles to use read-only Power BI admin APIs' to Enabled

    b.     Add the security group you created earlier\
    \
    ![](<../../.gitbook/assets/image (3).png>)\

11. While you're here, make sure these settings are applied as well: You can select ‘The entire organization’ or use the same security group as above.\
    ![](<../../.gitbook/assets/image (10).png>)\

12. Using the Tenant ID, Application (client) ID and secret value, create a new Connection in dScribe

#### All done! Congratulations!



### Known limitations

For older Power BI datasets, the dataset elements might not be retrieved when running the dScribe job. See [here](https://docs.microsoft.com/en-us/power-bi/admin/service-admin-metadata-scanning-setup#model-caching).
