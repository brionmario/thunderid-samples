![ThunderID Flutter Quickstart](https://raw.githubusercontent.com/thunder-id/samples/main/.github/assets/banners/quickstarts-flutter.png)

# ThunderID Flutter Quickstart

ThunderID Flutter Quickstart demonstrates the full authentication lifecycle using the [`thunderid_flutter`](https://pub.dev/packages/thunderid_flutter) SDK on iOS and Android.

**Flow demonstrated:**
1. App opens → unauthenticated state (sign-in screen)
2. User initiates sign-in / sign-up → SDK starts app-native Flow Execution
3. User completes the flow
4. Sign-in → authenticated state with profile information, token debugging, and sign-out button.
   Sign-up creates the account but does not start a session, so it returns to the landing screen
   and the new credentials have to be used to sign in.
5. User taps Sign Out → session terminated, returns to sign-in screen

## Get the Sample

```bash
git clone https://github.com/thunder-id/samples.git
cd samples/quickstarts/flutter
```

## Configure

```bash
cp .env.example .env
```

| Variable | Description |
|---|---|
| `THUNDERID_BASE_URL` | Base URL of your ThunderID server (default `https://localhost:8090`). |
| `THUNDERID_APP_ID` | ID of the ThunderID application the sample signs in to. |
| `THUNDERID_ATTESTATION_ENABLED` | Set to `true` to enable platform attestation. |
| `THUNDERID_CLOUD_PROJECT_NUMBER` | Google Cloud project number, used for Play Integrity attestation on Android. |

## Run

```bash
flutter pub get
flutter run
```

See [Try the Flutter Sample App](https://thunderid.dev/docs/v1.0.x/sdks/flutter/guides/try-the-sample-app)
in the Flutter SDK docs for prerequisites, creating the application, attestation, passkeys, and run instructions.

The SDK source lives in [thunder-id/flutter-sdks](https://github.com/thunder-id/flutter-sdks).
