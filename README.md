# yin_grecaptcha_plugin

google recaptcha v2

## Getting Started

use **Google ReCAPTCHA V2** (not V3)

Obtain your own key & secret here: https://www.google.com/recaptcha

Put `RecaptchaV2` widget into your widget tree (Usually inside `Stack` widget), **make sure it's placed on top of the tree and block all the behind interactions**:

```
RecaptchaV2Controller recaptchaV2Controller = RecaptchaV2Controller();
...
RecaptchaV2(
	apiKey: "YOUR_API_KEY", // for enabling the reCaptcha
	apiSecret: "YOUR_API_SECRET", // for verifying the responded token
	controller: recaptchaV2Controller,
	onVerifiedError: (err){
		print(err);
	},
	onVerifiedSuccessfully: (success) {
		setState(() {
		if (success) {
			// You've been verified successfully.
		} else {
			// "Failed to verify.
		}
		});
	},
),
```

The `RecaptchaV2` widget is hidden by default, you need to attach the `RecaptchaV2Controller` and call `show()` method when needed. Like this:
```
recaptchaV2Controller.show();
```

Manually hide it:
```
recaptchaV2Controller.hide();
```

That's it!