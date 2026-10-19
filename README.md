# The Network

A Flutter and Firebase app that gives university students one place to talk, share study material and take part in campus life. Students join chat groups for their university and department, download shared summaries, enter competitions, vote in polls, and send suggestions or complaints to administrators.

Graduation project for the Bachelor of Information Technology at the Islamic University of Gaza (January 2025), built by a team of four students.

<!--
Screenshots: add 4 to 6 phone screenshots (login, universities, group chat,
competitions, summaries, voting), for example:
<p float="left">
  <img src="screenshots/universities.png" width="200" />
  <img src="screenshots/chat.png" width="200" />
  <img src="screenshots/competitions.png" width="200" />
  <img src="screenshots/voting.png" width="200" />
</p>
A short demo video is in `Rsc. F. P/`; converting it to a GIF and placing it here
works well.
-->

## Features

- Register, log in and reset a forgotten password with Firebase Authentication
- Browse universities and join real-time chat groups for each university and department (Firebase Realtime Database)
- Upload study summaries from the device to Firebase Storage and download files shared by others
- Competition feed with likes and comments, plus a details screen for each competition
- Polls where each user can vote once, with votes tracked in Firestore
- Suggestion and complaint forms that send feedback to the administrators
- User profile with photo upload
- Custom theme system (text, buttons, inputs, app bar, chips, bottom sheets) defined in one place

## Tech stack

| Area | Tools |
|---|---|
| App | Flutter, Dart |
| Authentication | Firebase Auth |
| Data | Cloud Firestore (competitions, votes, suggestions, complaints, users), Firebase Realtime Database (group chat) |
| Files | Firebase Storage, file_picker, image_picker, dio (file downloads) |
| Local storage | shared_preferences |

## Project structure

```
lib/
├── main.dart, app.dart        # Firebase init and MaterialApp
├── core/
│   ├── constants/             # colors, image paths
│   └── theme/                 # light and dark themes, per-widget theme files
├── model/                     # competition, vote, suggestion, complaint
├── navigation/                # named routes and route generator
├── singleton/                 # shared preferences manager
└── screens/
    ├── authintication/        # login, register, forgot password
    ├── universities/          # university list
    ├── conversation/          # department group chat
    ├── summaries/             # file upload and download
    ├── competitions/          # feed, card, details
    ├── others/                # voting, suggestions, complaints
    └── profile/
```

The `Rsc. F. P/` folder holds the project report, the Figma design file and a demo recording.

## Getting started

1. Clone the repository and install packages:
   ```sh
   git clone https://github.com/mosabmoammar/graduation_project_the_network.git
   cd graduation_project_the_network
   flutter pub get
   ```
2. Create a Firebase project and enable Authentication (email and password), Cloud Firestore, Realtime Database and Storage.
3. Connect the app to your project (this regenerates `lib/firebase_options.dart`):
   ```sh
   flutterfire configure
   ```
4. Run on an Android device or emulator:
   ```sh
   flutter run
   ```
