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

## 🏛️ System Architecture

```mermaid
flowchart TD
    subgraph Client ["📱 Client Layer (Flutter App)"]
        UI1["📸 Camera / Gallery"] --> UI2["✂️ Image Cropper & Preview"]
        UI2 --> HTTP["🌐 Multipart HTTP POST (/predict)"]
    end

    subgraph Cloud ["☁️ Cloud Server (Render.com)"]
        API["⚡ FastAPI Endpoint Gateway"]
        PRE["🔄 Preprocessing (Resize to 256x256, Normalize)"]
        HTTP --> API
        API --> PRE
    end

    subgraph Model ["🧠 AI Inference Engine"]
        CNN["🌲 Deep Learning CNN Model"]
        CONF["📊 Argmax & Softmax Confidence Calculation"]
        REMEDY["💊 Cure & Prevention Mapping"]
        PRE --> CNN
        CNN --> CONF
        CONF --> REMEDY
    end

    subgraph Response ["📲 User Presentation"]
        JSON["📦 JSON Payload (Class, Confidence, Remedies)"]
        RESULT["📋 Interactive Diagnosis Card on Mobile"]
        REMEDY --> JSON
        JSON --> RESULT
    end

    style Client fill:#0f172a,stroke:#38bdf8,stroke-width:2px,color:#fff
    style Cloud fill:#1e1b4b,stroke:#818cf8,stroke-width:2px,color:#fff
    style Model fill:#064e3b,stroke:#34d399,stroke-width:2px,color:#fff
    style Response fill:#312e81,stroke:#a78bfa,stroke-width:2px,color:#fff
```
