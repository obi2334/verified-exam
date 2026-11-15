# Verified Exam

A Firebase-connected exam and proctoring app with web, PWA, Android, and iOS packaging.

## Repository contents

- `index.html` — browser entry point.
- `www/` — web assets used by Firebase Hosting and Capacitor.
- `firestore.rules` — Firestore access rules.
- `verified-exam-source.zip` — full project source, including the Android and iOS projects. Extract this archive to see the full folder structure. Dependencies and Firebase build cache are excluded.
- `README-APP.txt` — platform build and Firebase notes from the project.

## Run and build

Install Node.js and run `npm install` in the project folder. For the web version, configure Firebase Hosting and deploy with `firebase deploy --only hosting`.

For Android, install Android Studio and the Android SDK, then run `npx cap sync android` and `npx cap open android`. For iOS, use a Mac with Xcode and run `npx cap sync ios` and `npx cap open ios`, then configure signing in Xcode.

## Security and readiness

Review the Firebase setup and Firestore rules before connecting a project. Never add service-account keys, private credentials, student data, or real exam records to this public repository.

The browser currently contains exam delivery and grading logic. Face capture is a demonstration, not identity verification, and browser focus checks do not lock a device. Do not use this version for high-stakes exams until trusted server-side exam delivery and grading are implemented and validated.
