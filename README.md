# Smart Health Connect - Healthcare Management Android App

A comprehensive healthcare management Android application built with Java, Firebase Authentication, and Firebase Realtime Database.

## 🎯 Project Overview

Smart Health Connect integrates multiple healthcare services into a single digital platform, providing users with easy access to:
- Lab Test Booking
- Doctor Appointments
- Health Articles
- Order Management
- Profile & Settings

## 🛠️ Technology Stack

- **Language**: Java
- **Architecture**: MVP (Model-View-Presenter)
- **Backend**: Firebase Authentication + Firebase Realtime Database
- **UI Framework**: Material Design 3
- **Minimum SDK**: 24 (Android 7.0)
- **Target SDK**: 34 (Android 14)

## 📋 Prerequisites

1. Android Studio Hedgehog or later
2. Java JDK 17
3. Firebase project setup:
   - Create a Firebase project at [Firebase Console](https://console.firebase.google.com/)
   - Enable Authentication (Email/Password)
   - Enable Realtime Database
   - Download `google-services.json` and place it in `app/` directory

## 🚀 Setup Instructions

1. **Clone/Download the project**
   ```bash
   cd SmartHealthConnect_Rebuild
   ```

2. **Replace Firebase Configuration**
   - Open Firebase Console
   - Create a new project or use existing
   - Add Android app with package name: `com.smarthealthconnect`
   - Download `google-services.json`
   - Replace the template file in `app/google-services.json`

3. **Configure Firebase Database Rules**
   ```json
   {
     "rules": {
       "users": {
         "$uid": {
           ".read": "$uid === auth.uid",
           ".write": "$uid === auth.uid"
         }
       },
       "doctors": {
         ".read": true,
         ".write": false
       },
       "labtests": {
         ".read": true,
         ".write": false
       },
       "articles": {
         ".read": true,
         ".write": false
       },
       "appointments": {
         ".read": "auth != null",
         ".write": "auth != null"
       },
       "orders": {
         ".read": "auth != null",
         ".write": "auth != null"
       }
     }
   }
   ```

4. **Initialize Sample Data**
   
   You'll need to add sample data to Firebase Realtime Database:
   
   - **Doctors**: Add doctor entries under `/doctors`
   - **Lab Tests**: Add test packages under `/labtests`
   - **Articles**: Add health articles under `/articles`

5. **Gradle Sync**
   - Open project in Android Studio
   - Click "Sync Now" when prompted
   - Wait for dependencies to download

6. **Build and Run**
   - Connect Android device or start emulator
   - Click "Run" button or press Shift+F10

## 📁 Project Structure

```
SmartHealthConnect_Rebuild/
├── app/
│   ├── src/main/java/com/smarthealthconnect/
│   │   ├── activities/          # All activity classes
│   │   ├── adapters/            # RecyclerView adapters
│   │   ├── firebase/            # Firebase helper classes
│   │   ├── model/               # Data model classes
│   │   └── utils/               # Utility classes
│   ├── res/
│   │   ├── layout/              # XML layouts
│   │   ├── values/              # Strings, colors, themes
│   │   └── menu/                # Menu resources
│   ├── google-services.json     # Firebase config (replace with your own)
│   └── build.gradle
├── build.gradle
└── settings.gradle
```

## 🔑 Key Features

### Authentication
- Email/Password login
- User registration
- Password reset via email
- Session management

### Dashboard
- Material Design 3 UI
- Card-based navigation
- Quick access to all modules

### Lab Tests
- Browse available test packages
- Add to cart
- Checkout and booking

### Find Doctor
- Browse doctors by specialization
- View doctor details
- Book appointments
- Email and location integration

### Health Articles
- Read health articles
- Detailed article view with scroll

### Orders & History
- View booking history
- Track order status

### Profile & Settings
- Edit user profile
- Notification preferences toggle

## 🧪 Sample Data Structure

### Doctor Example
```json
{
  "doctors": {
    "doc001": {
      "doctorId": "doc001",
      "name": "Dr. John Smith",
      "specialization": "Cardiology",
      "fee": 500,
      "timings": "10 AM - 5 PM",
      "clinic": "CityCare Hospital",
      "email": "johnsmith@gmail.com",
      "phone": "9876543210",
      "address": "123 Main St, City",
      "rating": 4.5
    }
  }
}
```

### Lab Test Example
```json
{
  "labtests": {
    "test001": {
      "testId": "test001",
      "name": "Complete Blood Count",
      "cost": 400,
      "duration": "1 hour",
      "instructions": "Fasting for 8 hours required",
      "description": "Comprehensive blood analysis"
    }
  }
}
```

## 🐛 Troubleshooting

1. **Build Errors**
   - Ensure Gradle sync completed successfully
   - Check that `google-services.json` is in correct location
   - Verify Java version is 17

2. **Firebase Connection Issues**
   - Verify internet connection
   - Check Firebase project settings
   - Ensure Realtime Database rules are configured

3. **Login/Signup Errors**
   - Verify Firebase Authentication is enabled
   - Check email format
   - Ensure password is at least 6 characters

## 👥 Developers

- **K. Hailey**
- **GURRAMPATI LAVANYA** 

## 📝 License

This project is developed for educational purposes.

## 🔄 Version History

- **v1.0** - Initial release with all core features

---

**Note**: Remember to replace the template `google-services.json` with your actual Firebase configuration file before building the app.
