<!-- Top anchor for “Back to Top” links -->
<a name="readme-top"></a>

<div align="center">

  <!-- Hero banner (replace with your actual GIF or image path) -->
  <img src="https://github.com/user-attachments/assets/6b854ebf-1611-4ee9-bad9-493d700d73e8" alt="Google Summer of Code x Mifos Initiative" width="900" height="400" />

  <h1>Google Summer of Code 2025 – Contributions to Mifos Initiative</h1>

  <p>
    This repository documents my GSoC 2025 work with the <a href="https://github.com/openMF">Mifos Initiative</a>, plus contributions before the official coding period.
  </p>

  <!-- Badges -->
  <p>
    <img alt="GSoC 2025" src="https://img.shields.io/badge/GSoC-2025-ffa500?logo=google&logoColor=white">
    <img alt="Kotlin Multiplatform" src="https://img.shields.io/badge/Kotlin-Multiplatform-7F52FF?logo=kotlin&logoColor=white">
    <img alt="Compose Multiplatform" src="https://img.shields.io/badge/Compose-Multiplatform-2E7D32?logo=jetpackcompose&logoColor=white">
    <img alt="CI/CD" src="https://img.shields.io/badge/CI%2FCD-GitHub%20Actions-2088FF?logo=githubactions&logoColor=white">
  </p>

  <p>
    My GSoC project focused on <b>Making the Mobile Wallet Deployment-Ready for G2P and Merchant Use Cases</b>, but my work extended across multiple repositories to enhance functionality, fix bugs, improve CI/CD, and contribute to the Kotlin Multiplatform ecosystem within Mifos.
  </p>

</div>

## Table of Contents

- [Mobile Wallet](#mobile-wallet)
- [Mifos Mobile](#mifos-mobile)
- [KMP Project Template](#kmp-project-template)
- [Android Client (Field Officer app)](#android-client)
- [Mifos Passcode CMP (KMP library)](#mifos-passcode-cmp)
- [CI/CD – GitHub Actions & Reusable Workflows](#cicd--github-actions--reusable-workflows)

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
**About:** A **Kotlin Multiplatform** client for end users, built on the MifosX Self-Service platform. It lets customers securely view and transact on their own accounts and loans. Compared to staff apps, data is a curated subset appropriate for self-service. Shared KMP modules power business logic across Android, iOS, Desktop, and Web, with Kotlin/Compose UIs providing a streamlined, consistent experience.

| No. | PR | Description |
| --- | --- | --- |
| 1 | [#2844](https://github.com/openMF/Mifos-mobile/pull/2844) | Update testers group name for app distribution (CI). |
| 2 | [#2823](https://github.com/openMF/Mifos-mobile/pull/2823) | Configure iOS project to connect `cmp-shared` (KMP enablement). |
| 3 | [#2800](https://github.com/openMF/Mifos-mobile/pull/2800) | **Fix post-transfer navigation:** Users now return to the screen they started from—Home → **Home**, Savings Account → **Savings**, Loan Account → **Loan**—after a successful transfer. Improves consistency and UX. |
| 4 | [#2799](https://github.com/openMF/Mifos-mobile/pull/2799) | **Epic: Modularize Account feature.** Created module scaffolding and Gradle configs for **accounts (base)**, **savings-account**, **loan-account**, and **share-account**; wired dependencies (accounts depends on the others). Added KDoc, refactored/moved functions, renamed props for consistency, made the filter dialog dynamic (checkboxes from status), introduced card UI for account items, and organized module-specific strings. Tracks sub-work: #2774, #2775, #2776, #2773, #2778, #2782, #2781. |
| 5 | [#2795](https://github.com/openMF/Mifos-mobile/pull/2795) | Improve dynamic account selection; add decimal support in transactions. |
| 6 | [#2782](https://github.com/openMF/Mifos-mobile/pull/2782) | Remove `feature/account` module from CMP (cleanup). |
| 7 | [#2781](https://github.com/openMF/Mifos-mobile/pull/2781) | Add missing imports; remove unnecessary properties in composables. |
| 8 | [#2779](https://github.com/openMF/Mifos-mobile/pull/2779) | **Accounts:** Migrate `feature:accounts` to CMP. |
| 9 | [#2778](https://github.com/openMF/Mifos-mobile/pull/2778) | **Share Account:** Complete CMP migration. |
| 10 | [#2776](https://github.com/openMF/Mifos-mobile/pull/2776) | **Share Account:** Start module migration to CMP. |
| 11 | [#2775](https://github.com/openMF/Mifos-mobile/pull/2775) | **Loan Account:** Migrate module to CMP. |
| 12 | [#2774](https://github.com/openMF/Mifos-mobile/pull/2774) | **Savings Account:** Migrate module to CMP. |
| 13 | [#2773](https://github.com/openMF/Mifos-mobile/pull/2773) | Set up initial directory structure for `feature:account`. |
| 14 | [#2765](https://github.com/openMF/Mifos-mobile/pull/2765) | Configure & fix Detekt for KMP; enable Firebase upload for testing. |
| 15 | [#2762](https://github.com/openMF/Mifos-mobile/pull/2762) | Update README and add Zoom link. |
| 16 | [#2761](https://github.com/openMF/Mifos-mobile/pull/2761) | **About:** Migrate module to CMP. |
| 17 | [#2759](https://github.com/openMF/Mifos-mobile/pull/2759) | Fix incorrect `DataState` import in datastore. |
| 18 | [#2752](https://github.com/openMF/Mifos-mobile/pull/2752) | **Database:** Migrate module to KMP. |
| 19 | [#2748](https://github.com/openMF/Mifos-mobile/pull/2748) | Prevent crash when opening Mifos license; tweak icon colors. |
| 20 | [#2732](https://github.com/openMF/Mifos-mobile/pull/2732) | **Model:** Migrate module to KMP. |
| 21 | [#2724](https://github.com/openMF/Mifos-mobile/pull/2724) | Fix visibility on Savings Account Withdraw screen. |
| 22 | [#2721](https://github.com/openMF/Mifos-mobile/pull/2721) | Docs cleanup: remove outdated Notice section content. |

<div align="right">
  
[![Back To Top](https://img.shields.io/badge/Back%20To%20Top-Blue?style=flat)](#readme-top)

</div>

## KMP Project Template

**Repo:** [`openMF/kmp-project-template`](https://github.com/openMF/kmp-project-template)  
**About:** The **ultimate Kotlin Multiplatform project generator** with a production-ready setup.

- **Cross-Platform Support:** Android, iOS, Desktop, and Web from a single codebase  
- **Multi-Module Architecture:** Clean, organized, and scalable structure  
- **Advanced Source Set Hierarchy:** Sophisticated sharing with logical platform groupings  
- **Pre-configured CI/CD:** GitHub Actions for build, test, and deployment  
- **Code Quality Tools:** Static analysis and formatting pre-wired  
- **Sync Capabilities:** Utilities to stay in sync with upstream template changes  
- **Secrets Management:** Secure handling of keystores and other sensitive artifacts

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
**About:** A **Kotlin Multiplatform** application built on the MifosX core banking platform, designed for field officers to efficiently process transactions, manage client data, track center and group records, and handle accounts (loans, savings, recurring deposits). The goal is to streamline field operations with a shared cross-platform codebase (domain, data, networking), while delivering a polished Android experience and paving the way for additional platforms.

A standout capability is robust **offline support**, enabling officers to work in remote areas and sync when connectivity returns—so underserved clients can still access essential financial services.

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

## CI/CD – GitHub Actions & Reusable Workflows

**Repos:**  
[`openMF/mifos-x-actionhub`](https://github.com/openMF/mifos-x-actionhub) ·
[`openMF/mifos-x-actionhub-build-ios-app`](https://github.com/openMF/mifos-x-actionhub-build-ios-app) ·
[`openMF/mifos-x-actionhub-publish-ios-on-firebase`](https://github.com/openMF/mifos-x-actionhub-publish-ios-on-firebase) ·
[`openMF/mifos-x-actionhub-publish-ios-on-appstore-testflight`](https://github.com/openMF/mifos-x-actionhub-publish-ios-on-appstore-testflight) ·
[`openMF/mifos-x-actionhub-publish-ios-on-appstore`](https://github.com/openMF/mifos-x-actionhub-publish-ios-on-appstore)  
**About:** A suite of **reusable GitHub Actions** and workflows that standardize iOS/KMP delivery across Mifos projects: building signed/unsigned iOS apps, distributing to **Firebase App Distribution**, and publishing to **TestFlight**/**App Store** — with improved reliability via **SSH-based Fastlane Match**, clear inputs, and comprehensive documentation. These actions are used by the KMP template and app repos to keep release pipelines consistent and repeatable.

| No. | PR | Repo | Description |
| --- | --- | --- | --- |
| 1 | [#37](https://github.com/openMF/mifos-x-actionhub/pull/37) | `mifos-x-actionhub` | CI: create Compose resources directory path before build (prevents missing-path failures). |
| 2 | [#36](https://github.com/openMF/mifos-x-actionhub/pull/36) | `mifos-x-actionhub` | Add `ci_gradle_properties_path` support + README updates for flexible Gradle props. |
| 3 | [#35](https://github.com/openMF/mifos-x-actionhub/pull/35) | `mifos-x-actionhub` | CocoaPods-based iOS integration: add `use_cocoapods` and `shared_module` inputs. |
| 4 | [#8](https://github.com/openMF/mifos-x-actionhub-build-ios-app/pull/8) | `build-ios-app` | Docs: add Fastlane configuration and usage guidance. |
| 5 | [#33](https://github.com/openMF/mifos-x-actionhub/pull/33) | `mifos-x-actionhub` | Update iOS workflows to latest Fastlane actions; sync documentation. |
| 6 | [#5](https://github.com/openMF/mifos-x-actionhub-publish-ios-on-firebase/pull/5) | `publish-ios-on-firebase` | Add App Store Connect inputs to Firebase distribution action; README updates. |
| 7 | [#7](https://github.com/openMF/mifos-x-actionhub-build-ios-app/pull/7) | `build-ios-app` | Support both **signed Release** and **Debug** iOS builds in the action. |
| 8 | [#32](https://github.com/openMF/mifos-x-actionhub/pull/32) | `mifos-x-actionhub` | Add Fastlane lane for **App Store** deploy; update repo README. |
| 9 | [#1](https://github.com/openMF/mifos-x-actionhub-publish-ios-on-appstore/pull/1) | `publish-ios-on-appstore` | New action: publish iOS app to App Store via Fastlane + App Store Connect API. |
| 10 | [#31](https://github.com/openMF/mifos-x-actionhub/pull/31) | `mifos-x-actionhub` | Refactor CI to **SSH-based Match** and split **Firebase** / **TestFlight** deploy logic. |
| 11 | [#6](https://github.com/openMF/mifos-x-actionhub-build-ios-app/pull/6) | `build-ios-app` | Switch Match from HTTPS token to **SSH** for signing repo access in CI. |
| 12 | [#4](https://github.com/openMF/mifos-x-actionhub-publish-ios-on-firebase/pull/4) | `publish-ios-on-firebase` | Add **SSH** support and configuration in Firebase iOS publish action. |
| 13 | [#4](https://github.com/openMF/mifos-x-actionhub-publish-ios-on-appstore-testflight/pull/4) | `publish-ios-on-testflight` | Add **SSH** + extended config support for TestFlight deploy action. |
| 14 | [#28](https://github.com/openMF/mifos-x-actionhub/pull/28) | `mifos-x-actionhub` | Bump iOS build action to `v1.0.1`; add extra iOS inputs. |
| 15 | [#5](https://github.com/openMF/mifos-x-actionhub-build-ios-app/pull/5) | `build-ios-app` | README improvements/clarifications. |
| 16 | [#3](https://github.com/openMF/mifos-x-actionhub-build-ios-app/pull/3) | `build-ios-app` | Pass **Match** and **build** parameters via inputs (more reusable). |
| 17 | [#27](https://github.com/openMF/mifos-x-actionhub/pull/27) | `mifos-x-actionhub` | Add `MATCH_GIT_BASIC_AUTHORIZATION` env var for Git authentication. |
| 18 | [#3](https://github.com/openMF/mifos-x-actionhub-publish-ios-on-appstore-testflight/pull/3) | `publish-ios-on-testflight` | README updates for TestFlight action. |
| 19 | [#1](https://github.com/openMF/mifos-x-actionhub-publish-ios-on-appstore-testflight/pull/1) | `publish-ios-on-testflight` | CI: build and upload iOS app to **TestFlight** workflow. |

<div align="right">
  
[![Back To Top](https://img.shields.io/badge/Back%20To%20Top-Blue?style=flat)](#readme-top)

</div>

