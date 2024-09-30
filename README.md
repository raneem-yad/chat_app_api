
# Chat Training App

This is a simple chat application built using **Flutter** and **Firebase SDK** for user authentication, state management, and push notifications. The project is intended for learning purposes and demonstrates how to integrate Firebase services in a Flutter application.

## Features
- User authentication using **Firebase Authentication** (Email/Password, Google sign-in, etc.).
- Real-time chat messaging using **Cloud Firestore**.
- **Push notifications** for new messages using **Firebase Cloud Messaging (FCM)**.
- State management using **Provider**.
- Clean and modular code structure for easy understanding and extension.

## Requirements
- Flutter SDK: Ensure you have Flutter installed on your machine. You can install it from [Flutter Install](https://flutter.dev/docs/get-started/install).
- Firebase Project: A Firebase project is required to enable services like authentication, Firestore, and messaging.
- Android Studio / Visual Studio Code for development.

## Getting Started

### 1. Clone the Repository
```bash
git clone https://github.com/your_username/chat_training_app.git
cd chat_training_app
```

### 2. Set up Firebase
- Go to the [Firebase Console](https://console.firebase.google.com/), create a project, and register your app.
- Download the `google-services.json` for Android and `GoogleService-Info.plist` for iOS.
- Place the `google-services.json` in the `android/app` directory and `GoogleService-Info.plist` in the `ios/Runner` directory.
- Enable **Firestore**, **Firebase Authentication**, and **Firebase Cloud Messaging (FCM)** in your Firebase console.

### 3. Install Dependencies
Run the following command to install all required dependencies:
```bash
flutter pub get
```

### 4. Running the Application
Run the app on an emulator or a connected device:
```bash
flutter run
```

## Project Structure

```plaintext
lib/
├── main.dart               # Entry point of the application
├── services/               # Firebase services (Auth, Firestore, etc.)
├── models/                 # Data models for the app
├── providers/              # State management (Provider)
├── screens/                # All the app screens (ChatScreen, AuthScreen, etc.)
├── widgets/                # Custom widgets used throughout the app
└── utils/                  # Helper functions and utilities
```

### Key Files
- **main.dart**: Initializes Firebase and sets up the routing and state management.
- **auth_service.dart**: Manages user authentication using Firebase.
- **chat_service.dart**: Handles real-time chat using Firestore.
- **notification_service.dart**: Manages push notifications using Firebase Cloud Messaging.
- **chat_screen.dart**: Displays the chat UI and messages.
- **auth_screen.dart**: Provides user login and sign-up functionality.

## Firebase Setup

### Authentication
- Enable Email/Password and Google authentication from the Firebase console under **Authentication**.

### Firestore
- Set up a **Firestore** database to store chat messages.
- Use the following basic structure for storing messages:
  ```plaintext
  messages/
    - messageId
      - senderId: "userId"
      - text: "Hello World"
      - timestamp: timestamp
  ```

### Firebase Cloud Messaging (FCM)
- Enable **Cloud Messaging** and integrate FCM for push notifications.
- Ensure that you configure the FCM server key in the Firebase console to send notifications when new messages are received.

## State Management
The app uses the **Provider** package for state management. All the app states (e.g., user authentication, chat messages) are managed through `ChangeNotifier` and consumed by the UI using the `Consumer` widget.

## Push Notifications
Push notifications are implemented using **Firebase Cloud Messaging (FCM)**. When a new message is sent, an FCM notification is triggered and displayed to the user. You will need to handle notification permissions for iOS.

## Dependencies

Here are some of the key dependencies used in the project:

```yaml
dependencies:
  flutter:
    sdk: flutter
  firebase_core: ^2.0.0
  firebase_auth: ^4.0.0
  cloud_firestore: ^4.0.0
  firebase_messaging: ^14.0.0
  provider: ^6.0.0
```

To see the full list of dependencies, check the `pubspec.yaml` file.

## Future Improvements
- Add user typing indicators.
- Implement group chats and media sharing.
- Improve message search functionality.
- Implement better error handling and validation.

## Contributing
Feel free to fork this repository, improve the app, and create a pull request for any new features or bug fixes.

