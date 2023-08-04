---
description: Used to upload videos to YouTube channel
---

# 🔄 Google OAuth 2.0

{% hint style="info" %}
**How to use?** \
\
Just give any name for the connection, press "Add" button, choose your Google account and allow all required permissions.

**Also** you can overwrite the default Google OAuth 2.0 client using _Client ID_ and _Client Secret_ parameters.
{% endhint %}

### Scope list

Default scope for every new connection:

* [https://www.googleapis.com/auth/youtube](https://www.googleapis.com/auth/youtube) - Manage YouTube channel
* [https://www.googleapis.com/auth/youtube.upload](https://www.googleapis.com/auth/youtube.upload) - Manage videos on YouTube channel

### Parameters

**Client ID**

{% code overflow="wrap" %}
```javascript
{
    Name: "clientId"
    Type: "text"
    Required: false
    Advanced: true
}
```
{% endcode %}

**Client Secret**

{% code overflow="wrap" %}
```javascript
{
    Name: "clientSecret"
    Type: "text"
    Required: false
    Advanced: true
}
```
{% endcode %}
