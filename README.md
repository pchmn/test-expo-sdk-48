# Expo SDK 48 - bug with `react-native-maps`

When using expo sdk 48 with `react-native-maps` there is a bug at iOS prebuild.
If you set a Google Maps Api Key in `app.json` (`ios.config.googleMapsApiKey`) when prebuilding there is this error :

```
✖ Config sync failed
Error: [ios.appDelegate]: withIosAppDelegateBaseMod: Cannot add Google Maps to the project's AppDelegate because it's malformed. Please report this with a copy of your project AppDelegate.
Error: [ios.appDelegate]: withIosAppDelegateBaseMod: Cannot add Google Maps to the project's AppDelegate because it's malformed. Please report this with a copy of your project AppDelegate.
    at /Users/paul/Dev/perso/test-expo-sdk-48/node_modules/.pnpm/@expo+config-plugins@6.0.0/node_modules/@expo/config-plugins/build/ios/Maps.js:218:19
    at action (/Users/paul/Dev/perso/test-expo-sdk-48/node_modules/.pnpm/@expo+config-plugins@6.0.0/node_modules/@expo/config-plugins/build/plugins/withMod.js:201:29)
    at interceptingMod (/Users/paul/Dev/perso/test-expo-sdk-48/node_modules/.pnpm/@expo+config-plugins@6.0.0/node_modules/@expo/config-plugins/build/plugins/withMod.js:105:27)
    at action (/Users/paul/Dev/perso/test-expo-sdk-48/node_modules/.pnpm/@expo+config-plugins@6.0.0/node_modules/@expo/config-plugins/build/plugins/createBaseMod.js:61:27)
    at async interceptingMod (/Users/paul/Dev/perso/test-expo-sdk-48/node_modules/.pnpm/@expo+config-plugins@6.0.0/node_modules/@expo/config-plugins/build/plugins/withMod.js:105:21)
    at async evalModsAsync (/Users/paul/Dev/perso/test-expo-sdk-48/node_modules/.pnpm/@expo+config-plugins@6.0.0/node_modules/@expo/config-plugins/build/plugins/mod-compiler.js:204:25)
    at async Object.compileModsAsync (/Users/paul/Dev/perso/test-expo-sdk-48/node_modules/.pnpm/@expo+config-plugins@6.0.0/node_modules/@expo/config-plugins/build/plugins/mod-compiler.js:124:10)
    at async configureProjectAsync (/Users/paul/Dev/perso/test-expo-sdk-48/node_modules/.pnpm/@expo+cli@0.6.1_6weo4dzsrefthwodkc5gdxxcii/node_modules/@expo/cli/build/src/prebuild/configureProjectAsync.js:54:15)
    at async prebuildAsync (/Users/paul/Dev/perso/test-expo-sdk-48/node_modules/.pnpm/@expo+cli@0.6.1_6weo4dzsrefthwodkc5gdxxcii/node_modules/@expo/cli/build/src/prebuild/prebuildAsync.js:83:9)
```

If you remove `ios.config.googleMapsApiKey`, prebuild is working fine.

## Steps to reproduce

```
pnpm install

npx expo prebuild
```
