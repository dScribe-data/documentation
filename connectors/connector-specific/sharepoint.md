# Sharepoint

### Summary

This document explains the steps needed to prepare your Sharepoint environment for setting up a dScribe connection.&#x20;

### Step-by-step guide

1. Navigate to [Microsoft Azure Portal](https://portal.azure.com) and log in with a user with Admin permissions.\

2. Register a new app:\
   ![](../../.gitbook/assets/sharepoint\_appreg.png)![](../../.gitbook/assets/sharepoint\_appreg2.png)![](../../.gitbook/assets/sharepoint\_appreg3.png)\
   \
   Save your Tenant Id and your Client Id, you'll need it later:\
   ![](../../.gitbook/assets/sharepoint\_appreg4.png)\

3. Add API permissions:\
   ![](../../.gitbook/assets/sharepoint\_apiperm.png)![](../../.gitbook/assets/sharepoint\_apiperm2.png)![](../../.gitbook/assets/sharepoint\_apiperm3.png)![](../../.gitbook/assets/sharepoint\_apiperm4.png)![](../../.gitbook/assets/sharepoint\_apiperm5.png)![](../../.gitbook/assets/sharepoint\_apiperm6.png)\

4. Grant admin consent:\
   ![](../../.gitbook/assets/sharepoint\_apiperm7.png)\
   You will need to be to be an Admin to grant admin consent, login as an admin or contact someone who is an admin.\

5. Create a Client Secret:\
   ![](../../.gitbook/assets/sharepoint\_secret.png)![](../../.gitbook/assets/sharepoint\_secret2.png)\
   \
   Save your Client Secret somewhere safe, you'll need it later. \
   ![](../../.gitbook/assets/sharepoint\_secret3.png)\

6. Using the Tenant Id, Client Id and Client Secret**,** you can now create a new Source with these connection details in dScribe.

**Reached the end? Congratulations! You’re a star!** :star:****
