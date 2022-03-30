# Google Drive

### Summary

This document explains the steps needed to prepare your Google Drive environment for setting up a dScribe connection. dScribe uses a Service Account provided by Google Cloud Platform.

### Step-by-step guide

1. Navigate to [Google Cloud Platform](https://console.cloud.google.com) and log in with a user with Admin permissions.
2. Create a new project: \
   ![](../../.gitbook/assets/googledrive\_createProject.png)![](../../.gitbook/assets/googledrive\_createProject2.png)\

3.  Create a **Service Account** in your project via Menu > 'IAM & Admin' > 'Service Accounts':\
    ![](../../.gitbook/assets/googledrive\_creatingServiceAccount.png)

    \
    Enter a name and continue.\
    \
    Select role 'Owner' or 'Viewer'.\
    \
    ![](<../../.gitbook/assets/Screenshot 2022-03-30 at 13.55.16.png>)\
    \
    Click done.\
    \
    Save your Service Account email adress, you'll need it later:\
    ![](../../.gitbook/assets/googledrive\_createPrivateKey1.png)\

4. Create a **privateKey** for your Service Account:\
   Click on your Service Account name > KEYS > Add Key > Create a new key:\
   ![](../../.gitbook/assets/googledrive\_createPrivateKey1.png)![](../../.gitbook/assets/googledrive\_createPrivateKey2.png)![](../../.gitbook/assets/googledrive\_createPrivateKey3.png)\
   \
   Keep Key Type = JSON. When you click on 'Create', a file will be downloaded with your **privateKey**. **** \

5.  The **privateKey** needs to be **base64 encoded**:

    You can do this by going to [base64encode.org](https://www.base64encode.org). Paste your privateKey and click on encode.\
    ![](../../.gitbook/assets/googledrive\_encodedPrivateKey.png)

    \
    Save your encoded privateKey somewhere safe, you'll need it later. \

6.  Enable **Google Drive API** on the project that you want to use:

    In your menu bar, you can find **'API & Services' > 'Library'**. On this page you can search for the **Google Drive API** and enable it.\
    ![](../../.gitbook/assets/googledrive\_enableApi2.png)![](../../.gitbook/assets/googledrive\_enableApi.png)\

7.  Go to your [Google Drive](https://drive.google.com) and choose the folders you want to connect. You'll have to share these folders with your Service Account. This is the Service Account email adress you saved earlier.\
    ![](../../.gitbook/assets/googledrive\_shareDrive.png)\


    Paste the email adress of your Service Account and choose 'Editor' or 'Reader'.\
    ![](../../.gitbook/assets/googledrive\_shareDrive2.png)\

8. Using the **email adress of your Service Account** and **the base64 encoded** **Private key,** you can now create a new Source with these connection details in dScribe.

**Reached the end? Congratulations! You’re a star!** :star:****









