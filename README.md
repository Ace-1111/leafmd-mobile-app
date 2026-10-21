# 🌿 LeafMD – AI Plant Disease Diagnosis System

[![Download APK](https://img.shields.io/badge/Download%20APK-Google%20Drive-34A853?style=for-the-badge&logo=google-drive&logoColor=white)](https://drive.google.com/file/d/1aRWoSLHJe0gYo9M21WRpYLrDX_EUZzX7/view?usp=sharing)
[![Live Backend](https://img.shields.io/badge/API-Render-46E3B7?style=for-the-badge&logo=render&logoColor=black)](https://leafmd-api.onrender.com)
[![Flutter](https://img.shields.io/badge/Frontend-Flutter-02569B?style=for-the-badge&logo=flutter&logoColor=white)](https://github.com/Ace-1111/leafmd-mobile-app)
[![FastAPI](https://img.shields.io/badge/Backend-FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)](https://github.com/Ace-1111/plant-disease-backend)

An intelligent, cloud-connected mobile health companion for crops. Farmers and gardeners can snap photos of infected plant leaves and receive instant AI diagnosis with cure recommendations.

---

## 📲 Try the App (Instant Install)

Direct ready-to-use APK download karke apne Android phone par install karein:

👉 **[📥 Download LeafMD APK (Latest Release)](https://drive.google.com/file/d/1aRWoSLHJe0gYo9M21WRpYLrDX_EUZzX7/view?usp=sharing)**

> **Note:** Install karte samay agar *"Install from Unknown Sources"* ya *"Play Protect Warning"* aaye, toh **Install anyway** select karein.

---

## ✨ Features
* 📸 **Capture & Gallery Upload:** Instant leaf capture via phone camera or gallery selector.
* ✂️ **Interactive Cropping:** Crop precisely to the diseased foliage spot for maximum AI accuracy.
* ⚡ **Live Cloud Classification:** Connected 24/7 to our containerized FastAPI backend on Render.
* 🛡️ **Remedies & Advice:** Provides organic & chemical remedies alongside the confidence score.

---

## 🛠️ Tech Stack
* **Frontend:** Flutter (Dart)
* **Backend:** FastAPI (Python)
* **Tools:** `image_picker`, `image_cropper`, `flutter_launcher_icons`
* **Live API Backend:** [leafmd-api on Render](https://leafmd-api.onrender.com)
* **Backend Source Code:** [plant-disease-backend](https://github.com/Ace-1111/plant-disease-backend)

---

## 🚀 Run Locally

### Prerequisites
* Flutter SDK installed
* Android Studio / VS Code

### Steps
```bash
git clone https://github.com/Ace-1111/leafmd-mobile-app.git
cd leafmd-mobile-app
flutter pub get
flutter run
```
---
## System Architecture
```mermaid
graph TD
    %% Styling
    classDef client fill:#02569B,stroke:#013B6B,stroke-width:2px,color:#fff;
    classDef cloud fill:#009688,stroke:#00695C,stroke-width:2px,color:#fff;
    classDef ai fill:#FF6F00,stroke:#E65100,stroke-width:2px,color:#fff;
    classDef output fill:#2E7D32,stroke:#1B5E20,stroke-width:2px,color:#fff;

    subgraph Mobile_App ["📱 Flutter Mobile Client"]
        A[Camera / Gallery Selection]:::client --> B[Interactive Image Cropper]:::client
        B --> C[HTTP Multipart Request]:::client
    end

    subgraph Cloud_Backend ["☁️ Render Cloud Infrastructure"]
        C -->|POST /predict via HTTPS| D[FastAPI Gateway]:::cloud
        D --> E[Image Tensor Preprocessing]:::cloud
    end

    subgraph AI_Engine ["🧠 Deep Learning Inference"]
        E --> F[CNN Classification Model]:::ai
        F --> G[Extract Predictions & Confidence]:::ai
        G --> H[Map Remedial Measures]:::ai
    end

    subgraph Result_Display ["📊 Diagnosis Output"]
        H -->|JSON Response| I[Flutter Results Screen]:::output
        I --> J[Disease Name & Confidence %]:::output
        I --> K[Organic & Chemical Treatments]:::output
    end
