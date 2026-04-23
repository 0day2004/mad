# MAD Experiments – Viva Theory Guide

This README contains **theory notes for viva** for all experiment files present in this folder.

---

## Experiment 1: Installation and Configuration of Flutter Environment (Linux)

### Theory (for viva)
- Flutter is a UI toolkit by Google for building **cross-platform apps** from a single codebase.
- Flutter uses **Dart** language and a **widget-based architecture**.
- In Linux setup, required tools (Git, unzip, curl, etc.) support SDK download, extraction, and command-line workflows.
- Adding Flutter to `PATH` allows running commands like `flutter doctor` globally.
- `flutter doctor` is a diagnostic command that checks SDK, Android toolchain, browser/device support, and missing dependencies.
- `flutter create` generates a default project structure; `flutter run` builds and launches app on selected device.

### Key viva points
- Difference between **SDK installation** and **toolchain configuration**.
- Why `flutter doctor` is run multiple times (to verify fixes).
- Importance of accepting Android licenses for emulator/device builds.

---

## Experiment 2: Student ID Card UI using Flutter

### Theory (for viva)
- Flutter UI is built with nested widgets like `Scaffold`, `Container`, `Column`, `Text`, and `CircleAvatar`.
- `StatelessWidget` is suitable when UI does not change dynamically after build.
- `BoxDecoration` provides styling such as rounded corners, background colors, shadows, and borders.
- Layout and spacing are controlled through `SizedBox`, `Padding`, `Spacer`, and alignment properties.

### Key viva points
- Why this app uses `StatelessWidget` instead of `StatefulWidget`.
- How `Container` + `BoxDecoration` helps design card-like UI.
- Role of `CircleAvatar` and network image loading.

---

## Experiment 3: ListView UI using Flutter Layout Widgets

### Theory (for viva)
- `ListView.builder` creates list items lazily, so it is memory-efficient for dynamic/large lists.
- Layout composition combines `Column`, `Expanded`, `Row`, `Stack`, and `Positioned` to build complex cards.
- A list of maps (`List<Map<String, String>>`) acts as a lightweight local data source.
- `Expanded` ensures list takes remaining screen space while preserving top header content.

### Key viva points
- Difference between `ListView` and `ListView.builder`.
- Why `Stack` is used for profile avatar + status indicator.
- Benefits of separating data model and UI rendering logic.

---

## Experiment 4: Interactive Form using Flutter

### Theory (for viva)
- Interactive forms capture user input using `TextField` and `TextEditingController`.
- `Navigator.push()` enables screen transition while passing data (e.g., username).
- `StatefulWidget` manages mutable data like task list and current bottom navigation index.
- Modular screens (`DashboardPage`, `TaskPage`, `ProfilePage`) improve maintainability.
- Dialog-driven task creation demonstrates UI + state update cycle (`setState`).

### Key viva points
- Lifecycle and purpose of `TextEditingController`.
- Why task operations (`add/delete`) require `setState`.
- Difference between bottom navigation-based page switching vs route navigation.

---

## Experiment 5: Navigation and Routing in Flutter

### Theory (for viva)
- Flutter navigation is stack-based: each `Navigator.push()` adds a new route to stack.
- `MaterialPageRoute` maps a widget to a navigable screen.
- `Navigator.pushAndRemoveUntil()` can reset navigation history (useful for home/logout flows).
- Routing improves separation of concerns by isolating UI into screen-specific widgets.

### Key viva points
- Route stack concept (LIFO behavior).
- Difference: `push`, `pop`, and `pushAndRemoveUntil`.
- Why context is required for navigation.

---

## Experiment 6: Gesture Detection using Flutter

### Theory (for viva)
- Gestures represent user interactions such as tap, double tap, long press, and drag.
- `GestureDetector` listens to raw gesture events and triggers custom logic.
- `StatefulWidget` is used because lock state (`isLocked`) changes after tap.
- `AnimatedContainer` provides implicit animation when properties (color/decoration) change.

### Key viva points
- Difference between `GestureDetector` and `InkWell`.
- Why UI updates happen inside `setState`.
- How implicit animations improve UX without complex animation controllers.

---

## Experiment 7: Firebase Authentication using Flutter (FlutLab)

### Theory (for viva)
- Firebase Authentication is a Backend-as-a-Service module for secure identity management.
- Email/Password auth validates credentials against Firebase-managed user records.
- `firebase_core` initializes Firebase app; `firebase_auth` performs sign-in operations.
- Android app registration and `google-services.json` connect app package to Firebase project.

### Key viva points
- Why Firebase app initialization is mandatory before auth calls.
- Difference between authentication (identity) and authorization (permissions).
- Importance of package name matching during Firebase setup.

---

## Experiment 7.1: Firebase Authentication using Flutter (VS Code)

### Theory (for viva)
- This is a practical VS Code workflow of Firebase auth with local Flutter project tooling.
- Build files (`build.gradle`) integrate Google services plugin for Android Firebase support.
- Login flow includes async auth call, exception handling, and success navigation to home screen.
- `ScaffoldMessenger` provides user feedback (e.g., login failed).

### Key viva points
- Why async/await is used with network-based auth calls.
- Need for proper error handling in authentication.
- Difference between editor-based coding flow and cloud IDE flow.

---

## Experiment 8: Progressive Web App (PWA) using Flutter

### Theory (for viva)
- A PWA is a web app that can behave like an installable app on desktop/mobile.
- `manifest.json` defines app metadata (name, icons, theme, display mode).
- Service workers enable caching and offline capabilities (generated during Flutter web build).
- `display: standalone` allows app-like launch experience without browser chrome.
- Hosting with a static server is required to test installability reliably.

### Key viva points
- Conditions for “Add to Home Screen” (HTTPS/localhost, manifest, service worker).
- Role of `flutter build web` in generating production-ready web assets.
- Difference between normal website and PWA behavior.

---

## Experiment 10: Google Lighthouse PWA Analysis

### Theory (for viva)
- Lighthouse is an automated auditing tool built into Chrome DevTools.
- It evaluates categories: Performance, Accessibility, Best Practices, SEO, and PWA.
- Scores and diagnostics identify bottlenecks such as render-blocking resources, image issues, and missing metadata.
- PWA audit checks installability and service worker-related criteria.

### Key viva points
- Why Lighthouse is used during optimization and quality assurance.
- Meaning of each category score at a high level.
- How audit suggestions map to practical code/web improvements.

---

## Experiment 11: Deploy eCommerce PWA on GitHub Pages

### Theory (for viva)
- Deployment is the process of publishing build artifacts so users can access the app online.
- Flutter web output (`build/web`) contains static files suitable for GitHub Pages hosting.
- `--base-href` is important when app is served from a repository subpath instead of root domain.
- Git/GitHub workflow (`init`, commit, push) enables version-controlled deployment.
- GitHub Pages serves static content directly from selected branch/folder.

### Key viva points
- Why base path configuration matters for routing/assets.
- Difference between development run and production deployment.
- Benefits of static hosting for PWAs (simple, low-cost, globally accessible).

---

## Quick Revision Tips

- Focus on **core concepts**: widgets, state, navigation, Firebase auth flow, PWA fundamentals, and deployment.
- In viva, explain both **what** you implemented and **why** each tool/widget/config was used.
- Be ready to discuss one limitation and one improvement for each experiment.
