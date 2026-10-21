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
