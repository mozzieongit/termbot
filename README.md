TermBot is an SSH client that supports authentication with YubiKeys, Nitrokeys and other OpenPGP cards over NFC and USB.

For this it uses the COTECH Hardware Security SDK available at https://hwsecurity.dev

TermBot is based on ConnectBot.

[<img src="https://f-droid.org/badge/get-it-on.png"
      alt="Get it on F-Droid"
      height="80">](https://f-droid.org/packages/org.sufficientlysecure.termbot/)
[<img src="https://play.google.com/intl/en_us/badges/images/generic/en-play-badge.png"
      alt="Get it on Google Play"
      height="80">](https://play.google.com/store/apps/details?id=org.sufficientlysecure.termbot)

## Supported Hardware

### NFC
- Cotech Card
- YubiKey NEO
- YubiKey 5 NFC

### USB
- Nitrokey Start, Pro, Storage (with adapter)
- YubiKey 4, 4 Nano, 5, 5 Nano (with adapter)
- YubiKey 4C, 4C Nano, 5C, 5C Nano (directly over USB-C)
- Gnuk (with adapter)
- Secalot (with adapter)

Full list of supported hardware can be found here: https://hwsecurity.dev/docs/supported-hardware/

## Build Release
```
git tag 1.9.5-termbot1
./gradlew --quiet androidGitVersion
./gradlew assembleGoogleRelease
=======
The easiest way to get ConnectBot is to [install from Google Play Store][1].
If you have installed from a downloaded APK, Google Play Store can upgrade
your installed version to the latest version. However, once it has upgraded
*you can't install a version from the releases on GitHub anymore.*


### Download a release

ConnectBot can be downloaded from [releases](
https://github.com/connectbot/connectbot/releases) on GitHub. There are
two versions:

-  "`google`" &mdash; for a version that uses Google Play Services
to handle upgrading the cryptography provider
-  "`oss`" &mdash; includes the cryptography provider in the APK which
   increases its size by a few megabytes.
## Compiling

### Android Studio

ConnectBot is most easily developed in [Android Studio](
https://developer.android.com/studio/). You can import this project
directly from its project creation screen by importing from the GitHub URL.

### Command line

To compile ConnectBot using `gradlew`, you must first specify where your
Android SDK is via the `ANDROID_SDK_HOME` environment variable. Then
you can invoke the Gradle wrapper to build:

```sh
./gradlew build
```

### Continuous Integration

ConnectBot uses [GitHub Actions](https://github.com/connectbot/connectbot/actions)
for continuous integration. The workflow is defined in
`.github/workflows/ci.yml`.

#### Running Workflows Locally with act

In general, simply running `./gradlew build` should cover all the
checks run in the GitHub Actions continuous integration workflow, but you can
run GitHub Actions workflows locally using [`nektos/act`](https://github.com/nektos/act).
This requires Docker to be installed and running.

To run the main CI workflow (`ci.yml`):

```sh
act -W .github/workflows/ci.yml
>>>>>>> connectbot/main
```
afterwards, sign with keystore
