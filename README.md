<div align="center">

<img src="assets/mascot.png" width="140" alt="SleepSkr mascot"/>

# SleepSkr

### *Sleep to Learn.*

**Track your nights. Unlock daily knowledge. Build habits that compound.**

[![Android](https://img.shields.io/badge/Android-10%2B-3DDC84?style=flat-square&logo=android&logoColor=white)](https://android.com)
[![Kotlin](https://img.shields.io/badge/Kotlin-2.0-7F52FF?style=flat-square&logo=kotlin&logoColor=white)](https://kotlinlang.org)
[![Jetpack Compose](https://img.shields.io/badge/Jetpack_Compose-Material_3-4285F4?style=flat-square&logo=jetpackcompose&logoColor=white)](https://developer.android.com/jetpack/compose)
[![Solana Mobile](https://img.shields.io/badge/Solana_Mobile-Seeker-9945FF?style=flat-square&logo=solana&logoColor=white)](https://solanamobile.com)
[![License](https://img.shields.io/badge/License-Proprietary-1A1A1A?style=flat-square)](#license)
[![Version](https://img.shields.io/badge/Version-1.0.20-14F195?style=flat-square)](#)

**[🌐 Website](https://makidevweb3.github.io/SleepSKR/) · [🔒 Privacy Policy](https://makidevweb3.github.io/SleepSKR/privacy-policy.html) · [📋 Copyright](https://makidevweb3.github.io/SleepSKR/copyright.html) · [💬 Discord](https://discord.gg/Dqr8Kd8fFP)**

---

</div>

## What is SleepSkr?

SleepSkr is a **Sleep to Learn** Android app — a minimalist sleep tracker that turns your nightly routine into a compounding knowledge engine. Every night you log, a new piece of educational content unlocks on the Science screen. Sleep consistently. Learn consistently.

Built for the **Solana Mobile Seeker** ecosystem. Privacy-first. 100% local. No account required.

---

## Features

| | Feature | Description |
|---|---|---|
| 🌙 | **Sleep Tracking** | Log bedtime, wake time, quality (1–5★), dreams, mood, and night wakeups |
| 📚 | **Sleep to Learn** | Daily educational content unlocks based on your sleep consistency |
| 🔥 | **Streak System** | Track your consistency up to 90 days with progressive thresholds |
| 📊 | **Analytics** | Global score, deep sleep estimation, cycle count, quality trends |
| 🧬 | **Circadian Science** | Insights based on real sleep research, built into the Science screen |
| 🔒 | **Privacy First** | 100% local Room Database — no server, no cloud, no account needed |
| ⛓️ | **Solana Mobile** | Optional Saga/Seeker wallet integration — no transactions, identity only |
| 🌐 | **4 Languages** | English · Français · 中文 · Русский |
| 🎮 | **Proof of Sleep** | Gamified transition screen with blockchain aesthetics |
| 📱 | **Guest Mode** | Use the full app instantly without any sign-up |

---

## Tech Stack

```
Language        Kotlin
UI Framework    Jetpack Compose (Material 3)
Architecture    MVVM + Coroutines/Flow + Hilt
Database        Room (100% local SQLite)
DI              Hilt / Dagger
Web3            Solana Mobile Wallet Adapter (optional)
Min SDK         Android 10 (API 29)
Target SDK      Android 14 (API 34)
Package         com.taqueur.sommeil
```

---

## Architecture

```
com.taqueur.sommeil/
├── data/
│   ├── db/              # Room Database, DAOs
│   ├── entities/        # SleepSession, ScientificInsight
│   └── repository/      # Data access layer
├── di/                  # Hilt modules
├── ui/
│   ├── screens/         # Home, Analytics, Science, Profile
│   │   ├── HomeScreen
│   │   ├── AnalyticsScreen
│   │   ├── ScienceScreen
│   │   └── ProfileScreen
│   ├── components/      # Shared Composables
│   ├── theme/           # Colors, Typography, Shapes
│   └── navigation/      # NavHost, BottomBar
├── viewmodel/           # ViewModels per screen
└── util/                # Score calculator, date helpers
```

---

## Data Model

```kotlin
@Entity(tableName = "sleep_sessions")
data class SleepSession(
    @PrimaryKey val id: String = UUID.randomUUID().toString(),
    val bedTimeTimestamp: Long,
    val wakeTimeTimestamp: Long?,     // null if session in progress
    val qualityRating: Int?,          // 1 to 5
    val hadDreams: Boolean?,
    val nightWakeups: Int?,
    val mood: String?,                // "FATIGUED" | "NORMAL" | "ENERGETIC"
    val calculatedScore: Int?,        // 0–100
    val createdAt: Long = System.currentTimeMillis()
)
```

---

## Design System

```
Background      #F5F0E8  (warm beige)
Cards           #EDE6D8
Ink             #1A1A1A  (deep black)
Solana accent   #9945FF → #14F195
Typography      Poppins / Inter (geometric sans-serif)
Corner radius   Generous (16–24dp)
```

Minimalist beige/black aesthetic designed for pre-sleep and post-wake clarity — minimal cognitive load, maximum calm.

---

## Screens

```
Splash          Minimal beige + moon icon
Onboarding      Starry moon illustration, guest mode CTA
Home            Day state (sleep CTA) / Night state (session in progress)
Wake Up         Morning logging form (time, quality, mood, dreams)
Proof of Sleep  Gamified validation — blockchain aesthetic, dark/violet
Analytics       Circular score gauge + 2×2 stats grid
Science         Daily unlocks — streak, circadian insights, study cards
Profile         Stats, preferences, language, theme, wallet, data export
```

---

## Availability

<div align="center">

**SleepSkr is distributed exclusively via the [Seeker Mobile Dapp Store](https://solanamobile.com).**

Optimized for Solana Saga & Seeker · Compatible with any Android 10+ device

</div>

---

## Localization

SleepSkr ships with full string coverage across 4 languages:

| Language | Code | Status |
|---|---|---|
| English | `en` | ✅ Complete |
| Français | `fr` | ✅ Complete |
| 中文 | `zh` | ✅ Complete |
| Русский | `ru` | ✅ Complete |

---

## Privacy

> **SleepSkr collects zero data.**

- All sleep data is stored locally on-device via Room Database
- No internet connection required
- No analytics, crash reporting, or telemetry
- The daily unlock system runs entirely on-device — no server validates your sleep
- Solana wallet integration is optional, read-only (public address only), zero transactions
- One-tap data deletion from the Profile screen

→ Full details: [Privacy Policy](https://makidevweb3.github.io/SleepSKR/privacy-policy.html)

---

## License

```
Copyright © 2025 tobeamaki.store — All Rights Reserved.

SleepSkr is proprietary software. The source code, unlock system logic,
educational content, visual design, and brand assets are the exclusive
intellectual property of tobeamaki.store.

Redistribution, modification, reverse engineering, or reuse of any part
of this software is prohibited without explicit written permission.
```

Third-party open-source libraries (Jetpack Compose, Room, Hilt, Kotlin Coroutines, Material 3, Solana MWA) remain under their respective Apache 2.0 licenses.

→ Full details: [Copyright](https://makidevweb3.github.io/SleepSKR/copyright.html)

---

## Contact

<div align="center">

**tobeamaki.store**

[🌐 Website](https://tobeamaki.store) · [💬 Discord](https://discord.gg/Dqr8Kd8fFP) · [📧 maki@tobeamaki.store](mailto:maki@tobeamaki.store) · [🎵 TikTok @tobeamaki](https://tiktok.com/@tobeamaki)

<img src="assets/mascot.png" width="60" alt="SleepSkr"/>

*Sweet dreams. Sharp mind.*

</div>
