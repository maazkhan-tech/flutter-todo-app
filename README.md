# Flutter Todo App

A full-featured Todo application built with Flutter, using **Riverpod** for state management, **SQLite** for local persistence, and **GoRouter** for navigation. Supports task categories, date/time scheduling, completion tracking, and a polished themed UI.

---

## Features

-  **Create tasks** with title, notes, category, date & time
-  **Mark tasks** as complete / incomplete
-  **Delete tasks** with swipe or button
-  **Date-based filtering** — tap any date to view its tasks
-  **9 task categories** — Work, Personal, Health, Travel, Shopping, Education, Social, Home, Others
-  **SQLite local storage** — data persists across sessions
-  **Themed UI** — Indigo color scheme with Google Fonts (Dekko)
-  **GoRouter navigation** with clean route management
-  **Riverpod state management** with `ProviderScope`

---

## Tech Stack

| Technology | Usage |
|---|---|
| Flutter | UI Framework |
| Dart | Programming Language |
| `flutter_riverpod` | State management |
| `sqflite` | Local SQLite database |
| `go_router` | Declarative navigation |
| `flex_color_scheme` | Advanced theming |
| `google_fonts` | Custom typography (Dekko) |
| `font_awesome_flutter` | Icon set |
| `equatable` | Value equality for models |
| `intl` | Date & time formatting |
| `gap` | Spacing utility |

---

## Project Structure

```
lib/
├── main.dart                        # App entry point with ProviderScope
├── app/
│   └── app.dart                     # Root app widget
├── config/
│   ├── routes/
│   │   ├── app_routes.dart          # Route definitions
│   │   ├── routes.dart
│   │   ├── routes_location.dart     # Route path constants
│   │   └── routes_provider.dart     # GoRouter provider
│   └── theme/
│       └── app_theme.dart           # FlexColorScheme light theme
├── data/
│   ├── datasource/
│   │   └── task_datasource.dart     # SQLite CRUD operations
│   ├── models/
│   │   └── task.dart                # Task model (fromJson/toJson)
│   └── repositories/
│       ├── task_repository.dart     # Abstract repository
│       └── task_repository_impl.dart
├── providers/
│   ├── task/
│   │   ├── task_notifier.dart       # Task state notifier
│   │   ├── task_state.dart          # Task state model
│   │   └── tasks_provider.dart      # Riverpod provider
│   ├── category_provider.dart
│   ├── date_provider.dart
│   └── time_provider.dart
├── screens/
│   ├── home_screen.dart             # Task list by date
│   └── create_task_screen.dart      # New task form
├── utils/
│   ├── task_category.dart           # TaskCategory enum (9 categories)
│   ├── helpers.dart                 # Date/time utilities
│   ├── app_alerts.dart              # Snackbar helpers
│   └── extensions.dart              # BuildContext extensions
└── widgets/
    ├── app_background.dart
    ├── categories_selection.dart
    ├── display_list_of_tasks.dart
    ├── task_tile.dart
    ├── select_date_time.dart
    └── common_text_field.dart
```

---

## Getting Started

### Prerequisites

- Flutter SDK `>=3.8.1`
- Dart SDK `>=3.0.0`
- Android Studio / VS Code with Flutter extension

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/maazkhan-tech/flutter-todo-app.git
   cd flutter-todo-app
   ```

2. **Install dependencies**
   ```bash
   flutter pub get
   ```

3. **Run the app**
   ```bash
   flutter run
   ```

---

## Key Dependencies

```yaml
dependencies:
  flutter_riverpod: ^2.6.1
  sqflite: ^2.4.2
  go_router: ^15.2.0
  flex_color_scheme: ^8.2.0
  google_fonts: ^6.2.1
  font_awesome_flutter: ^10.8.0
  equatable: ^2.0.7
  intl: ^0.20.2
  gap: ^3.0.1
  path: ^1.9.1
```

---

## Architecture

This app follows a **layered architecture** pattern:

```
UI (Screens & Widgets)
        ↓
Providers (Riverpod — State Management)
        ↓
Repository (Abstract interface)
        ↓
Datasource (SQLite via sqflite)
```

- **Screens** consume providers via `ConsumerWidget` / `ConsumerStatefulWidget`
- **Notifiers** handle business logic and call the repository
- **Repository pattern** decouples data logic from UI
- **SQLite datasource** is a singleton with full CRUD support

---

## Database Schema

```sql
CREATE TABLE tasks (
  id        INTEGER PRIMARY KEY AUTOINCREMENT,
  title     TEXT,
  note      TEXT,
  date      TEXT,
  time      TEXT,
  category  TEXT,
  isCompleted INTEGER
);
```

---

## Task Categories

| Category | Icon | Color |
|---|---|---|
| Work | 💼 | Amber |
| Personal | 👤 | Light Blue |
| Health | ❤️ | Orange |
| Travel | ✈️ | Pink |
| Shopping | 🛍️ | Deep Orange |
| Education | 🎓 | Blue Grey |
| Social | 👥 | Brown |
| Home | 🏠 | Green |
| Others | 📅 | Purple |

---

## What I Learned

- Riverpod state management with `StateNotifier` and `ProviderScope`
- SQLite database integration using `sqflite` with singleton pattern
- Repository pattern for clean separation of data and UI concerns
- GoRouter for declarative routing in Flutter
- Advanced theming with `FlexColorScheme` and `Google Fonts`
- Using enums with properties (icon + color) for categories
- `ConsumerWidget` vs `ConsumerStatefulWidget` usage

---

## Contributing

Contributions, issues, and feature requests are welcome!
Feel free to open an [issue](https://github.com/maazkhan-tech/flutter-todo-app/issues) or submit a pull request.

---

## License

This project is open source and available under the [MIT License](LICENSE).

---

## Author

**Your Name**
- GitHub: [@maazkhan-tech](https://github.com/maazkhan-tech)
- LinkedIn: [Click](https://linkedin.com/in/maaz-khan-5385bb386)
