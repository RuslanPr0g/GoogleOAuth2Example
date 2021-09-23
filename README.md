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

<br /><br />

## Add a Google Sign-In button
The easiest way to add a Google Sign-In button to your site is to use an automatically rendered sign-in button. With only a few lines of code, you can add a button that automatically configures itself to have the appropriate text, logo, and colors for the sign-in state of the user and the scopes you request.<br />

To create a Google Sign-In button that uses the default settings, add a div element with the class g-signin2 to your sign-in page: <br />
<code>&lt;div class="g-signin2" data-onsuccess="onSignIn"&gt;&lt;/div&gt;</code><br />

## Get profile information
After you have signed in a user with Google using the default scopes, you can access the user's Google ID, name, profile URL, and email address.<br />

To retrieve profile information for a user, use the getBasicProfile() method.<br />
<code>
  function onSignIn(googleUser) {
  var profile = googleUser.getBasicProfile();
  console.log('ID: ' + profile.getId()); // Do not send to your backend! Use an ID token instead.
  console.log('Name: ' + profile.getName());
  console.log('Image URL: ' + profile.getImageUrl());
  console.log('Email: ' + profile.getEmail()); // This is null if the 'email' scope is not present.
}
</code><br />
<blockquote>Important: Do not use the Google IDs returned by getId() or the user's profile information to communicate the currently signed in user to your backend server. Instead, send <a src="https://developers.google.com/identity/sign-in/web/backend-auth">ID tokens</a>, which can be securely validated on the server.</blockquote>



