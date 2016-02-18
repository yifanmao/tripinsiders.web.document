# Third party log in
------
## [Facebook](https://developers.facebook.com/docs/facebook-login/manually-build-a-login-flow)

### 1. Invoking the login dialog

```
<a href='https://www.facebook.com/v2.0/dialog/oauth?client_id={app-id}&redirect_uri={redirect-uri}&scope={scope}&state={state}'>Log in with Facebook</a>

```
This endpoint has the following required parameters:
> * `client_id`: The ID of your app, found in your app's dashboard.
> * `redirect_uri`: The URL that you want to redirect the person logging in back to. This URL will capture the response from the Login Dialog

It also has the following optional parameters:

> * `state`: An arbitrary unique string created by your app to guard against [Cross-site Request Forgery](http://en.wikipedia.org/wiki/Cross-site_request_forgery).
> * `scope`: A comma separated list of [Permissions](https://developers.facebook.com/docs/facebook-login/permissions/) to request from the person using your app.

This will return a code for step two

### 2. Get access token

```
https://graph.facebook.com/v2.3/oauth/access_token?client_id={app-id}&redirect_uri={first-step-redirect-uri}&client_secret={app-secret}&code={first-step-result}
```

Then it will return the access token

```
{"access_token":"",
"token_type":"",
"expires_in":5161818}
```

## 3. Get user info

```
https://graph.facebook.com/me?fields=id,name,email,cover&access_token={step-two-result}
```

Then it will return the user info

```
result:
{
"id": "",
"name": "",
"email": ""
}
```
