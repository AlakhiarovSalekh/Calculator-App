# Cross-Platform Calculator App — React, React Native & Electron

[![Stars](https://img.shields.io/github/stars/AlakhiarovSalekh/Calculator-App?style=social)](https://github.com/AlakhiarovSalekh/Calculator-App/stargazers)

![Platform](https://img.shields.io/badge/Platform-Web%20%7C%20Desktop%20%7C%20Mobile-blue)
![React](https://img.shields.io/badge/React-Framework-61DAFB)
![React Native](https://img.shields.io/badge/React%20Native-Mobile-61DAFB)
![JavaScript](https://img.shields.io/badge/JavaScript-ES6-F7DF1E)
![License](https://img.shields.io/badge/License-MIT-green)

A Modern Cross-Platform calculator application built with React and React Native technologies.

This project demonstrates how a single codebase can be used to create applications for multiple platforms including Web, Desktop, Android, and iOS while maintaining a consistent user experience.

## Why this project

This repository explores a shared application architecture across web, desktop, Android, and iOS. The interesting part is not only the calculator UI, but how logic is reused while rendering remains platform-aware.

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

Screenshots are not currently included in this repository. The previous README referenced image files that are not present in the current repository tree.

## Libraries/tools

This project uses libraries and tools like:
- es6 syntax and [babel](https://babeljs.io)
- [react](https://facebook.github.io/react) for the Website App and Desktop App,
- [react-native](https://facebook.github.io/react-native) for the iOS & Android Apps
- [NW](http://nwjs.io) to package the Desktop App
- [Electron](http://electron.atom.io) to package the Desktop App
- [flux](https://facebook.github.io/flux) to organize the data flow management
- [css-loader](https://github.com/webpack/css-loader) to integrate the styles in the builds
- [grunt](http://gruntjs.com) to create the builds
- [webpack](https://webpack.github.io) to help during the development phase with hot reloading

## Basic philosophy

All the code is contained in the `src` directory, especially the 3 main entry files that are used for the builds:
- `index.ios.js` & `index.android.js` are the ones used to build the iOS & Android Apps
- `index.js` is the one used to build the Website App and Desktop App as the code is strictly the same.

### Flux architecture actions/stores

The [Flux](https://facebook.github.io/flux) architecture is fully shared across all builds. This means that the logic and data-management code is implemented once and reused across platforms. This allows us to have an easy tests suite as well and to ensure that our code is working properly on all the devices.

### Components

The real interest of the project is in how the components are structured to share most of their logic while redefining only what is specific to each device.

Basically, every component has a main `Class` which inherits a base `Class` containing all the logic. Then, the main component imports a different Render function selected during the build. The file extension `.ios.js`, `.android.js` or `.js` is used by the build tool to import only the right file.

The `.native.js` files contain code that is shared between both mobile platforms (iOS & Android). Currently, the `.ios.js` and `.android.js` files compose this `.native.js` file since all code is shared right now. However, if a component needed to be different for platform specific reasons, that code would be included in the corresponding platform specific files.

At the end, every component is defined by 6 files. If we look at the screen component, here is its structure.

```
Screen.js
├── ScreenBase.js
├── ScreenRender.ios.js (specific to iOS build
├── ScreenRender.android.js (specific to Android build)
├── ScreenRender.native.js (shared mobile app code - iOS & Android)
└── ScreenRender.js (used during Website and Desktop build)
```

And here is the main `Class` file which composes the files.

```js
'use strict';

import Base from './ScreenBase';
import Render from './ScreenRender';

export default class Screen extends Base {
  constructor (props) {
    super(props);
  }

  render () {
    return Render.call(this, this.props, this.state);
  }
}
```

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
git clone https://github.com/AlakhiarovSalekh/Calculator-App.git
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

## Contributing

Bug fixes, documentation improvements, portability fixes, and focused enhancements are welcome through issues and pull requests.

## Repository

https://github.com/AlakhiarovSalekh/Calculator-App

> If this project is useful to you, consider starring the repository. It helps you find it again and helps other developers discover the project.

## More Projects by Salekh

- [50 Projects — HTML, CSS & JavaScript](https://github.com/AlakhiarovSalekh/50-Projects-HTML-CSS-JavaScript) — 50 focused frontend practice projects.
- [Weather App](https://github.com/AlakhiarovSalekh/Weather-App) — native Android weather application.
- [Notes App](https://github.com/AlakhiarovSalekh/Notes-App) — modern Android notes app with Jetpack Compose.

## Author

**Alakhiarov Salekh**

GitHub: https://github.com/AlakhiarovSalekh

## License

MIT License
