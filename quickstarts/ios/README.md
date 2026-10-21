![ThunderID iOS Quickstart](https://raw.githubusercontent.com/thunder-id/samples/main/.github/assets/banners/quickstarts-ios.png)

# ThunderID iOS Quickstart

ThunderID iOS Quickstart demonstrates the full authentication lifecycle using the `ThunderID iOS` SDK.

**Flow demonstrated:**
1. App opens → unauthenticated state (sign-in screen)
2. User initiates sign-in / sign-up → SDK starts app-native Flow Execution
3. User completes the flow
4. Sign-in → authenticated state with profile information, token debugging, and sign-out button.
   Sign-up creates the account but does not start a session, so it returns to the landing screen
   and the new credentials have to be used to sign in.
5. User taps Sign Out → session terminated, returns to sign-in screen

The app depends on the published [ThunderID iOS SDK](https://github.com/thunder-id/ios-sdks)
release through Swift Package Manager, so it builds on its own without a checkout of the SDK.

## Get the Sample

```bash
git clone https://github.com/thunder-id/samples.git
cd samples/quickstarts/ios
cp Sources/Config.plist.example Sources/Config.plist
```

Set `THUNDERID_BASE_URL` and `THUNDERID_APPLICATION_ID` in `Sources/Config.plist`, then open
`Quickstart.xcodeproj` in Xcode and run the `Quickstart` scheme on a simulator or device.
`Sources/Config.plist` is listed in `.gitignore`, so your local values are not committed.

## Setup & Run

See [Try the iOS Sample App](https://thunderid.dev/docs/v1.0.x/sdks/ios/guides/try-the-sample-app)
in the iOS SDK docs for prerequisites, configuration, attestation, passkeys, and run instructions.

## Where Things Are

| Path | What it is |
|------|------------|
| `Sources/` | The SwiftUI app and `Config.plist.example` |
| `Quickstart.xcodeproj` | Xcode project, with the SDK as a remote Swift package |
| `Package.swift` | The same app as a Swift package |
| `thunderid-config/thunderid-config.yaml` | The application the [iOS SDK E2E suite](https://github.com/thunder-id/ios-sdks/tree/main/Tests/e2e) imports into ThunderID before it drives this sample |
