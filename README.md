<div align="center"><a name="readme-top"></a>

# Google Summer of Code 2025 – Contributions to Mifos Initiative
This repository documents my work during Google Summer of Code 2025 with the [Mifos Initiative](https://github.com/openMF), as well as my contributions before the official coding period.

My GSoC project focused on **Making the Mobile Wallet Deployment-Ready for G2P and Merchant Use Cases**, but my work extended across multiple repositories to enhance functionality, fix bugs, improve CI/CD, and contribute to the Kotlin Multiplatform ecosystem within Mifos.

</div>

## Table of Contents

- [Mobile Wallet](#mobile-wallet)
- [Mifos Mobile (Android end-user app)](#mifos-mobile)
- [KMP Project Template](#kmp-project-template)
- [Android Client (Field Officer app)](#android-client)
- [Mifos Passcode CMP (KMP library)](#mifos-passcode-cmp)
- [Fineract Client KMP SDK](#fineract-client-kmp-sdk)

## Mobile Wallet

**Repo:** [`openMF/mobile-wallet`](https://github.com/openMF/mobile-wallet)  
**About:** A Kotlin Multiplatform (KMP) reference implementation of a digital wallet built on Apache Fineract. It supports Android, iOS, desktop, and web platforms using Compose Multiplatform, Ktor/Ktorfit, and Koin to deliver a clean architecture-based wallet with payment capabilities. Developed for both client and merchant use cases, this wallet is optimized for financial inclusion scenarios and aligned with open digital finance frameworks.

| No. | PR | Description |
| --- | --- | --- |
| 1 | [#1904](https://github.com/openMF/mobile-wallet/pull/1904) | Speed up CI by optimizing the slow `cmp_shared` build step. |
| 2 | [#1901](https://github.com/openMF/mobile-wallet/pull/1901) | Align Fastlane `Fastfile` and configs with the KMP project structure for smoother distribution. |
| 3 | [#1900](https://github.com/openMF/mobile-wallet/pull/1900) | Fix multiplatform targets (iOS, Desktop, JS) and update dependency versions. |
| 4 | [#1898](https://github.com/openMF/mobile-wallet/pull/1898) | Consolidate network layers (move `core-base/network` into `core/network`). |
| 5 | [#1897](https://github.com/openMF/mobile-wallet/pull/1897) | Replace `MaterialTheme` with `KptMaterialTheme` in feature layer (shared design system). |
| 6 | [#1896](https://github.com/openMF/mobile-wallet/pull/1896) | Replace `MaterialTheme` with `KptMaterialTheme` in core layer. |
| 7 | [#1895](https://github.com/openMF/mobile-wallet/pull/1895) | Sync missing root files/folders from the KMP project template. |
| 8 | [#1894](https://github.com/openMF/mobile-wallet/pull/1894) | Complete build-logic setup; add missing dependencies to the version catalog. |
| 9 | [#1893](https://github.com/openMF/mobile-wallet/pull/1893) | Rename modules from `mifospay-*` to `cmp-*` for consistency. |
| 10 | [#1884](https://github.com/openMF/mobile-wallet/pull/1884) | Implement iOS file sharing and improve Android share logic. |
| 11 | [#1878](https://github.com/openMF/mobile-wallet/pull/1878) | Fix iOS navigation & crashes; add `TransferDate` serializer; improve Beneficiary & Home screens. |
| 12 | [#1877](https://github.com/openMF/mobile-wallet/pull/1877) | Add Postman collection to validate self-service APIs for the wallet. |
| 13 | [#1876](https://github.com/openMF/mobile-wallet/pull/1876) | Fix crash on app open without internet after passcode entry. |
| 14 | [#1875](https://github.com/openMF/mobile-wallet/pull/1875) | Fix `TransferDetail` deserialization by changing `transferDate` type to `String`. |
| 15 | [#1874](https://github.com/openMF/mobile-wallet/pull/1874) | Improve Make Transfer account selection (BottomSheetScaffold refactor). |
| 16 | [#1872](https://github.com/openMF/mobile-wallet/pull/1872) | **Auth:** Implement full Sign-In & Sign-Up flows with validation. |
| 17 | [#1867](https://github.com/openMF/mobile-wallet/pull/1867) | Update testers group name for app distribution. |

<div align="right">
  
[![Back To Top](https://img.shields.io/badge/Back%20To%20Top-Blue?style=flat)](#readme-top)

</div>

## Mifos Mobile

**Repo:** [`openMF/Mifos-mobile`](https://github.com/openMF/Mifos-mobile)  
**About:** The official native Android application for end-user clients built on the MifosX/Fineract self-service platform. Written in Kotlin, it allows customers to view and manage their savings, loans, and transactions securely. The app provides a pared-down user experience tailored to mobile clients with integration into core banking services.

| No. | PR | Description |
| --- | --- | --- |
| 1 | [#2844](https://github.com/openMF/Mifos-mobile/pull/2844) | Update testers group name for app distribution (CI). |
| 2 | [#2823](https://github.com/openMF/Mifos-mobile/pull/2823) | Configure iOS project to connect `cmp-shared` (KMP enablement). |
| 3 | [#2800](https://github.com/openMF/Mifos-mobile/pull/2800) | Fix navigation flow after successful transaction. |
| 4 | [#2795](https://github.com/openMF/Mifos-mobile/pull/2795) | Improve dynamic account selection; add decimal support in transactions. |
| 5 | [#2782](https://github.com/openMF/Mifos-mobile/pull/2782) | Remove `feature/account` module from CMP (cleanup). |
| 6 | [#2781](https://github.com/openMF/Mifos-mobile/pull/2781) | Add missing imports; remove unnecessary properties in composables. |
| 7 | [#2779](https://github.com/openMF/Mifos-mobile/pull/2779) | **Accounts:** Migrate `feature:accounts` to CMP. |
| 8 | [#2778](https://github.com/openMF/Mifos-mobile/pull/2778) | **Share Account:** Complete CMP migration. |
| 9 | [#2776](https://github.com/openMF/Mifos-mobile/pull/2776) | **Share Account:** Start migration to CMP. |
| 10 | [#2775](https://github.com/openMF/Mifos-mobile/pull/2775) | **Loan Account:** Migrate module to CMP. |
| 11 | [#2774](https://github.com/openMF/Mifos-mobile/pull/2774) | **Savings Account:** Migrate module to CMP. |
| 12 | [#2773](https://github.com/openMF/Mifos-mobile/pull/2773) | Set up initial directory structure for `feature:account`. |
| 13 | [#2765](https://github.com/openMF/Mifos-mobile/pull/2765) | Configure & fix Detekt for KMP; enable Firebase upload for testing. |
| 14 | [#2762](https://github.com/openMF/Mifos-mobile/pull/2762) | Update README and add Zoom link. |
| 15 | [#2761](https://github.com/openMF/Mifos-mobile/pull/2761) | **About:** Migrate module to CMP. |
| 16 | [#2759](https://github.com/openMF/Mifos-mobile/pull/2759) | Fix incorrect `DataState` import in datastore. |
| 17 | [#2752](https://github.com/openMF/Mifos-mobile/pull/2752) | **Database:** Migrate to KMP. |
| 18 | [#2748](https://github.com/openMF/Mifos-mobile/pull/2748) | Prevent crash when opening Mifos license; tweak icon colors. |
| 19 | [#2732](https://github.com/openMF/Mifos-mobile/pull/2732) | **Model:** Migrate to KMP. |
| 20 | [#2724](https://github.com/openMF/Mifos-mobile/pull/2724) | Fix visibility on Savings Account Withdraw screen. |
| 21 | [#2721](https://github.com/openMF/Mifos-mobile/pull/2721) | Docs cleanup: remove outdated Notice section content. |

<div align="right">
  
[![Back To Top](https://img.shields.io/badge/Back%20To%20Top-Blue?style=flat)](#readme-top)

</div>

## KMP Project Template

**Repo:** [`openMF/kmp-project-template`](https://github.com/openMF/kmp-project-template)  
**About:** A boilerplate template designed for Kotlin Multiplatform projects. It provides standard architecture, build configuration, and Gradle setup to boot‑strap new KMP-driven SDKs or client apps. It streamlines cross-platform development and enforces best practices for modular, Kotlin-based libraries and applications.

| No. | PR | Description |
| --- | --- | --- |
| 1 | [#85](https://github.com/openMF/kmp-project-template/pull/85) | **iOS:** Switch to CocoaPods integration for `cmp-shared`. |
| 2 | [#78](https://github.com/openMF/kmp-project-template/pull/78) | Refactor Fastlane and CI workflows for more robust iOS distribution. |
| 3 | [#77](https://github.com/openMF/kmp-project-template/pull/77) | Add TODO app use case to Home screen (sample). |
| 4 | [#72](https://github.com/openMF/kmp-project-template/pull/72) | **Adaptive Layouts (Design System):** Added Material 3 adaptive scaffolds for phones/tablets — `AdaptiveNavigableListDetailPaneScaffold`, `AdaptiveListDetailPaneScaffold`, `AdaptiveNavigableSupportingPaneScaffold`, and `AdaptiveNavigationSuiteScaffold`. Encapsulates list–detail and supporting-pane patterns, window-size awareness, and ready-to-use examples. |
| 5 | [#71](https://github.com/openMF/kmp-project-template/pull/71) | Update testers group name for distribution (CI). |
| 6 | [#49](https://github.com/openMF/kmp-project-template/pull/49) | **Theme Selection & Dynamic Colors (Android 12+):** Cross-platform theme picker. On Android choose **Default** or **Android**, toggle **Dynamic Colors** (12+), and switch **Light/Dark**; iOS/Web/Desktop support **Light/Dark** toggle. Introduced reusable `ThemeCard`; used `getPlatform` & `supportsDynamicTheming`. |
| 7 | [#70](https://github.com/openMF/kmp-project-template/pull/70) | Modularize Design System as a CMP UI library; add dynamic theming. |
| 8 | [#62](https://github.com/openMF/kmp-project-template/pull/62) | **Ktorfit Networking Module:** Turn-key `HttpClient` config (`setupDefaultHttpClient`) with sensible defaults (timeouts, logging, auth, JSON) and overrides. Added `ResultSuspendConverterFactory` & `ResultFlowConverterFactory` for `Result<Success, RemoteError>` wrapping on suspend/Flow APIs—less boilerplate, unified error handling. |
| 9 | [#61](https://github.com/openMF/kmp-project-template/pull/61) | Add missing App Store Connect metadata & privacy details. |
| 10 | [#60](https://github.com/openMF/kmp-project-template/pull/60) | Create **release** lane for App Store; add metadata support. |
| 11 | [#59](https://github.com/openMF/kmp-project-template/pull/59) | **iOS CI/CD Overhaul:** Migrated Fastlane Match to **SSH** (more reliable), reverted to **automatic signing**, and updated docs. Multi-Platform Build & Publish workflow can ship to **Firebase**, **TestFlight**, or both; integrated changes across shared actions/workflows. |
| 12 | [#57](https://github.com/openMF/kmp-project-template/pull/57) | Revert accidental `google-services.json` commit. |
| 13 | [#56](https://github.com/openMF/kmp-project-template/pull/56) | Rename workflow naming & versioning (consistency). |
| 14 | [#55](https://github.com/openMF/kmp-project-template/pull/55) | Fix Firebase App Distribution failures in template. |
| 15 | [#52](https://github.com/openMF/kmp-project-template/pull/52) | Fastlane lane for iOS Firebase releases. |
| 16 | [#51](https://github.com/openMF/kmp-project-template/pull/51) | Update Fastlane version. |
| 17 | [#48](https://github.com/openMF/kmp-project-template/pull/48) | Configure iOS project to connect `cmp-shared`. |
| 18 | [#47](https://github.com/openMF/kmp-project-template/pull/47) | Add `core-base/` to the sync workflow. |
| 19 | [#46](https://github.com/openMF/kmp-project-template/pull/46) | Add `core-base/datastore` module. |
| 20 | [#45](https://github.com/openMF/kmp-project-template/pull/45) | Add `core/datastore` module. |
| 21 | [#43](https://github.com/openMF/kmp-project-template/pull/43) | **Core-Base Database Module:** Moved shared Room pieces to `core-base/database`; `DatabaseFactory` now returns `RoomDatabase.Builder` for per-app customization. Kept app-specific entities/DAOs in `core/database`; added expect/actual structure and Koin wiring. |
| 22 | [#42](https://github.com/openMF/kmp-project-template/pull/42) | Add `core/database` module. |

<div align="right">
  
[![Back To Top](https://img.shields.io/badge/Back%20To%20Top-Blue?style=flat)](#readme-top)

</div>

## Android Client

**Repo:** [`openMF/android-client`](https://github.com/openMF/android-client)  
**About:** A field‑officer facing Android app that runs on top of the Mifos/Fineract backend. Originally built as a Kotlin multi-module application, it enables staff to manage portfolios, approve loans, and handle client data in remote locations. Recent efforts focus on migrating its network layer to the fineract-client-kmp-sdk and adopting Multiplatform code structure.

| No. | PR | Description |
| --- | --- | --- |
| 1 | [#2378](https://github.com/openMF/android-client/pull/2378) | Update testers group name used for app distribution (CI). |
| 2 | [#2376](https://github.com/openMF/android-client/pull/2376) | Same CI update across workflows to keep distribution groups consistent. |

<div align="right">
  
[![Back To Top](https://img.shields.io/badge/Back%20To%20Top-Blue?style=flat)](#readme-top)

</div>

## Mifos Passcode CMP

**Repo:** [`openMF/mifos-passcode-cmp`](https://github.com/openMF/mifos-passcode-cmp)  
**About:** A Kotlin Multiplatform library providing secure passcode functionality for Mifos applications. It supports Android, iOS, and desktop apps and enforces passcode lock on resume or inactivity. Released under Apache 2.0, it improves app security and UX consistency across platforms.

| No. | PR | Description |
| --- | --- | --- |
| 1 | [#42](https://github.com/openMF/mifos-passcode-cmp/pull/42) | Implement biometric authentication support for iOS. |
| 2 | [#41](https://github.com/openMF/mifos-passcode-cmp/pull/41) | Add iOS build support for the CMP module. |

<div align="right">
  
[![Back To Top](https://img.shields.io/badge/Back%20To%20Top-Blue?style=flat)](#readme-top)

</div>

