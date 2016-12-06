## What is this?

This is a quick way of distributing your iPhone/iPad applications to a limited group of people, either be it in your organization, or outside. 

This can be used for testing, beta signup, or internal delivery purposes.

This is the Visa version of the great automatic approach elaborated by Fastlane team, which levarages on the External Testing option provided by the Apple iTunes Connect and TestFlight.

## Quick start

Assuming you already have a [Heroku](https://www.heroku.com/) account follow those steps:

- [![Deploy](https://www.herokucdn.com/deploy/button.png)](https://www.heroku.com/deploy?template=https://github.com/visa-innovation-sf/boarding)
- Enter your iTunes Connect credentials and the bundle identifier of your app. This will all be stored on your own Heroku instance as environment variables
- Click on `View` once the setup is complete and start sharing the URL

`boarding` does all kinds of magic for you, like fetching the app name and app icon.

Heroku is free to use for the standard machine. If you need a Heroku account, ask your back-end team if you already have a company account.

---

![SetupGif](https://raw.githubusercontent.com/fastlane/boarding/master/assets/BoardingSetup.gif)

---

If your account is protected using 2-factor author, follow the [2 step verification guide](https://github.com/fastlane/fastlane/blob/master/spaceship/README.md#2-step-verification).

## Security

To secure your webpage, you only have to set the `ITC_TOKEN` environment variable to any password.

- You can send your users the link and tell them the password
- You can send them the direct link including the token like this: https://url.com/?token=[password]

## Available environment variables

**Required:**

- `ITC_USER` iTunes Connect username
- `ITC_PASSWORD` iTunes Connect password
- `ITC_APP_ID` The Apple ID or Bundle Identifier of your app

**Optional:**
- `ITC_TOKEN` Set a password to protect your website from random people signing up
- `ITC_CLOSED_TEXT` Set this text to temporary disable enrollment of new beta testers
- `RESTRICTED_DOMAIN` Set this domain (in the format `domain.com`) to restrict users with emails in another domain from signing up. This list supports multiple domains by setting it to a comma delimited list (`domain1.com,domain2.com`)
- `FASTLANE_ITC_TEAM_ID` If you're in multiple teams, enter the id of your iTC team here. Make sure it matches on of the IDs of the iTunes Connect user's teams.
- `FASTLANE_ITC_TEAM_NAME` If you're in multiple teams, enter the name of your iTC team here. Make sure it matches.
