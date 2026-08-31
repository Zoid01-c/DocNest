# 🦅 DocNest — Intelligent On-Device Personal Document Hub

<p align="center">
  <img src="app/src/main/res/drawable/app_logo.png" alt="DocNest Logo" width="128" height="128" style="border-radius: 28px;" />
</p>

<p align="center">
  <b>Organize, View, Encrypt, and Manage all your Personal Documents with 100% On-Device Privacy.</b>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Android-3DDC84?style=for-the-badge&logo=android&logoColor=white" alt="Platform" />
  <img src="https://img.shields.io/badge/Kotlin-2.0.21-7F52FF?style=for-the-badge&logo=kotlin&logoColor=white" alt="Kotlin" />
  <img src="https://img.shields.io/badge/Jetpack%20Compose-Material%203-4285F4?style=for-the-badge&logo=jetpackcompose&logoColor=white" alt="Compose" />
  <img src="https://img.shields.io/badge/Privacy-100%25%20Offline-green?style=for-the-badge" alt="Offline" />
  <img src="https://img.shields.io/badge/License-MIT-blue?style=for-the-badge" alt="License" />
</p>

---

## 🌟 Overview

**DocNest** is a privacy-first, lightning-fast Android personal document manager engineered with **Jetpack Compose** and modern Android architecture. 

Unlike traditional cloud-based document managers that upload sensitive files to remote servers, DocNest operates **100% locally on your device**. It scans, auto-categorizes, decrypts, and manages identity cards, academic marksheets, tax statements, and medical reports without a single byte of data leaving your phone.

---

## ✨ Key Features

### 🧠 Smart On-Device Auto-Classification
* **Page-1 Content Intelligence:** Even if a file is named `DOC-20240830-WA0012.pdf` or `Scan_001.pdf`, DocNest analyzes the first-page text stream to identify academic marksheets, exam hall tickets, degree certificates, Aadhaar, PAN cards, salary slips, and tax statements.
* **Folder Context Heuristics:** Automatically derives context from parent directories (e.g. `/College/`, `/Academics/`, `/Salary/`, `/Bills/`).
* **5 Core Intelligent Categories:**
  - 🎓 **Education:** Marksheets, Degrees, Hall Tickets, Results, Transcripts.
  - 🪪 **Identity:** Aadhaar Cards, PAN Cards, Passports, Driving Licenses, Voter IDs.
  - 💰 **Finance:** Salary Slips, ITR / Tax Returns, Bank Statements, Bills, Invoices.
  - 👤 **Personal:** Medical Reports, Resumes/CVs, Rent Agreements, Vehicle RC/PUC.
  - 📁 **Other:** Generic & custom-tagged documents.

---

### 📖 Fluid Multi-Page PDF Viewer
* **Natural Gesture Navigation:** Swipe left/right seamlessly between pages with 60 FPS fling physics and momentum.
* **Smart Zoom & Pan:** Double-tap or pinch to zoom up to 5x with fluid 2D panning. Swiping automatically switches between panning (when zoomed) and page switching (when at 1.0x).
* **High-Performance Memory Cache:** Thread-safe `LruCache` bitmap rendering ensures zero lag when browsing multi-page documents.

---

### 🔒 Password-Protected PDF & e-Aadhaar Support
* **On-Device Decryption:** Open encrypted PDFs (such as password-protected e-Aadhaar files, salary slips, and bank statements) directly inside the app.
* **Helpful Guides & Persistence:** Built-in guidance for e-Aadhaar password formats (*First 4 letters of name in CAPITAL + Birth Year*) with optional encrypted "Remember Password" persistence.

---

### 🛡️ Hardware-Backed App Lock
* **Biometric & PIN Authentication:** Secure your entire document vault using Android's native `BiometricPrompt` (Fingerprint, Face Unlock, or Device PIN).
* **Lifecycle Protection:** Automatically locks when the app is backgrounded or switched, keeping sensitive files safe from prying eyes.

---

### 📤 Universal Sharing & External Viewing
* **Secure FileProvider Integration:** Share documents directly to WhatsApp, Gmail, Drive, or open them in external viewers (Adobe Reader, Google Drive) with instant read permissions and zero permission errors.

---

### 🎨 Modern Material You Design
* **Dynamic Theming:** Beautiful Light & Dark modes, fluid glassmorphism surfaces, and bouncy spring animations.
* **Clean & Distraction-Free:** Sleek top app bar with zero clutter.

---

## 🛠️ Tech Stack & Architecture

DocNest is built using the latest industry standards for modern Android development:

* **UI Layer:** 100% [Jetpack Compose](https://developer.android.com/jetpack/compose) with Material 3 design tokens.
* **Architecture:** MVVM (Model-View-ViewModel) + Unidirectional Data Flow (UDF).
* **Asynchronous Programming:** Kotlin [Coroutines](https://kotlinlang.org/docs/coroutines-overview.html) & [StateFlow](https://developer.android.com/kotlin/flow/stateflow-and-sharedflow).
* **Database & Persistence:**
  - [Room Database](https://developer.android.com/training/data-storage/room) with SQLite indexing.
  - [Jetpack DataStore](https://developer.android.com/topic/libraries/architecture/datastore) for reactive settings.
* **PDF & Document Engine:**
  - Hardware-accelerated `android.graphics.pdf.PdfRenderer`.
  - On-Device [`pdfbox-android`](https://github.com/TomRoush/PdfBox-Android) for encrypted document decryption & text extraction.
* **Security & System:**
  - AndroidX `BiometricPrompt` API.
  - `androidx.core.content.FileProvider`.

---

## 📱 Screenshots

<p align="center">
  <img src="screenshots/home_screen.png" width="30%" alt="Home Dashboard" />
  &nbsp;&nbsp;&nbsp;&nbsp;
  <img src="screenshots/viewer_screen.png" width="30%" alt="Swipeable PDF Viewer" />
  &nbsp;&nbsp;&nbsp;&nbsp;
  <img src="screenshots/settings_screen.png" width="30%" alt="Settings & App Lock" />
</p>

---

## 🚀 Getting Started

### Prerequisites
* **Android Studio:** Hedgehog (2023.1.1) or newer.
* **JDK:** Version 17 or 21.
* **Android Device / Emulator:** Android 8.0 (API Level 26) or higher.

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/your-username/DocNest.git
   cd DocNest
   ```

2. **Open in Android Studio:**
   * Launch Android Studio.
   * Select **Open** and choose the `DocNest` project folder.

3. **Build and Run:**
   * Let Gradle sync dependencies.
   * Press `Shift + F10` or click the **Run ▶** button to launch on your device/emulator.

4. **Build APK via Command Line:**
   ```bash
   # On Windows
   .\gradlew.bat assembleDebug

   # On macOS / Linux
   ./gradlew assembleDebug
   ```
   The output APK will be located at: `app/build/outputs/apk/debug/app-debug.apk`.

---

## 🧪 Running Unit Tests

DocNest includes a unit test suite covering document classification, regex parsing, and multi-page indexing:

```bash
# Run all unit tests
.\gradlew.bat testDebugUnitTest
```

---

## 👨‍💻 Creator & Lead Developer

Created with passion by **Rehan Jakir Khan**.

* 🐙 **GitHub:** [github.com/rehanjakirkhan](https://github.com/) *(Add your username)*
* 💼 **LinkedIn:** [linkedin.com/in/rehanjakirkhan](https://linkedin.com/) *(Add your profile)*

---

## 📄 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

---

<p align="center">
  Made with ❤️ for 100% On-Device Privacy.
</p>
