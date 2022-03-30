# Google Drive

### Summary

This document explains the steps needed to prepare your Google Drive environment for setting up a dScribe connection. The connection we use is via 3 Service Account that Google Cloud Platform provides.

### Step-by-step guide

1.  Create, use and prepare a project in Google Platform or use an existing project.

    \
    We need a project in [Google Platform](https://console.cloud.google.com) to create a service account.

    1. To make a new project:\
       ![](../../.gitbook/assets/googledrive\_createProject.png)![](../../.gitbook/assets/googledrive\_createProject2.png)\

    2.  Enable **Google Drive API** on the project that you want to use:

        On the left sidebar you can find **'API & Services' > 'Library'**. On this page you can search for the **Google Drive API** and enable it.\
        ![](../../.gitbook/assets/googledrive\_enableApi2.png)![](../../.gitbook/assets/googledrive\_enableApi.png)





    3\. Create and preparing a **Service Account** in your project in Google Platform

    1.  Creating a **Service Account:**

        On the left sidebar you can find 'IAM & Admin' > 'Service Accounts'. On this page you can add a service account to your project\
        ![](../../.gitbook/assets/googledrive\_creatingServiceAccount.png)

        \
        While creating a Service Account, you'll need to add a name and a role. Choose the role owner or viewer.\
        ![](<../../.gitbook/assets/Screenshot 2022-03-30 at 13.55.16.png>)\
        \
        Save your Service Account email adress, you'll need it later.\

    2. Creating and preparing a **privateKey** for your Service Account:\

       1.  To create a key for your Service Account, you'll need to click on your Service Account name and click on 'Create a Key'.\
           ![](../../.gitbook/assets/googledrive\_createPrivateKey1.png)![](../../.gitbook/assets/googledrive\_createPrivateKey2.png)![](../../.gitbook/assets/googledrive\_createPrivateKey3.png)\


           When you click on 'Create', a file will be downloaded with your **privateKey.**&#x20;

           Example file:\
           ![](<../../.gitbook/assets/Screenshot 2022-03-30 at 13.59.08.png>)\

       2.  The **privateKey** needs to be **base64 encoded**:

           You can do this by going to [base64encode.org](https://www.base64encode.org). Paste your privateKey and click on encode.\
           ![](../../.gitbook/assets/googledrive\_encodedPrivateKey.png)

           \
           Save your encoded privateKey somewhere safe, you'll need it later. \

2. Preparing your **Google Drive** for connection.\
   (You will need the email adress of your Service Account)\

   1.  Go to your [Google Drive](https://drive.google.com) and choose the folders you want to connect. You'll have to share these folders to your Service Account:\
       ![](../../.gitbook/assets/googledrive\_shareDrive.png)\


       Paste the email adress of your Service Account and choose 'Editor' or 'Reader'.\
       ![](../../.gitbook/assets/googledrive\_shareDrive2.png)\

3. Using the **email adress of your Service Account** and **the base64 encoded** **Private key,** you can now create a new Connection in dScribe.

**Reached the end? Congratulations! You’re a star!** :star:****









