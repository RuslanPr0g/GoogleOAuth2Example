# GoogleOAuth2Example
### Google Sign-In manages the OAuth 2.0 flow and token lifecycle, simplifying your integration with Google APIs. A user always has the option to revoke access to an application at any time.

## Create authorization credentials
Any application that uses OAuth 2.0 to access Google APIs must have authorization credentials that identify the application to Google's OAuth 2.0 server. The following steps explain how to create credentials for your project. Your applications can then use the credentials to access APIs that you have enabled for that project.

- Go to the <a src="https://console.cloud.google.com/apis/credentials">Credentials page.</a>
- Click Create credentials > OAuth client ID.
- Select the Web application application type.
- Name your OAuth 2.0 client and click Create

After configuration is complete, take note of the client ID that was created. You will need the client ID to complete the next steps. (A client secret is also created, but you need it only for server-side operations.)

