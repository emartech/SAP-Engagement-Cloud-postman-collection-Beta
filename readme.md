# SAP Engagement Cloud - Beta Developer Tooling
**Please note that SAP Engagement Cloud is in the 'closed pilot' phase, with general availability expected in the near future.** 

**Written in the Postman format and tested with Bruno**

This document describes the Emarsys Suite API v3, which uses OpenID Connect (OAuth 2.0 client credentials grant) authentication. 

- Introduction to Emarsys API: [link](https://help.sap.com/docs/SAP_EMARSYS/8bf21e3e3ad3475bb9e25de1e0ac3d86/fdf6b8c874c11014ab07d03045e4962a.html)
- Creating your API credentials: [link](https://help.sap.com/docs/SAP_EMARSYS/5d44574160f44536b0130abf58cb87cc/fdf4b58974c110149353957a3e7ef453.html#openid-connect)

### For an open source alternative to Postman, this collection is also compatible with Bruno, as described [here](#Using-this-collection-with-Bruno).

## Creating your API user

To create your API user, follow [this documentation guide for OpenID Connect](https://help.sap.com/docs/SAP_EMARSYS/5d44574160f44536b0130abf58cb87cc/fdf4b58974c110149353957a3e7ef453.html#openid-connect)

> [!NOTE]
> Be sure to copy your all of the credential details from the gray text boxes to a secure location immediately, as you won't be able to access them again!


## Using with Postman

### Installing the collection in Postman
1. First, make sure you have Postman installed. These collections are meant to be used with the program Postman, which can be downloaded here: https://www.postman.com/downloads/
1. Download this repository by clicking on the Green "Code" button at the top of this page, then "Download Zip":
  ![Graphic displaying the location of the "code" and "download ZIP" buttons on the current github page](./readme-images/github-download-steps.png)
3. Extract the files from the .zip folder
4. With Postman installed and the collections downloaded, click on the import button in the top-left:
  ![Postman import button](./readme-images/import-button.png)
1. Select The upload files option:
    ![Postman upload files option](./readme-images/upload-files-button.png)
1. Select the file "Emarsys Postman Collection" from the downloaded files
    ![Postman file selector with "Emarsys Postman Collection" highlighted](./readme-images/file-selector-oauth.png)
1. Finally, select the import button to confirm and the package will be fully installed!
 
### Setting up your API user in Postman

1. In Postman, click on the folder for the Emarsys API collection, then select the Authorization tab
1. Scroll down to the "Configure New Token" section where you will see red text in the boxes for Client ID and Client Secret
![The program Postman, with the Authorization configuration panel open for the collection called "Emarsys - Suite and Sales APIs - V3. There is a large red circle around the parameters for Client ID and Client Secret, which highlights the red text {{OIDC_ClientID}} and {{OIDC_Secret}}, respectively."](./readme-images/postman-oauth-configuration.png)
1. Hover your mouse over the red text for {{OIDC_ClientID}} to see the options of where to store this variable. Click the Environment section to save the variable. If you see text that says "No environment selected", click "Create One" and give it a name like "Emarsys environment"

    ![The program Postman, with the Authorization configuration panel open for the collection called "Emarsys - Suite and Sales APIs - V3. That page is scrolled to view the parameters for Client ID and Client Secret, with placeholder text of {{OIDC_ClientID}} and {{OIDC_Secret}}. Above those fields is a dialog window that says "add variable to" with options for Environment, Collection, Globals, and Vault. There is a large red circle around the option "Create One" next to the Environment option."](./readme-images/postman-configure-new-environment.png)
1. In the "Enter Value" checkbox, enter the value you saved from the Emarsys API user creation screen. Do this for Client ID and Client Secret. The text for each will turn from red to blue once it's configured correctly
    **Note** If you are using [SAP Cloud Identities](https://help.emarsys.com/hc/en-us/articles/22036625729554-Security-settings-API-Credentials#openid-connect-sap-cloud-identity) to manage your Emarsys API credentials, you will need to replace the Access Token URL as well
1. Scroll to the bottom of the window and click the Orange "Get New Access Token" button. Postman will take a moment to make sure your credentials work, then report it was successful. Click "Proceed" on this window, then click "Use Token"
1. Your credentials are now configured!

### Configuring your Base URL

In the Engagement Cloud edition of the Emarsys APIs, you will need to specify the API endpoint that your account uses for your requests. During the beta, that endpoint will always be `https://api.sap.emarsys.net/api`. In the future, you will be able to find it in the same page as your API users' permissions.

Here's how to set the endpoint in your environment:

1. Find out your endpoint (`https://api.sap.emarsys.net/api` will always be the correct endpoint while in Beta)
1. Click on the Environments dropdown in the top-right corner of Postman (it will display the name of your current environment if you have one selected)
1. Click the arrow icon next to the evironment you'd like to use, or click the 'plus' button next to the search bar to create a new one
1. Type "baseUrl" into the Variable column where it says "Add Variable" and for the value, paste your endpoint found in step 1.

Your environment should look like this:

![The program Postman, with the Environments editiong window open. There is a table of data with columns 'variable' and 'value'. The entries are the variable 'OIDC_ClientID' with no value, 'OIDC_Secret' with no value, and 'baseUrl' with a value of 'https://api.sap.emarsys.net/api'."](./readme-images/postman-beta-environment-with-baseUrl.png)

#### Once your API user and base url are configured as explained above, you're ready to start using the Postman collection!


# Using this collection with Bruno

[Bruno](https://docs.usebruno.com/) is an open-source API tool that is very similar to Postman, but is fully free to use and is supported by the Open-Source community.

### Installing the collection in Bruno

1. Make sure you have Bruno installed. You can download Bruno here: https://www.usebruno.com/downloads
1. Download this repository by clicking on the Green "Code" button at the top of this page, then "Download Zip":

    ![Graphic displaying the location of the "code" and "download ZIP" buttons on the current github page](./readme-images/github-download-steps.png)

1. Extract the files from the .zip folder
1. With Bruno downloaded and the collections downloaded, click on the Import Collection button:

    ![Graphic displaying the location of the "Import Collection" button in Bruno's UI](./readme-images/bruno-import-button.png)

1. Select "Postman Collection" for the collection type
1. Select the file "Emarsys_postman_collection.json" from the files you downloaded previously and press open:

    ![Graphic displaying the file selector for importing Postman collection files into Bruno](./readme-images/bruno-file-selector.png)

1. Bruno will then ask you where you'd like to save the imported collection. Select any location on your computer you would like to store your work in Bruno. A good option may be your Documents folder, or a project folder where you keep your work on Emarsys. After you do so, the API collection will be visible in Bruno.

1. Begin setting up your authentication to the API by clicking on the name of the collection in the left-hand menu and then selecting the tab "Auth". In that page, apply the following settings:

    - Set the "Grant Type" dropdown to "Client Credentials"
    - Set the Access Token URL to "https://auth.emarsys.net/oauth2/token"
    - Set the Client ID to {{OIDC_CLIENT_ID}}
    - Set the Client Secret to {{OIDC_SECRET}}
    - Set the "Add Credentials to" dropdown to "Basic Auth Header"
    - Lower down, in the Settings section, check the box for "Automatically fetch token if not found"
    - Click "Get Access Token" to test the settings
    - Click Save

    ![Graphic displaying the Auth settings page for Bruno to configure Oauth](./readme-images/bruno-configuring-auth-page.png)

1. Bruno is now configured and ready for you to fill in your API credentials. Follow the steps for configuring your environments in the next section before sending your first request

### Setting up your API user in Bruno

This collection uses Bruno Environment Variables to manage the credentials for the account(s) you work with.
![A sample of a fully-configured Bruno Environment, with variables OIDC_CLIENT_ID and OIDC_SECRET set](./readme-images/bruno-sample-oauth-environment-config.png)
[This guide goes over how to create those environments](https://docs.usebruno.com/secrets-management/secret-variables)

The required variables are:
- OIDC_CLIENT_ID
- OIDC_SECRET
- baseUrl

The baseUrl variable is the endpoint for API requests, which will always be `https://api.sap.emarsys.net/api` during the beta.

In the Engagement Cloud edition of the Emarsys APIs, you will need to specify the API endpoint that your account uses for your requests. During the beta, that endpoint will always be `https://api.sap.emarsys.net/api`. In the future, you will be able to find it in the same page as your API users' permissions.

> [!NOTE] 
> If you are using [SAP Cloud Identities](https://help.emarsys.com/hc/en-us/articles/22036625729554-Security-settings-API-Credentials#openid-connect-sap-cloud-identity) to manage your Emarsys API credentials, you will need to add your Access Token URL in the variable "OIDC_SCI_HOST"
