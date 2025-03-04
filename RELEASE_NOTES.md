# Release Notes

This section contains past updates we've sent to customers via Discord.

## 0.4.0 (June 2, 2023)

We've just released Shorebird CLI v0.4.0 🎉

✨ The most notable changes are:

- 🧩 Support for Android Archive Add-To-App workflows
  - `shorebird release aar` and `shorebird patch aar`
- 🐛 Fix uploads for large apps
- 🚨 Breaking Change: `shorebird patch` was renamed to `shorebird patch android` as continued preparation to support iOS

📚 Release notes can be found at https://github.com/shorebirdtech/shorebird/releases/tag/v0.4.0

As always, you can upgrade using `shorebird upgrade`

Please let us know if we can help!

## 0.3.1 (May 30, 2023)

We've just released Shorebird CLI v0.3.1 🎉

✨ The most notable changes are:

- 📦 Allow resubmitting a release after a partial failure
- 📝 Additional verbose logging `shorebird --verbose`
- ⚠️ Improved error output if artifact uploads fail

📚 Release notes can be found at https://github.com/shorebirdtech/shorebird/releases/tag/v0.3.1

As always, you can upgrade using `shorebird upgrade`

Please let us know if we can help!

## 0.3.0 (May 25, 2023)

We've just released Shorebird CLI v0.3.0 🎉

✨ The most notable changes are:

- 🐦 Support for Flutter 3.10.2 and Dart 3.0.2
- 🚨 Breaking Change: `shorebird release` was removed in favor of `shorebird release android` as part of the preparation to support iOS
- ⚠️ `shorebird patch` alerts users of non-patchable changes
- 🩹 Fixed a bug which caused crashes on Android API <28

📚 Release notes can be found at https://github.com/shorebirdtech/shorebird/releases/tag/v0.3.0

As always, you can upgrade using shorebird upgrade

Please let us know if we can help!

## 0.2.2 (May 22, 2023)

We've just released Shorebird CLI v0.2.2 🎉

✨ The most notable changes are:

- 🐦 Support for Flutter 3.10.1 and Dart 3.0.1

📚 Release notes can be found at https://github.com/shorebirdtech/shorebird/releases/tag/v0.2.2

As always, you can upgrade using shorebird upgrade

Please let us know if we can help!

## 0.2.1 (May 17, 2023)

We've just released Shorebird CLI v0.2.1 🎉

✨ The most notable changes are:

🤝 Added support for managing collaborators (see shorebird collaborators --help)
🍧 Fixed flavors case sensitivity
🧑‍🔧 Fixed rare crash when shorebird was misconfigured

📚 Release notes can be found at https://github.com/shorebirdtech/shorebird/releases/tag/v0.2.1

As always, you can upgrade using shorebird upgrade

Please let us know if we can help!

## 0.2.0 (May 12, 2023)

We've just released v0.2.0 of shorebird 🎉 :shorebird:

✨ Highlights:
- 🐦 Support for Flutter 3.10.0 and Dart 3.0.0
- 🤖 Fixed Android Studio paths on Linux
- 📦 `shorebird release` no longer accepts `--release-version`
  - release versions are derived from build artifacts
- ✅ `shorebird release --force` will skip confirmation prompts (thanks @rkishan516)!

Note: Moving to Dart 3 is breaking.  Dart 3 is not able to build apps that run
in Dart 2.x (e.g. apps you released last week) and vice versa.  Once you upgrade
to Shorebird 0.2.0, you will not be able to push patches to releases made with
Shorebird 0.1.0 or earlier.  You will need to make a new release with Shorebird
0.2.0 to be able to push patches from Shorebird 0.2.0.

We can add support for multiple Flutter versions in the future:
https://github.com/shorebirdtech/shorebird/issues/472
Let us know if that's important to you.

📚 Changelog
https://github.com/shorebirdtech/shorebird/releases/tag/v0.2.0


## 0.1.0 (May 6, 2023)

We've just released v0.1.0 of shorebird 🎉 :shorebird: 

✨ Highlights include:

- 🍧 Support for Flavors 
- 🗑️ Support for deleting releases and their artifacts (shorebird releases delete)
- 📝 Support for listing releases (shorebird releases list)
- 🧑‍⚕️ Shorebird Doctor can now also apply fixes for some issues (shorebird doctor --fix)

📚 Changelog
https://github.com/shorebirdtech/shorebird/releases/tag/v0.1.0

## 0.0.10

We've just released Shorebird CLI v0.0.10.

We discovered a bug in 0.0.9 that caused releases made from 0.0.9 with
a version name including build number (e.g. `1.0.0+1`) to fail to update.

`shorebird release` would include the build number in the version name,
but the updater client would not include the build number in its request
to the server.

The fix was to make the updater client always also include the build number
which will make "1.0.0+1" and "1.0.0+2" correctly different versions.

What else is new:
* `shorebird run` now supports `-d` to specify a device ID.
* Fixed `shorebird run` on linux x64 when `web` was enabled for the project.
* Fixed Windows install script to work even when IE was not installed.
* Fixed Windows install to add the correct path to the PATH variable.

As always, you can upgrade with `shorebird upgrade`.

Please let us know if we can help!

Eric

## 0.0.9 - Open Beta

Welcome to 0.0.9, big changes ahead!

If you're already using Shorebird, you can upgrade to the latest version
with `shorebird upgrade`.

It no longer requires an invite to use Shorebird.  You can create and account
and subscribe to the Open Beta directly from the command line.  Instructions
are available at our new docs site: https://docs.shorebird.dev/

What's new:
 * New site: https://shorebird.dev/ and docs site: https://docs.shorebird.dev/
 * Windows support!  https://docs.shorebird.dev now has instructions on how
   to install Shorebird on Windows.
 * Updates no longer block launch.  When available, updates are still applied
   during app launch, but now on a background thread.  This means that your
   development flow to test your patches will involve launching your app
   letting it update in the background, and then re-launching to see the patch
   applied.  This change was made to improve the experience for users
   (there is no longer a synchronous network request during app startup) and
   make apps resilient to unreliable networks during launch.

As always, please let us know if you see any issues.

## Announcement for 0.0.8

We've just released Shorebird CLI v0.0.8 🎉

What's new:
* Updated to Flutter 3.7.12.
* Updated Shorebird to use a specific revision of Flutter (rather than
  "latest stable in our fork", making it possible to check out a specific
  version of Shorebird from git and expect it to be able to build binaries
  even months in the future).
* Added (partial) support for Android build numbers.
* Added `shorebird account create` and `shorebird account subscribe` to
  automate our onboarding process for new trusted testers.
* Improved the way we proxy Flutter artifacts (via download.shorebird.dev) to
  greatly improve our speed of releasing new versions of Shorebird.

Let us know if you see any issues!

## Announcement for 0.0.7

We've just released Shorebird CLI v0.0.7 🎉 

What's new:
* Fixed our backend to not error for large app releases.
* `shorebird build` is now split into two subcommands:
  * `shorebird build apk` (new)
  * `shorebird build appbundle` (previously `shorebird build`)

Changelog: https://github.com/shorebirdtech/shorebird/releases/tag/v0.0.7 


## Announcement for 0.0.6

We're happy to announce Shorebird 0.0.6!

Shorebird should be ready for production apps < 10k users.

You should be able to get test latest via `shorebird upgrade`

What's new:
* Fixed updates to apply when app installed with apk splits (as the Play
  Store does by default). This was our last known production blocking issue.
* `shorebird subscription cancel` now is able to cancel your monthly
  Shorebird subscription.  Your Shorebird account will keep working until
  the end of your billing period.  After expiration, your apps will continue
  to function normally, just will no longer pull updates from Shorebird.
* `shorebird cache clean` (Thanks @TypicalEgg!) will now clear Shorebird
  caches.
* Install script now pulls down artifacts as part of install.
* Continued improvements to our account handling in preparation for supporting
  self-sign-up.

Known issues:
* Shorebird is still using Flutter 3.7.10.  We will update to 3.7.11 right
  after this release:
  https://github.com/shorebirdtech/shorebird/issues/305
* Shorebird does not yet support Android versionCode, only versionName.
  https://github.com/shorebirdtech/shorebird/issues/291

Please try shorebird in production and let us know how we can help!

Eric


## Announcement for 0.0.5

We're happy to announce Shorebird 0.0.5!

TL;DR: Shorebird should be ready for use in production for apps < 10k users.

You should be able to get the latest via `shorebird upgrade`.

What's new:
* Updates should now apply consistently (previously sometimes failed).
https://github.com/shorebirdtech/shorebird/issues/235.  This was our
last-known production-blocking issue.
* `shorebird doctor` and other commands now are a bit more robust in
their checks.
* We did a ton of backend work (which shouldn't be visible), mostly
in terms of testing to make sure we're ready for production.  We also
integrated our backend with Stripe (to make subscription management
possible).

Known issues:
* Shorebird is still using Flutter 3.7.10.  We will update to 3.7.11
in the next couple days.  We've done the previous Flutter updates
manually, but we're working on automating updates so that Shorebird
can track Flutter versions as soon as minutes after they are released.
https://github.com/shorebirdtech/shorebird/issues/236

You can see what we're tracking for 0.0.6 here:
https://github.com/orgs/shorebirdtech/projects/6/views/1

We've also wired up Stripe integration on the backend and will have some
subscription management (including ability to cancel) in our next release.

We expect you all will have requests as you try Shorebird in production
please don't hesitate to let us know!  We're standing by to fix/add what
you need to help you be successful.

Please try shorebird in production and let us know how we can help!

Eric



## Announcement for 0.0.4

I'm happy to announce shorebird 0.0.4!

This one's a big one.  Unfortunately it's also breaking.

You will both need to re-install shorebird and re-login to shorebird:

```bash
rm -rf ~/.shorebird
curl --proto '=https' --tlsv1.2 https://raw.githubusercontent.com/shorebirdtech/install/main/install.sh -sSf | sh
```

Then you'll want to `shorebird login` and follow the prompts to authenticate
with a Google account.

We believe we've updated our database to mark all trusted testers as paid
accounts after the auth migration, but if you see any issues, please let us
know, and we'll be happy to fix your account right away.

What's new:
* `shorebird` supports Android 32-bit and 64-bit devices!
* `shorebird` works on Linux and Mac-Intel hosts!
* `shorebird login` uses Google OAuth instead of API keys.
* `shorebird doctor` does some basic validation.
* `shorebird account` shows your login status.
* Updated to Flutter 3.7.10.
* We also automated our builds of the Shorebird engine.
  While that won't affect your usage, it did make this release
  possible and will allow us to keep up to date with Flutter more easily as
  well as removing a source of human error in our processes.

As part of adding support for Android arm32 devices as well as Linux and
Mac-Intel hosts, we've changed how `shorebird` uses Flutter.  Previously it used
the Flutter SDK already installed on your machine.  Now it brings its own copy
of `flutter`.  This is due to the fact that our previous method of replacing the
Flutter engine binaries on Android went in through a (hacky) development-only
path, which only supported only a single architecture at a time (hence us
previously limiting `shorebird` only 64-bit Android devices).

Now we use a fork of Flutter.  The only change in our fork is the engine version
it tries to fetch.  When `shorebird` runs our forked `flutter`, we also tell it
to fetch its engine artifacts from our server (download.shorebird.dev) instead
of Google's (download.flutter.io).  download.shorebird.dev knows how to replace
a few Android artifacts with Shorebird enabled ones and proxy all other requests
to Google's servers.  This is how we now support all platforms Flutter does
since it's using the same host binaries as an unmodified Flutter SDK.

https://github.com/shorebirdtech/shorebird/blob/main/FORKING_FLUTTER.md has more
information on how we forked Flutter if you're curious.

Known issues:
* We have had reports of patches sometimes failing to apply.  We expect to have
  a fix for this early next week.
  https://github.com/shorebirdtech/shorebird/issues/235
* Shorebird itself should work on Windows, but we haven't updated our installer
  script to support it yet.  https://github.com/shorebirdtech/install/issues/10

Please try out the new platforms and new auth flow and let us know what you
think.
