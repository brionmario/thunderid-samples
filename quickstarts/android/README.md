![ThunderID Android Quickstart](https://raw.githubusercontent.com/thunder-id/samples/main/.github/assets/banners/quickstarts-android.png)

# ThunderID Android Quickstart

ThunderID Android Quickstart demonstrates the full authentication lifecycle using the [ThunderID Android SDK](https://github.com/thunder-id/android-sdks) on Android.

**Flow demonstrated:**
1. App opens → unauthenticated state (sign-in screen)
2. User initiates sign-in / sign-up → SDK starts app-native Flow Execution
3. User completes the flow
4. Sign-in → authenticated state with profile information, token debugging, and sign-out button.
   Sign-up creates the account but does not start a session, so it returns to the landing screen
   and the new credentials have to be used to sign in.
5. User taps Sign Out → session terminated, returns to sign-in screen

The sample depends on the published SDK from [JitPack](https://jitpack.io/#thunder-id/android-sdks)
(`com.github.thunder-id:android-sdks`), declared in `build.gradle.kts`.

## Prerequisites

- JDK 17 or later
- Android Studio, or the Android SDK with `ANDROID_HOME` set
- An Android emulator or device (API 26+)
- A running ThunderID instance

## Get the Sample

```bash
git clone https://github.com/thunder-id/samples.git
cd samples/quickstarts/android
cp config.properties.example config.properties
```

## Configure

This sample uses app-native authentication (Flow Execution API), so only the base URL and application ID are required, no OAuth2 client ID or redirect URIs.

| Variable | Description |
|----------|-------------|
| `THUNDERID_BASE_URL` | Base URL of your ThunderID server (HTTPS) |
| `THUNDERID_APPLICATION_ID` | Application UUID from the ThunderID Console |
| `THUNDERID_ATTESTATION_ENABLED` | `true` to send a Google Play Integrity token with each flow (optional) |
| `THUNDERID_CLOUD_PROJECT_NUMBER` | Google Cloud project number used for Play Integrity (optional) |

`config.properties` is gitignored. Never commit real credentials. Each value can also be supplied as an environment variable of the same name.

If your ThunderID server runs on `localhost`, don't use `localhost` in `THUNDERID_BASE_URL` directly:

- **Emulator**: use `https://10.0.2.2:8090`, the emulator's alias for your host machine's loopback.
- **Physical device**: run `adb reverse tcp:8090 tcp:8090` and keep using `https://localhost:8090`, or point the URL at your host machine's LAN IP.

## Run

Open this directory in Android Studio, sync Gradle, and run it on an emulator or device. From the command line:

```bash
./gradlew installDebug
```

## Attestation and Passkeys

See [Try the Android Sample App](https://thunderid.dev/docs/v1.0.x/sdks/android/guides/try-the-sample-app) in the Android SDK docs for Google Play Integrity attestation and passkey (Digital Asset Links, `assetlinks.json.example`) setup.

## End-to-End Tests

`thunderid-config/thunderid-config.yaml` declares the application the Android SDK's [E2E suite](https://github.com/thunder-id/android-sdks/tree/main/tests/e2e) provisions on a test server. The suite fetches this sample and builds it against the SDK checkout under test.
