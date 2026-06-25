# OrthoView

<p align="center">
  <img src="app/src/main/logo-playstore.png" alt="OrthoView logo" width="120">
</p>

OrthoView is a native Android app for recording, organizing, and reviewing short orthodontic progress videos (front view / side view) per patient. Each patient gets a dedicated folder, making it easy to capture a consistent set of angles over time and look back at recordings later.

## Features

- **Guided video capture** — record a front-view and a side-view clip directly through the device camera, automatically named with a timestamp.
- **Per-patient folders** — videos are grouped by a folder name (e.g. patient name) entered before recording.
- **Browse & search** — search through existing folders and jump straight to the videos inside.
- **Playback** — open any recorded clip in the device's video player via a `FileProvider`.
- **Delete** — remove single videos or entire folders, with a confirmation prompt.
- **Built-in tutorial** — an in-app video walks new users through how to use the app.

## Tech stack

- Java
- Android SDK (`minSdk` 24, `targetSdk`/`compileSdk` 31)
- AndroidX (AppCompat, ConstraintLayout, Material Components)
- `FileProvider` for secure access to recorded videos
- Gradle (Groovy DSL)

## Project structure

```
app/src/main/java/com/example/orthoview/
├── StartActivity.java          # Landing screen: open recorder, browse storage, watch tutorial
├── MainActivity.java           # Recording screen: capture front/side videos, manage folders
└── VideoTutorialActivity.java  # Plays the bundled tutorial video
```

## Permissions

| Permission | Reason |
| --- | --- |
| `CAMERA` | Required to record video |
| `WRITE_EXTERNAL_STORAGE` / `READ_EXTERNAL_STORAGE` | Required to save and read recorded videos in app-specific storage |

All recordings are stored in the app's own external files directory (`getExternalFilesDir`), not in shared/public storage.

## Getting started

### Prerequisites

- Android Studio (Giraffe or newer recommended)
- Android SDK Platform 31
- A device or emulator with a camera

### Build & run

```bash
git clone https://github.com/niklas7400/orthoview.git
cd orthoview
./gradlew installDebug
```

Or simply open the project in Android Studio and run the `app` configuration on a connected device/emulator.

## License

This project is licensed under the [MIT License](LICENSE).
