# Calculator App

![Platform](https://img.shields.io/badge/Platform-Web%20%7C%20Desktop%20%7C%20Mobile-blue)
![React](https://img.shields.io/badge/React-Framework-61DAFB)
![React Native](https://img.shields.io/badge/React%20Native-Mobile-61DAFB)
![JavaScript](https://img.shields.io/badge/JavaScript-ES6-F7DF1E)
![License](https://img.shields.io/badge/License-MIT-green)

A modern cross-platform calculator application built with React and React Native technologies.

This project demonstrates how a single codebase can be used to create applications for multiple platforms including Web, Desktop, Android, and iOS while maintaining a consistent user experience.

## Features

* Cross-platform architecture
* Modern calculator interface
* Shared codebase for all platforms
* Desktop application support
* Mobile application support
* Web application support
* Fast and lightweight performance
* Responsive design

## Screenshots

### Mobile Apps (iOS & Android)

![Mobile Apps](images/mobile-apps.png "Mobile Apps")

### Desktop Apps (NW & Electron)

![Desktop App](images/desktop-apps.png "Desktop App")

### Website App

![Website App](images/website-app.png "Website App")

## Technology Stack

### Frontend

* React
* React Native
* JavaScript (ES6)

### Build & Development Tools

* Babel
* Webpack
* Grunt

### Architecture

* Flux

## Project Structure

The application is designed around a shared architecture where the majority of the business logic is reused across all supported platforms.

Supported platforms:

* Web
* Desktop
* Android
* iOS

This approach minimizes code duplication and simplifies long-term maintenance.

## Installation

Clone the repository:

```bash
git clone https://github.com/SALEKH7/Calculator-App.git
```

Install dependencies:

```bash
npm install
```

## Running the Application

### Web Version

```bash
npm run build
npm run serve-web
```

### Desktop Version

Using Electron:

```bash
npm run serve-electron
```

Using NW:

```bash
npm run serve-nw
```

### Android Version

```bash
react-native run-android
```

### iOS Version

Open the iOS project in Xcode and run the application.

## Testing

Run all tests:

```bash
npm test
```

## Roadmap

Future improvements planned for the project:

* Scientific Calculator Mode
* Calculation History
* Dark Mode
* Currency Converter
* Additional Mathematical Functions
* Improved User Experience
* Enhanced Performance

## Repository

https://github.com/SALEKH7/Calculator-App

## Author

**Alakhiarov Salekh**

GitHub: https://github.com/SALEKH7

## License

MIT License