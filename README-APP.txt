VERIFIED EXAM — CROSS-PLATFORM APP SOURCE

This is one Firebase-connected app codebase packaged for:
- Android phones/tablets (native Android project)
- iPhone/iPad (native iOS project; build/signing requires a Mac with Xcode)
- Windows, macOS, Chromebook, and Linux (open the same hosted web app in a browser)

It is a native WebView wrapper around the existing exam web app. It is not a
replacement for Safe Exam Browser and does not reliably lock a device against
leaving the app. Do not represent browser tab/blur checks as device lockdown.

ANDROID BUILD (Windows with Android Studio installed)
1. Install Android Studio and its Android SDK.
2. Open a terminal in this folder and run: npm install
3. Run: npx cap sync android
4. Run: npx cap open android
5. In Android Studio, connect a phone or choose an emulator, then press Run.
   To distribute, build a signed Android App Bundle (AAB) in Android Studio.

IOS BUILD
1. Copy this folder to a Mac with current Xcode installed.
2. Run: npm install
3. Run: npx cap sync ios
4. Run: npx cap open ios
5. Choose a development team/signing profile in Xcode and run on a device.
   App Store/TestFlight publishing requires an Apple Developer account.

WEB/COMPUTER ACCESS
From this project folder, deploy the web version with: firebase deploy --only hosting.
The included Firebase Hosting config targets www/. The resulting
HTTPS link works in modern desktop and mobile browsers and can be used where
native installation is not available.

FIREBASE
The app uses the existing Firebase configuration embedded in www/index.html.
Firebase Authentication and Firestore rules must be configured and published.
Every user must have a Firebase account. The native wrapper does not make the
client-side exam answer key or grading trusted; server-side exam delivery and
grading are still required before high-stakes exams.

CAMERA/MICROPHONE
The web app requests camera/microphone through browser APIs. Verify permission
prompts on each target device before using face capture or proctor video.
This face capture is a demonstration, not biometric identity verification.
