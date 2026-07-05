# 📱 Mobile Development Capabilities

> Load this module for mobile app development tasks.
> Load trigger: Code / Architect mode with mobile-related request.

## Cross-Platform
- **React Native**: Expo (managed + bare), Reanimated, Hermes engine, Native Modules
- **Flutter**: Widget tree, Riverpod/BLoC, Platform Channels, CustomPainter
- **MAUI / .NET MAUI**: MVVM, Shell navigation, platform-specific handlers

## Native Android
- **Kotlin**: Jetpack Compose, Coroutines + Flow, Room, Hilt/Dagger
- **Java**: XML layouts, RecyclerView, AsyncTask (legacy), Retrofit
- **Architecture**: MVVM, Clean Architecture, MVI, Single Activity pattern
- **Libraries**: Retrofit, OkHttp, Glide, Coil, ExoPlayer, Firebase SDK
- **DI**: Hilt, Koin, Dagger

## Native iOS (Swift)
- **SwiftUI**: @State, @Binding, @ObservedObject, @EnvironmentObject
- **UIKit**: Auto Layout, Storyboards, UITableView, UICollectionView
- **Combine** / async-await for reactive programming
- **SwiftData** / Core Data for persistence
- **SPM** (Swift Package Manager) for dependencies

## Common Concerns
- **State Management**: Redux (React), BLoC/Riverpod (Flutter), ViewModel (native)
- **Offline First**: SQLite, Realm, WatermelonDB, Firestore offline persistence
- **Push Notifications**: FCM, APNs, OneSignal, custom notification channels
- **Deep Linking**: Branch, Firebase Dynamic Links, universal links + app links
- **Biometrics**: Fingerprint, Face ID, Android Biometric API
- **Payments**: Stripe, RevenueCat, Apple Pay, Google Pay

## App Store & Distribution
- **App Store Connect**: TestFlight, app review guidelines, in-app purchases
- **Google Play Console**: closed/open testing, staged rollouts, pre-registration
- **Code Push**: CodePush (RN), Shorebird (Flutter), app center
- **App Bundling**: Android App Bundle, iOS .ipa, code signing, provisioning profiles

## Performance
- **Memory**: leak detection (LeakCanary, Instruments), image caching, lazy loading
- **Startup**: cold start optimization, deferred deep linking, splash screens
- **Network**: offline caching, prefetching, pagination, image compression
- **Size**: APK/IPA size optimization, ProGuard/R8, asset compression, App Bundles

## Testing
- **Unit**: JUnit (Android), XCTest (iOS), Jest (RN), flutter_test
- **UI**: Espresso, XCUITest, Detox (RN), integration_test (Flutter)
- **E2E**: Detox, Appium, Maestro, BrowserStack
- **Snapshot**: SnapshotTesting (iOS), Paparazzi (Android), Storybook (RN)

## Security
- Certificate pinning (OkHttp, TrustKit, Alamofire)
- Obfuscation: ProGuard, R8, iOS symbol stripping
- Keychain / EncryptedSharedPreferences for sensitive data
- Root/jailbreak detection (SafetyNet, DeviceCheck)
- OWASP Mobile Top 10 awareness
