# GoogleOAuth2Example
### Google Sign-In manages the OAuth 2.0 flow and token lifecycle, simplifying your integration with Google APIs. A user always has the option to revoke access to an application at any time.

## Create authorization credentials
Any application that uses OAuth 2.0 to access Google APIs must have authorization credentials that identify the application to Google's OAuth 2.0 server. The following steps explain how to create credentials for your project. Your applications can then use the credentials to access APIs that you have enabled for that project.

- Go to the <a src="https://console.cloud.google.com/apis/credentials">Credentials page.</a>
- Click Create credentials > OAuth client ID.
- Select the Web application application type.
- Name your OAuth 2.0 client and click Create

After configuration is complete, take note of the client ID that was created. You will need the client ID to complete the next steps. (A client secret is also created, but you need it only for server-side operations.)

## Load the Google Platform Library
You must include the Google Platform Library on your web pages that integrate Google Sign-In. <br />
<code><script src="https://apis.google.com/js/platform.js" async defer></script></code><br />

Specify the client ID you created for your app in the Google Developers Console with the google-signin-client_id meta element. <br />
<code>&lt;meta name="google-signin-client_id" content="YOUR_CLIENT_ID.apps.googleusercontent.com"&gt;</code><br />
<blockquote>Note: You can also specify your app's client ID with the client_id parameter of the gapi.auth2.init() method.</blockquote>
