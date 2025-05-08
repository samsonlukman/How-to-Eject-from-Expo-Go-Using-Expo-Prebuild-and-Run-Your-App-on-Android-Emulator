# How to Eject from Expo Go Using Expo Prebuild and Run Your App on Android Emulator

## Step-by-Step Guide

### 1. Prebuild the App
```bash
npx expo prebuild
```

### 2. Run the Android App
```bash
npx expo run:android
```
> This will build your app and attempt to open it on an Android emulator or connected phone. You may encounter an error. Follow
> next step below.

---

### 3. Set Up Android SDK
- Download **Android Studio**.
- Go to **More actions > SDK Manager > SDK Tools**.
- Install the following:
  - Android SDK Command-line Tools

### 4. Copy Android SDK Path
You will need the SDK location for the next steps.

---

### 5. Configure `local.properties`
In your app folder:
- Navigate to the `android` directory.
- Create a file named `local.properties` if it doesn't already exist.
- Add this line (replace with your actual path):
```properties
sdk.dir=C:\Users\HP\AppData\Local\Android\Sdk
```

---

### 6. Run the App
```bash
npx expo run:android
```
> Your app should open on your emulator or phone.

---

### 7. Handle License Errors
If you encounter a license error:
- Open **Command Prompt (CMD)**.
- Navigate to your Android SDK folder.
- Go into the `cmdline-tools/latest/bin` directory:
```bash
cd C:\Users\HP\AppData\Local\Android\Sdk\cmdline-tools\latest\bin
```
- Run the following:
```bash
sdkmanager.bat --licenses
```
> Accept all licenses.

---

## For Dependency Issues
### Check and Align Dependencies
```bash
npx expo-doctor
```
> This shows which versions are expected.

```bash
npx expo install
```
> Installs all correct versions of dependencies for your Expo SDK.

### Clean and Prebuild Again
```bash
npx expo prebuild --clean
```

---

### Final Step: Run the App Again
```bash
npx expo run:android
```
> If you get the error:
```
INSTALL_FAILED_UPDATE_INCOMPATIBLE
```
> It means a conflicting version of the app is on your device.

**Solution:**
Uninstall any existing version of the app from your device, then run the command again.

---

You're now fully ejected from Expo Go and running a custom native Android build!

**To build your production version of the app without using this command**:

```bash
eas build --profile production --platform development
```

navigate to the android folder in your app and run:

```bash
gradlew bundleRelease
```
[Subscribe to my Youtube channel](https://www.youtube.com/@tinktechy)
