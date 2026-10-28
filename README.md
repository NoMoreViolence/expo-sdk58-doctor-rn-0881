# expo-doctor expects react-native 0.88.0 on SDK 58.0.21 (template ships 0.88.1)

Unmodified app from `npx create-expo-app@latest -t default@sdk-58` (expo ~58.0.21, react-native 0.88.1, npm).

```sh
npm install
npx expo-doctor          # ✖ Check that packages match versions required by installed Expo SDK
                         #   react-native  expected 0.88.0  found 0.88.1
npx expo install --check # react-native@0.88.1 - expected version: 0.88.0
```

`expo@58.0.21`'s `bundledNativeModules.json`, this template, and `GET https://api.expo.dev/v2/sdks/58.0.0/native-modules`
all say react-native 0.88.1, but `GET https://api.expo.dev/v2/versions/latest` →
`sdkVersions["58.0.0"].facebookReactNativeVersion` is still `0.88.0`, and `@expo/cli`
(`getVersionedPackages.js`) uses that field for `react-native`.
