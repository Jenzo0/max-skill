# 📱 Mobile Development Capabilities

> Load trigger: Code/Architect mode with mobile-related request.

## Cross-Platform

| Framework | State | UI |
|---|---|---|
| React Native | Zustand, TanStack Query, Redux | Expo, Reanimated, Native Modules |
| Flutter | Riverpod, BLoC, Provider | Widget tree, CustomPainter, Platform Channels |
| .NET MAUI | MVVM, Community Toolkit | XAML, Shell navigation, handlers |

## Native Android (Kotlin)

- **UI**: Jetpack Compose, Material 3, XML layouts (legacy)
- **Architecture**: MVVM, Clean Architecture, MVI, Single Activity
- **DI**: Hilt, Koin, Dagger
- **Persistence**: Room, DataStore, SQLite
- **Networking**: Retrofit, OkHttp, Ktor, Apollo GraphQL

## Native iOS (Swift)

- **UI**: SwiftUI (@State, @Binding, @ObservedObject, @EnvironmentObject) or UIKit
- **Architecture**: MVVM, Coordinator, VIPER, TCA (The Composable Architecture)
- **Concurrency**: async/await, Combine, Actors
- **Persistence**: SwiftData, Core Data, Realm, GRDB
- **Networking**: URLSession, Alamofire, Apollo iOS

## Common Concerns

| Concern | Approach |
|---|---|
| Offline First | SQLite/Realm local DB + sync engine + conflict resolution |
| Push Notifications | FCM + APNs via OneSignal or custom relay |
| Deep Linking | Universal links (iOS) + App Links (Android) |
| Biometrics | Face ID, Touch ID, Android Biometric API |
| Payments | Stripe, RevenueCat, Apple Pay, Google Pay |
| App Store | TestFlight, staged rollouts, code push (Shorebird/CodePush) |
