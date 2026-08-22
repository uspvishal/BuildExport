# USP- Apples and Bananas — OTA Testing

This is the website-side package for your Ad Hoc iOS + Android testing portal.

## Put these files on your HTTPS website

```text
/
├── index.html
├── ios/
│   └── manifest.plist
└── android/
    └── ApplesBananas.apk
```

## iOS

Your actual `ApplesBananas.ipa` is NOT recreated here. Upload the IPA from your Xcode Ad Hoc export to an HTTPS binary host, such as a GitHub Release.

Then edit `ios/manifest.plist`:

- `IPA_URL_HERE` = direct HTTPS URL to the IPA
- `BUNDLE_ID_HERE` = your actual iOS bundle identifier

Then edit `index.html`:

- `BUILD_NUMBER_IOS`
- `BUILD_NUMBER_ANDROID`
- `IOS_MANIFEST_URL`

Example:

`IOS_MANIFEST_URL` should point to:

`https://YOUR-USERNAME.github.io/YOUR-REPO/ios/manifest.plist`

The Apple button uses the iOS `itms-services` installation mechanism.

## Important

Do NOT rename your actual IPA to `.plist`, and do NOT replace the IPA with a text placeholder.

Your Xcode export already contains the real IPA. The website only needs the manifest to point to that IPA.

`DistributionSummary.plist`, `ExportOptions.plist`, and `Packaging.log` are Xcode export records and are NOT required for OTA installation.
