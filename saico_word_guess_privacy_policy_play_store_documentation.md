# SAICO Word Guess — Privacy Policy & Play Store Documentation

This document serves as the official **Privacy Policy**, **Data-Handling Specification**, and **Google Play Store Submission Guide** for **SAICO Word Guess** (Native Android App written in Kotlin/Java).

---

## Table of Contents
1. [Privacy Policy](#1-privacy-policy)
2. [Data Handling & Safety Declaration](#2-data-handling--safety-declaration)
3. [Play Store Submission Assets & Documentation](#3-play-store-submission-assets--documentation)
   - [Android Manifest Configuration](#a-android-manifest-configuration)
   - [Store Listing Text](#b-store-listing-text)
   - [Content Rating & Target Audience](#c-content-rating--target-audience)
4. [License & Developer Info](#4-license--developer-info)

---

## 1. Privacy Policy

**Effective Date:** October 12, 2026  
**Last Updated:** October 12, 2026  

### Overview
**SAICO Word Guess** ("we", "our", or "us") respects your privacy. This Privacy Policy describes how we collect, use, and handle data when you play our mobile application on Android devices.

### Information We Collect

1. **Authentication & Identity Data:**
   * **Email Address:** When signing in via **Google Sign-In** (powered by Firebase Auth and Google Credential Manager), we process your email address. This is used exclusively to verify eligibility for SASTRA University campus leaderboards (`@sastra.ac.in`).
   * **Display Name:** Derived from your Google account to identify your score on the public campus leaderboard.

2. **Gameplay & Analytics Data:**
   * **Scores, Time Penalties, and Timestamps:** We store your accumulated points, game activity timestamps, and performance metrics in the **Firebase Realtime Database** to maintain leaderboard integrity.

3. **Guest Mode Data:**
   * Players using **Guest Mode** can play without providing any personally identifiable information (PII). Scores recorded in Guest Mode are saved locally on the device and are **not** submitted to the cloud leaderboard.

### How We Use Your Information

* **Campus Verification:** To verify that the user belongs to SASTRA University (`@sastra.ac.in`) before accepting scores onto the restricted campus leaderboard.
* **Leaderboard Display:** To rank player performance publicly.
* **App Performance:** To fetch dynamic game puzzles from cloud storage (with offline local fallback support).

### Data Privacy & Visibility

* **Email Protection:** Your email address is **never displayed publicly** on the leaderboard. Only your derived Display Name and numerical score are visible to other players.
* **Third-Party Data Sharing:** We do **not** sell, rent, or commercialize your personal information. Data is transmitted securely and exclusively processed by Google Cloud / Firebase backend infrastructure.

### Third-Party Services
The app uses trusted third-party services provided by Google LLC:
* [Firebase Authentication](https://firebase.google.com/products/auth)
* [Firebase Realtime Database](https://firebase.google.com/products/database)
* [Google Credential Manager](https://developer.android.com/identity/sign-in/credential-manager)

### Data Retention and Deletion Requests
* **Retention:** Account information and high scores are retained as long as the application leaderboard remains active.
* **Account & Data Deletion:** Users may request complete removal of their stored profile and leaderboard entries by submitting a deletion request through the **Profile Screen** in the app or by emailing the developer contact provided below.

---

## 2. Data Handling & Safety Declaration

The following mapping corresponds to the **Google Play Console Data Safety Form**:

| Data Category | Specific Field | Collected? | Shared? | Encryption in Transit? | Purpose |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Personal Info** | Name (Display Name) | Yes | No | Yes (HTTPS / TLS) | Leaderboard functionality & account management |
| **Personal Info** | Email Address | Yes | No | Yes (HTTPS / TLS) | User authentication & campus domain verification (`@sastra.ac.in`) |
| **App Activity** | Game Progress / Scores | Yes | No | Yes (HTTPS / TLS) | Score persistence and rank evaluation |
| **Device / Identifiers** | Hardware/Device IDs | No | No | N/A | N/A |

### Security Measures
* **In-Transit Encryption:** All communications with Firebase Realtime Database and Cloud Sheets use HTTPS/TLS encrypted connections.
* **At-Rest Protection:** Data stored on Firebase Realtime Database is governed by Google’s security policies and access rules.

---

## 3. Play Store Submission Assets & Documentation

### A. Android Manifest Configuration

Below is the required configuration for `AndroidManifest.xml` targeting Native Android:

```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.saico.wordguess">

    <!-- Network Permissions for Firebase Auth & Dynamic Cloud Puzzles -->
    <uses-permission android:name="android.permission.INTERNET" />
    <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />

    <application
        android:allowBackup="true"
        android:icon="@mipmap/ic_launcher"
        android:label="SAICO Word Guess"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/Theme.SAICOWordGuess">

        <!-- Fullscreen Splash Activity (6s Intro Video) -->
        <activity
            android:name=".ui.SplashActivity"
            android:exported="true"
            android:screenOrientation="portrait"
            android:theme="@style/Theme.SAICOWordGuess.NoActionBar.Fullscreen">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />
                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>

        <!-- Main Game Activity (Strict Portrait Lock) -->
        <activity
            android:name=".ui.MainActivity"
            android:exported="false"
            android:screenOrientation="portrait"
            android:windowSoftInputMode="adjustResize" />

    </application>

</manifest>
```

---

### B. Store Listing Text

#### Short Description *(80 characters max)*
```text
Challenge your vocabulary in SAICO Word Guess! Race against the spiral timer!
```

#### Full Description
```text
Welcome to SAICO Word Guess — an intense word-puzzle game built for speed, accuracy, and quick thinking!

⚡ GAMEPLAY FEATURES:
• 90-Second Spiral Countdown: Watch time tick down on an inward-filling spiral canvas.
• Dynamic Puzzles: Fresh hints and words delivered straight from the cloud with seamless offline support.
• Tactical Scoring:
  - Correct Answer: +20 Seconds
  - Wrong Answer: -15 Seconds
  - Skip Word: -10 Seconds
• Smart UI Controls: Interactive buttons that adapt dynamically to your inputs.

🎓 CAMPUS LEADERBOARD:
• Sign in using Google Sign-In with your verified SASTRA University email (@sastra.ac.in).
• Compete against fellow students and claim the top spot on the live leaderboards!
• Privacy-First Design: Your email is kept completely private—only your display name and high scores are shown.

🎮 GUEST MODE & NAVIGATION:
• Play immediately in Guest Mode without logging in.
• Uniform bottom navigation with animated marquee scrolling lets you toggle easily between Gameplay, Leaderboards, and Profile management.

Download SAICO Word Guess today and put your vocabulary to the ultimate test!
```

---

### C. Content Rating & Target Audience

* **Target Age Group:** Everyone (3+ / PEGI 3 / ESRB Everyone).
* **In-App Purchases:** No.
* **Contains Ads:** No.
* **Interactive Elements:** Users Share Info (Display names visible on public leaderboards).
* **Violence / Sexual Content / Sensitive Topics:** None.

---

## 4. License & Developer Info

* **Developer Name:** SAICO Development Team
* **Institution:** SASTRA Deemed University
* **Contact Email:** `support@sastra.ac.in` *(Replace with your project support email)*
* **Repository:** [GitHub - SAICO Word Guess](https://github.com/)

---
*Created for SAICO Word Guess Android Release.*