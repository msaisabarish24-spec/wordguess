# SAICO Word Guess 

**SAICO Word Guess** is a fast-paced native Android word-puzzle game built using **Kotlin/Java**. Players race against an inward-filling 90-second spiral countdown timer to guess words using dynamic hints fetched from cloud storage. It features seamless offline fallbacks, Google Sign-In with Firebase Auth, and an exclusive verified campus leaderboard for **SASTRA University** (`@sastra.ac.in`) students.

---

##  Features

* **Cinematic Intro:** 6-second fullscreen portrait video splash screen.
* **Locked Portrait Orientation:** Optimized strictly for single-handed vertical smartphone gameplay.
* **Dynamic Canvas Timer:** Custom 90-second inward-filling spiral timer rendered dynamically on canvas.
* **Tactical Time Mechanics:**
  *  **Correct Guess:** Adds **+20 seconds**.
  *  **Wrong Guess:** Penalizes **-15 seconds**.
  *  **Skip Word:** Moves to the next puzzle with a **-10 seconds** penalty.
  *  **Smart Input:** Guess button automatically disables when the input box is empty.
* **Cloud & Offline Sync:** Dynamically fetches puzzles and hints from cloud spreadsheets with local offline fallbacks.
* **Authentication Options:**
  * **Google Sign-In:** Secure authentication using Google Credential Manager & Firebase Auth.
  * **Guest Mode:** Play immediately without signing in (scores saved locally).
* **Campus Leaderboard:**
  * Restricted submission strictly to verified SASTRA University domain emails (`@sastra.ac.in`).
  * Privacy-first: User emails are kept private; only public Display Names and cumulative scores are displayed.
* **Persistent Bottom Navigation:** Smooth navigation between Game, Leaderboards, and Profile screens featuring marquee horizontal text scrolling for long titles.

---

##  Tech Stack & Architecture

* **Language:** Kotlin / Java
* **UI Framework:** Android Native Layouts (XML) with custom Canvas drawing
* **Authentication:** Google Credential Manager API & Firebase Authentication
* **Database & Cloud Storage:** Firebase Realtime Database & Google Sheets API
* **Architecture:** MVVM (Model-View-ViewModel)

---

##  Repository Structure

```text
SAICO-Word-Guess/
├── app/
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/com/saico/wordguess/
│   │   │   │   ├── data/          # Firebase, Spreadsheet APIs, & Repositories
│   │   │   │   ├── ui/            # Activities, Fragments, Custom Canvas Views
│   │   │   │   └── util/          # Timer, Marquee, & Validation Utils
│   │   │   ├── res/
│   │   │   │   ├── raw/           # saico_word_guess_intro_6s.mp4
│   │   │   │   └── layout/        # App Layout XMLs
│   │   │   └── AndroidManifest.xml
├── build.gradle
├── README.md
└── PRIVACY_POLICY.md
```

---

##  Getting Started

### Prerequisites
* **Android Studio:** Ladybug (2024.2.1) or newer recommended.
* **JDK:** Version 17 or higher.
* **Android SDK:** API Level 24 (Android 7.0) minimum, targeting API Level 34/35.

### Installation & Setup

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/your-username/saico-word-guess.git
   cd saico-word-guess
   ```

2. **Configure Firebase:**
   * Create a project in the [Firebase Console](https://console.firebase.google.com/).
   * Enable **Google Auth** in Firebase Authentication.
   * Add an Android app with your package name (`com.saico.wordguess`) and SHA-1 fingerprint.
   * Download `google-services.json` and place it in the `app/` directory.

3. **Build the Project:**
   Open the project in Android Studio, sync Gradle, and run it on an emulator or connected physical Android device.

---

##  Rules & Game Mechanics Summary

| Action | Result / Impact |
| :--- | :--- |
| **Initial Time** | 90-Second Countdown (Inward Spiral Timer) |
| **Correct Guess** | +20 Seconds Added |
| **Wrong Guess** | -15 Seconds Subtracted |
| **Skip Button** | Next Puzzle & -10 Seconds Subtracted |
| **Campus Ranking Eligibility** | Requires authentication with `@sastra.ac.in` email |

---

##  Privacy & Play Store Documentation

A complete, Play Store-compliant **Privacy Policy** and **Data Safety Specification** can be found in [PRIVACY_POLICY.md](./privacypolicy.md) (or within the app's Profile Screen).

---

## 📄 License & Credits

Developed by **Mister Sai Sabarish** for the **SAICO Project**.  
For inquiries, support, or feedback, please open an issue in this repository.
