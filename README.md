# TravelSafelyBoneshellSpmNTTA

Swift Package for the TravelSafely SDK (NTTA).

## Requirements

- iOS 16.0 or later
- Xcode 27 or later

## Installation

1. In Xcode, choose **File → Add Package Dependencies…**
2. Enter `https://github.com/Applied-Information/TravelSafelyBoneshellSpmNTTA` and pick the latest version.
3. Add the **TravelSafelyBoneshell** library to your app target.

Swift Package Manager also fetches the SDK's dependencies: `realm-swift` (20.0.6 or later 20.x) and `CocoaAsyncSocket` 7.6.5.

## Usage

```swift
import TravelSafelyBoneshell
```

If your app uses Realm itself, `import RealmSwift` works through this package. Don't add `realm-swift` to your app target separately. Doing so can make the app crash at launch on a device.

## Releasing a new version (Applied Information)

1. In the SDK project, run `./scripts/build_xcframework.sh <version>` (for example `1.0.1`). It builds `SPM-Distribution/TravelSafelyBoneshell.xcframework.zip` and writes the version and checksum into `SPM-Distribution/Package.swift`.
2. Copy `Package.swift`, `Sources/`, `README.md` and `.gitignore` from `SPM-Distribution/` into this repo. Don't copy the `.xcframework` or the zip.
3. Commit, then tag the commit with the same version and push the tag.
4. Create a GitHub release for that tag and attach `TravelSafelyBoneshell.xcframework.zip`.
