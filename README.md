# 🌿 LeafMD – Mobile Application

LeafMD is a cross-platform Flutter application designed to assist farmers and gardeners in detecting plant leaf diseases instantly using Computer Vision and AI.

---

## 📱 Features
* **Camera & Gallery Capture:** Directly photograph infected leaves or pick from the gallery.
* **Smart Crop:** Integrated cropping tool to focus specifically on affected leaf regions.
* **Real-time Diagnostics:** Connects to a cloud-hosted FastAPI backend for sub-second classification.
* **Treatment Recommendations:** Displays disease confidence scores along with practical remedies.

---

## 🛠️ Tech Stack
* **Framework:** Flutter (Dart)
* **Backend Integration:** REST APIs via `http` package
* **Tools:** `image_picker`, `image_cropper`, `flutter_launcher_icons`
* **Live API Backend:** [leafmd-api on Render](https://leafmd-api.onrender.com)
* **Backend Source Code:** [plant-disease-backend](https://github.com/Ace-1111/plant-disease-backend)

---

## 🚀 Getting Started

### Prerequisites
* Flutter SDK installed
* Android Studio / VS Code

### Run Locally
```bash
git clone [https://github.com/Ace-1111/leafmd-mobile-app.git](https://github.com/Ace-1111/leafmd-mobile-app.git)
cd leafmd-mobile-app
flutter pub get
flutter run


# 🌿 LeafMD – AI Plant Disease Diagnosis System

[![Download APK](https://img.shields.io/badge/Download%20APK-Google%20Drive-34A853?style=for-the-badge&logo=google-drive&logoColor=white)]https://drive.google.com/file/d/1aRWoSLHJe0gYo9M21WRpYLrDX_EUZzX7/view?usp=sharing
[![Live Backend](https://img.shields.io/badge/API-Render-46E3B7?style=for-the-badge&logo=render&logoColor=black)](https://leafmd-api.onrender.com)
[![Flutter](https://img.shields.io/badge/Frontend-Flutter-02569B?style=for-the-badge&logo=flutter&logoColor=white)](https://github.com/Ace-1111/leafmd-mobile-app)
[![FastAPI](https://img.shields.io/badge/Backend-FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)](https://github.com/Ace-1111/plant-disease-backend)

An intelligent, cloud-connected mobile health companion for crops. Farmers and gardeners can snap photos of infected plant leaves and receive instant AI diagnosis with cure recommendations.

---

## 📲 Try the App (Instant Install)

Aapko code compile karne ki zaroorat nahi hai. Direct ready-to-use APK download karke install karein:

👉 **[📥 Download LeafMD APK (Latest Release)][(https://drive.google.com/file/d/1aRWoSLHJe0gYo9M21WRpYLrDX_EUZzX7/view?usp=sharing)]**


---

## ✨ Features
* 📸 **Capture & Gallery Upload:** Instant leaf capture via phone camera or gallery selector.
* ✂️ **Interactive Cropping:** Crop precisely to the diseased foliage spot for maximum AI accuracy.
* ⚡ **Live Cloud Classification:** Connected 24/7 to our containerized FastAPI backend on Render.
* 🛡️ **Remedies & Advice:** Provides organic & chemical remedies alongside the confidence score.

---

## 🏛️ System Architecture

```text
  [Android Device (LeafMD App)]
                │
                ▼ (Multipart Upload)
  [Cloud: Render.com Container]
                │
                ▼ (FastAPI /predict)
    [AI Vision Inference Engine]
                │
                ▼ (JSON: Disease, Confidence, Remedy)
  [Instant Health Report on Screen]
