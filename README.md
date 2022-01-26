# Mono Vanilla Javascript
This is a simple HTML and vanilla Javascript implementation of the Mono Connect widget. To get started:

## Step 1: Clone this repository
e.g _Using HTTPS_:
```
git clone https://github.com/withmono/Vanilla-javascript-for-mono-connect.git
```

_Alternatively, if you use ssh_:
```
git clone git@github.com:withmono/Vanilla-javascript-for-mono-connect.git
```

## Step 2: Update your public key
Open the `index.html` file in your preferred text editor, update the config object with your public key gotten from the [Mono Dashboard](https://app.mono.co/apps)
```javascript
// from line 27
 var config = {
    key: "YOUR_PUBLIC_KEY_HERE", // enter your public key here
    scope:"auth",
    onSuccess: function (response) {
      copyToClipboard(response.code);
      console.log(JSON.stringify(response));
      alert(JSON.stringify(response));
      /**
       response : { "code": "code_xyz" }
       you can send this code back to your server to get this
       authenticated account and start making requests.
       */
    },
    onClose: function () {
      console.log('user closed the widget.')
    }
  };
```

And you're set!

The code gotten back after the widget authentication should be exchanged for a permanent **Account ID** using the [Exchange token](https://docs.mono.co/reference/authentication-endpoint) endpoint. You can then use the Account ID to request for data for the connected account.

## Reference
[Postman](https://documenter.getpostman.com/view/15068056/TzscomUB)\
[Mono Docs](https://docs.mono.co/docs)

## Support
If you're having general trouble with Mono Connect.js or your Mono integration, please reach out to us at hi@mono.co or come chat with us using Intercom on https://app.mono.co. We're proud of our level of service, and we're more than happy to help you out with your integration to Mono.
