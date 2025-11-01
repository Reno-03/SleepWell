<div align="center">

  <img src="assets/images/icon.png" alt="SleepWell Logo" width="200"/>

</div>

# SleepWell

A comprehensive cross-platform sleep tracking mobile application designed to help users monitor their sleep patterns, set alarms, track weather conditions, and analyze factors affecting sleep quality. Built with Flutter, this application provides an intuitive interface for managing your sleep health with detailed statistics, personalized recommendations, and seamless alarm functionality.

## 📸 Demo

<div align="center">
  <img src="/screenshots/demo.gif" height="400"/>
</div>

## 🌟 Features

- **User Authentication**: Secure account system for personalized sleep tracking and data management

- **Sleep Monitoring**: Record and track your sleep and wake times with comprehensive history

- **Sleep Statistics**: Detailed analytics including:
  - Total sleep time
  - Average sleep duration
  - Longest and shortest sleep sessions
  - Sleep session count
  - Visual data representation

- **Alarm System**: 
  - Set custom alarms with reliable notifications
  - Background alarm support using Android Alarm Manager
  - Audio playback with custom alarm sounds
  - Exact alarm scheduling for precise wake times

- **Weather Integration**: 
  - Real-time weather data based on your location
  - Temperature and weather condition display
  - Weather-based sleep recommendations
  - Location-based weather services using Geolocator

- **Sleep Factors Tracking**: 
  - Identify and record factors that affect your sleep quality
  - Personalized recommendations based on tracked factors
  - Sleep quality analysis

- **Local Data Storage**: 
  - SQLite database for offline data persistence
  - Secure user data management
  - Fast and reliable local storage

- **Modern UI/UX**: 
  - Clean and intuitive Material Design interface
  - Lottie animations for enhanced user experience
  - Bottom navigation for easy access to all features
  - Responsive design for various screen sizes

## 🛠️ Technology Stack

- **Flutter** - Cross-platform UI framework
- **Dart 3.4.1+** - Programming language
- **SQLite** - Local database for data persistence
- **Android Alarm Manager Plus** - Reliable alarm scheduling
- **Flutter Local Notifications** - Local notification system
- **Geolocator** - Location services for weather
- **Weather API** - Real-time weather data integration
- **Lottie** - Beautiful animations
- **Shared Preferences** - Lightweight key-value storage
- **Audioplayers** - Audio playback for alarms
- **Permission Handler** - Runtime permission management

## 📋 Prerequisites

Before running this application, ensure you have:

- **Flutter SDK** (latest stable version) installed
- **Dart SDK** (comes with Flutter)
- **Android Studio** or **VS Code** with Flutter extensions
- **Android SDK** (for Android development)
- **Xcode** (for iOS development, macOS only)
- **OpenWeather API Key** (for weather functionality)
- **Git** for cloning the repository

### Required Permissions

The app requires the following permissions:
- Location (for weather services)
- Notifications (for alarms and reminders)
- Schedule Exact Alarm (for precise alarm scheduling)
- Internet (for weather API calls)
- Vibrate (for alarm notifications)

## 🚀 Installation

1. **Clone the repository**

   ```bash
   git clone <repository-url>
   cd SleepWell
   ```

2. **Install Flutter dependencies**

   ```bash
   flutter pub get
   ```

3. **Configure API Keys**

   - Obtain an OpenWeather API key from [OpenWeatherMap](https://openweathermap.org/api)
   - Add your API key to `lib/consts.dart` or create an environment configuration file:
     ```dart
     const String OPENWEATHER_API_KEY = 'your_api_key_here';
     ```

4. **Run the application**

   For Android:
   ```bash
   flutter run
   ```

   For iOS (macOS only):
   ```bash
   flutter run -d ios
   ```

   For Web:
   ```bash
   flutter run -d chrome
   ```

5. **Build release APK** (Android)

   ```bash
   flutter build apk --release
   ```

## 📖 Usage

### Getting Started

1. **Launch the app** - You'll be greeted with an introduction screen
2. **Create an account** - Sign up with your credentials or log in to an existing account
3. **Welcome screen** - Complete the initial setup
4. **Select Sleep Factors** - Choose factors that affect your sleep quality

### Main Interface

The app features a bottom navigation bar with four main sections:

- **Statistics Tab** 📊
  - View comprehensive sleep statistics
  - Track sleep patterns over time
  - Monitor average sleep duration
  - View longest and shortest sleep sessions

- **Clock Tab** ⏰
  - Set wake-up alarms
  - Record sleep and wake times
  - View sleep history
  - Manage alarm settings

- **Weather Tab** ☁️
  - Check current weather conditions
  - View temperature and weather descriptions
  - Get location-based weather data
  - Understand how weather affects sleep

- **Information Tab** ℹ️
  - Learn about the app
  - Access help and support
  - View app version and details

### Additional Features

- **Drawer Menu**: Access from the top-left hamburger icon
  - About App
  - Factors Checklist
  - Logout

- **Sleep Recording**: 
  - Tap on the clock to record your sleep time
  - Record wake time when you wake up
  - All data is automatically saved to your local database

- **Alarm Management**:
  - Set alarms with custom times
  - Alarms work in the background
  - Receive notifications even when the app is closed

## 🗂️ Project Structure

```
SleepWell/
├── android/                 # Android-specific files
│   ├── app/
│   │   └── src/
│   │       └── main/
│   │           └── AndroidManifest.xml
│   └── build.gradle
├── ios/                     # iOS-specific files
├── lib/
│   ├── assets/              # Lottie animations and images
│   │   ├── flutter_icon.png
│   │   ├── hour_glass.json
│   │   ├── jumping_location.json
│   │   ├── light_bulb.json
│   │   ├── sleeping_emoji.json
│   │   └── sqlite_icon.png
│   ├── JsonModels/          # Data models
│   │   ├── sleeping_factor.dart
│   │   ├── users_sleeping_factor.dart
│   │   └── users.dart
│   ├── screens/             # UI screens
│   │   ├── about_app_page.dart
│   │   ├── factors_page.dart
│   │   ├── intro_page.dart
│   │   ├── login.dart
│   │   ├── main_interface.dart
│   │   ├── signup.dart
│   │   ├── welcome_page.dart
│   │   └── navigation_screens/
│   │       ├── clock_page.dart
│   │       ├── clock_view.dart
│   │       ├── info_page.dart
│   │       ├── statistics_page.dart
│   │       └── weather_page.dart
│   ├── SQLite/              # Database management
│   │   ├── sqlite_monitor.dart
│   │   ├── sqlite_sleep_facors.dart
│   │   └── sqlite_user.dart
│   ├── consts.dart          # Constants and configuration
│   └── main.dart            # Application entry point
├── assets/                   # Static assets
│   ├── alarm.mp3           # Alarm sound
│   ├── images/
│   │   └── icon.png        # App icon
│   └── [1-14].png          # Weather icons
├── pubspec.yaml             # Flutter dependencies
├── analysis_options.yaml    # Dart analyzer options
└── README.md
```

## 🗄️ Database Schema

The application uses SQLite for local data storage with the following main components:

- **Users Table**: Stores user account information and credentials
- **Sleep Monitor Table**: Tracks sleep and wake times, sleep sessions
- **Sleep Factors Table**: Stores factors affecting sleep quality
- **User Sleep Factors Table**: Links users to their sleep factors

All data is stored locally on the device, ensuring privacy and offline functionality.

## 🔧 Configuration

### API Keys

To use the weather feature, you need to configure your OpenWeather API key in `lib/consts.dart`:

```dart
const String OPENWEATHER_API_KEY = 'your_openweather_api_key';
```

### App Permissions

The app automatically requests necessary permissions on first launch:
- Location permission (for weather)
- Notification permission (for alarms)
- Exact alarm scheduling permission (for precise alarms)

## 📝 Notes

- This application was developed as a comprehensive sleep tracking solution
- All user data is stored locally using SQLite - no data is sent to external servers (except weather API calls)
- The app requires location permissions for weather features but respects user privacy
- Alarm functionality works reliably in the background using Android Alarm Manager Plus
- The application has been validated for performance and functionality

## 🐛 Troubleshooting

### Common Issues

1. **Weather not loading**: 
   - Ensure you have a valid OpenWeather API key
   - Check that location permissions are granted
   - Verify internet connectivity

2. **Alarm not working**:
   - Grant notification permissions when prompted
   - Grant "Schedule Exact Alarm" permission
   - Ensure the app is not force-stopped

3. **Database errors**:
   - Clear app data and reinstall if database becomes corrupted
   - Ensure sufficient storage space on device

## 🚧 Future Enhancements

Potential features for future versions:
- Cloud synchronization for sleep data
- Advanced sleep analysis with AI insights
- Integration with fitness trackers
- Sleep quality scoring algorithm
- Customizable alarm sounds
- Sleep goal setting and tracking

## 👤 Author

**Reno-03**

---

## 📄 License

This project is developed for educational and personal use. All rights reserved.

## 🙏 Acknowledgments

- Flutter team for the amazing framework
- OpenWeatherMap for weather API services
- All contributors to the open-source packages used in this project

---

<div align="center">

**Sleep Well, Live Well** 😴✨

</div>
