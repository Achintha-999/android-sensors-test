<div align="center">

# 📱 Android Sensors Test

**A simple Android app to test and view device sensor data in real time**  
Built as a lightweight example project to read sensors using Android’s `SensorManager`.

<br/>

<!-- Badges (decorative + useful) -->
![Platform](https://img.shields.io/badge/Platform-Android-3DDC84?logo=android&logoColor=white)
![Language](https://img.shields.io/badge/Language-Java-007396?logo=coffeescript&logoColor=white)
![Build](https://img.shields.io/badge/Build-Gradle-02303A?logo=gradle&logoColor=white)
![IDE](https://img.shields.io/badge/IDE-Android%20Studio-3DDC84?logo=androidstudio&logoColor=white)

</div>

---

## ✨ Overview

**Android Sensors Test** is an Android application that launches a single screen (`MainActivity`) and listens to the device sensors.  
It is useful for:

- ✅ Quickly verifying which sensors your phone has  
- ✅ Watching **live sensor values** while moving the device  
- ✅ Learning how to use Android’s **sensor APIs** in a minimal project

---

## 🧭 Project Structure

```text
android-sensors-test/
├─ app/
│  ├─ src/main/
│  │  ├─ AndroidManifest.xml
│  │  ├─ java/lk/acx/sensors/MainActivity.java
│  │  └─ res/...
│  └─ build.gradle
├─ build.gradle
├─ settings.gradle
└─ gradlew / gradlew.bat
```

**Entry point:** `MainActivity`  
**Package:** `lk.acx.sensors`  
**Launcher Activity:** Declared in the manifest.

---

## 🧩 How it works (high level)

### 1) App Launch 🚀
When you open the app, Android starts:

- `lk.acx.sensors.MainActivity`

as the launcher activity (configured in the manifest).

### 2) Sensor Access 🧠
Inside `MainActivity`, the app uses Android’s sensor framework (typically via):

- `SensorManager` to access the sensor service  
- One or more `Sensor` objects (accelerometer, gyroscope, etc.)  
- A listener (commonly `SensorEventListener`) to receive real-time updates

### 3) Real-time Updates 📈
As the device moves, Android delivers sensor events and the UI is updated to show the latest values.

> Notes:
> - Behavior depends on sensor availability (some devices may not have all sensors).
> - Update rate / sampling depends on the chosen sensor delay and device hardware.

---

## 📋 Requirements

### ✅ Software
- Android Studio (recommended)
- Android SDK installed via Android Studio
- Gradle wrapper included (`./gradlew`)

### ✅ Device
- Any Android phone/emulator (phone recommended for real sensors)
- For best results: a device with accelerometer/gyroscope/magnetometer

---

## ⚙️ Setup & Run

### Option A: Android Studio (recommended) 🛠️
1. **Clone** the repository
2. Open the project in **Android Studio**
3. Let Gradle sync complete
4. Connect a device (USB debugging enabled) or use an emulator
5. Press **Run ▶**

### Option B: Command line 🧪
From the repository root:

```bash
# macOS/Linux
./gradlew assembleDebug
```

```bat
:: Windows
gradlew.bat assembleDebug
```

Then install the generated APK on a device.

---

## 📄 Manifest / App Configuration

The app defines an application and a single launcher activity in:

- `app/src/main/AndroidManifest.xml`

Key facts:
- App label is set via `@string/app_name`
- Theme: `@style/Theme.Sensors`
- Launcher activity: `.MainActivity`

---

## 🔐 Permissions

Most common motion sensors (accelerometer, gyroscope, etc.) **do not require runtime permissions**.

If you extend this project later to use sensors/features like:
- location (GPS)
- body sensors / health-related data
- bluetooth / nearby devices

…you may need to add extra permissions and runtime permission handling.

---

## 🧪 Use cases / Examples

- 🧰 Hardware diagnostics: confirm sensor presence and sanity-check values
- 🧑‍🎓 Education: learn sensor listeners, lifecycle handling, and update rates
- 🕹️ Prototyping: quickly test sensor-driven UI/controls

---

## 🧯 Troubleshooting

### “No sensor values / always zero”
- Your device may not have that sensor
- Try a real phone (emulators often don’t provide real sensor data by default)
- Ensure the app is properly registering the listener (and unregistering on pause)

### “App feels slow / too many updates”
- Reduce the sampling rate (use a slower delay)
- Update UI less frequently (throttle UI updates)

---

## 🗺️ Roadmap (optional ideas)

If you want to expand this project:
- Add a **sensor list screen** (show all sensors supported by the device)
- Add **charts/graphs** (plot sensor data over time)
- Add **export** (CSV logging)
- Add **calibration** helpers (e.g., magnetometer calibration tips)

---

## 🤝 Contributing

Contributions are welcome:
1. Fork the repo
2. Create a feature branch
3. Commit changes
4. Open a pull request

---

## 📜 License

No license file is currently included.  
If you want this project to be reusable by others, consider adding a license (e.g., MIT, Apache-2.0).

---

## 📌 Key Files

- `app/src/main/AndroidManifest.xml` — app + launcher activity configuration  
- `app/src/main/java/lk/acx/sensors/MainActivity.java` — main sensor reading logic  
- `app/build.gradle` — app module build configuration  

---
