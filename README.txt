DISCIPLINE — ONLINE + CLOUD VERSION
===================================

This version is designed for:
- online publishing
- sign-in from any phone/laptop
- private cloud data per account
- no Supabase
- no Next.js
- plain HTML/CSS/JavaScript

IMPORTANT
---------
A website that syncs your data between devices needs an online database and an account. This build uses Firebase Authentication + Cloud Firestore instead of Supabase.

1) CREATE FIREBASE PROJECT
--------------------------
Go to the Firebase Console and create a project.
Then add a Web App to the project.
Firebase will give you a firebaseConfig object.

2) ENABLE EMAIL/PASSWORD LOGIN
------------------------------
Firebase Console -> Authentication -> Sign-in method -> Email/Password -> Enable.

3) CREATE FIRESTORE
-------------------
Firebase Console -> Firestore Database -> Create database.
Choose the production/security-rules option if offered.
Then use the rules in firebase.rules.

4) ADD YOUR FIREBASE CONFIG
---------------------------
Open index.html and find:

const firebaseConfig={apiKey:"PASTE_YOUR_FIREBASE_API_KEY", ... };

Replace the placeholder values with the config from your Firebase Web App.
Do NOT put any Firebase Admin/service-account private key in the website.
The normal Firebase Web App config is intended to be used by the browser; Firestore Security Rules protect each user's data.

5) PUBLISH
----------
Upload these files to any static website host:
- index.html
- manifest.webmanifest

firebase.rules is for your Firebase Firestore rules; do not rely on it being served by the website.

6) FIRESTORE RULES
------------------
Copy firebase.rules into Firebase Console -> Firestore Database -> Rules, then Publish.

The rule makes /users/USER_ID readable/writable only by the signed-in user whose Firebase UID equals USER_ID.

FEATURES
--------
- Dashboard
- Custom habits
- Habit completion history
- Goals + progress
- Custom challenge duration / no-end challenge
- Suggested Student / Discipline / Reading templates
- Focus timer
- Streaks
- 14-day calendar
- Line chart
- Donut chart
- Treemap-style effort view
- Bullet target chart
- Daily Anthem fixed by calendar day
- Discipline Quote independent of Anthem
- Daily important task
- Daily reflection
- Light/dark/system mode
- Accent colors
- Profile
- Backup/export JSON
- Import/restore JSON
- Private cloud sync across signed-in devices
- Mobile-first UI

NOTE ABOUT "CHANGE FROM ANYWHERE"
----------------------------------
You can change the app's code from wherever you manage the published files, but changing the app itself is different from changing your personal data. Your personal goals/habits/settings sync through Firestore.
