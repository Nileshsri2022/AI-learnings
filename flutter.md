

# 🗺️ ROADMAP: Flutter Development
### *From Zero to Deploying Real Apps — Complete Week-by-Week Plan*

---

## 📍 Quick Skill Assessment First

| Before Starting Flutter, You Need | Status Check |
|---|---|
| Any one programming language (C++/Java/Python) | ✅ Required |
| Basic OOP concepts (classes, objects, inheritance) | ✅ Required |
| Basic understanding of how apps work (user) | ✅ Required |
| Git & GitHub basics | 🟡 Learn alongside |
| Prior mobile dev experience | ❌ NOT required |

> 💡 **Flutter uses Dart language** — you do NOT need to learn Dart separately first. We'll learn Dart *inside* Flutter context, which is faster and more practical.

---

## 🏗️ THE COMPLETE ROADMAP — 16 WEEKS

```
📊 STRUCTURE OVERVIEW

 PHASE 1 ██████░░░░░░░░░░  Weeks 1-3   → Dart + Flutter Basics
 PHASE 2 ██████████░░░░░░  Weeks 4-6   → Widgets & UI Mastery
 PHASE 3 ██████████████░░  Weeks 7-10  → State, APIs, Storage
 PHASE 4 ████████████████  Weeks 11-14 → Advanced + Projects
 PHASE 5 ████████████████  Weeks 15-16 → Testing, CI/CD, Deploy

 🔴 = Critical (Must Learn)
 🟡 = Important (Should Learn)
 🟢 = Good to Know (Learn When Needed)
```

---

## PHASE 1: FOUNDATION (Weeks 1–3)
### 🎯 Goal: *Write your first Flutter app and understand Dart*

---

### 📅 Week 1: Dart Language Essentials + Setup

#### 🔴 Development Environment Setup (Day 1)
```
Install these:
├── Flutter SDK (flutter.dev)
├── IDE (Pick ONE):
│   ├── VS Code ✅ (Recommended — lightweight, fast)
│   ├── Android Studio (heavier but full-featured)
│   └── IntelliJ IDEA (alternative)
├── Flutter & Dart plugins for your IDE
├── Android Emulator OR physical device
├── (Optional) Xcode — only if you have a Mac for iOS
└── Flutter CLI — verify with: flutter doctor
```

**Setup verification — run this in terminal:**
```bash
flutter doctor
```
✅ All green checkmarks = ready to go.

#### 🔴 Dart Pad (Day 1 — Quick Start)
> Use [dartpad.dev](https://dartpad.dev) to practice Dart without any setup

#### 🔴 Dart Basics (Days 2–5)

```dart
// ──────── VARIABLES & DATA TYPES ────────

void main() {
  // Type inference
  var name = 'Rahul';           // String (inferred)
  String college = 'IIT Delhi'; // Explicit type
  int year = 3;
  double cgpa = 8.5;
  bool isPlaced = false;
  
  // Final vs Const
  final currentTime = DateTime.now();  // Runtime constant
  const pi = 3.14159;                 // Compile-time constant
  
  // Null Safety (Dart's killer feature)
  String? nullableName;    // Can be null
  String nonNullable = ''; // Cannot be null
  
  print('$name from $college, Year $year, CGPA: $cgpa');
}
```

```dart
// ──────── FUNCTIONS ────────

// Regular function
int add(int a, int b) {
  return a + b;
}

// Arrow function (one-liners)
int multiply(int a, int b) => a * b;

// Named parameters (VERY common in Flutter)
void greet({required String name, int age = 20}) {
  print('Hello $name, age $age');
}

// Optional positional parameters
void log(String msg, [String? tag]) {
  print('${tag ?? "LOG"}: $msg');
}

void main() {
  greet(name: 'Rahul', age: 21);
  log('App started', 'INIT');
}
```

```dart
// ──────── CONTROL FLOW ────────

void main() {
  int marks = 75;
  
  // If-else
  if (marks >= 90) {
    print('A+');
  } else if (marks >= 75) {
    print('A');
  } else {
    print('Keep trying');
  }
  
  // For loop
  for (int i = 0; i < 5; i++) {
    print('Iteration $i');
  }
  
  // For-in loop
  var subjects = ['DSA', 'OS', 'DBMS'];
  for (var sub in subjects) {
    print(sub);
  }
  
  // Switch (Dart 3 pattern matching)
  switch (marks) {
    case >= 90:
      print('Outstanding');
    case >= 75:
      print('Good');
    default:
      print('Average');
  }
}
```

```dart
// ──────── OPERATORS ────────

void main() {
  // Null-aware operators (USE THESE A LOT)
  String? name;
  print(name ?? 'Guest');        // If null, use 'Guest'
  name ??= 'Default';           // Assign if null
  
  // Cascade operator (common in Flutter)
  var list = [3, 1, 2]
    ..sort()
    ..add(4);
  print(list); // [1, 2, 3, 4]
  
  // Spread operator
  var moreItems = [0, ...list, 5];
  print(moreItems); // [0, 1, 2, 3, 4, 5]
}
```

#### 🟡 Built-in Types Deep Dive (Days 6–7)

```dart
// ──────── COLLECTIONS ────────

void main() {
  // List (Array equivalent)
  List<int> numbers = [1, 2, 3, 4, 5];
  numbers.add(6);
  numbers.where((n) => n % 2 == 0).forEach(print); // 2, 4, 6
  
  // Map (Dictionary/HashMap equivalent)
  Map<String, int> scores = {
    'DSA': 85,
    'OS': 78,
    'DBMS': 92,
  };
  scores['CN'] = 88;
  
  // Set (unique elements)
  Set<String> skills = {'Flutter', 'Dart', 'Firebase'};
  skills.add('Flutter'); // Won't duplicate
  
  // List methods you'll use DAILY in Flutter
  var items = [1, 2, 3, 4, 5];
  var doubled = items.map((e) => e * 2).toList();
  var filtered = items.where((e) => e > 3).toList();
  var sum = items.fold(0, (prev, e) => prev + e);
}
```

**📋 Week 1 Mini-Project: Dart CLI Calculator**
```
Build a command-line calculator that:
✅ Takes two numbers and an operator
✅ Supports +, -, *, /, % operations
✅ Handles division by zero
✅ Uses functions, null safety, error handling
```

---

### 📅 Week 2: Flutter Basics — First App

#### 🔴 Understanding Flutter Architecture (Day 1)

```
┌─────────────────────────────────────────────┐
│              YOUR FLUTTER APP               │
├─────────────────────────────────────────────┤
│                                             │
│   ┌──────────┐   Everything in Flutter      │
│   │  Widget   │   is a WIDGET               │
│   │  Tree     │   (like HTML elements,      │
│   │          │    but for mobile apps)      │
│   └────┬─────┘                              │
│        │                                    │
│   ┌────▼─────┐   Flutter converts widgets   │
│   │  Element  │   into elements (manages    │
│   │  Tree     │   lifecycle & state)        │
│   └────┬─────┘                              │
│        │                                    │
│   ┌────▼─────┐   Elements create render     │
│   │  Render   │   objects (actual pixels     │
│   │  Tree     │   on screen)                │
│   └──────────┘                              │
│                                             │
│   🧒 Think of it like:                      │
│   Widget = Blueprint (chai recipe)          │
│   Element = Chef (follows recipe)           │
│   RenderObject = Actual chai (what you see) │
└─────────────────────────────────────────────┘
```

#### 🔴 Your First Flutter App (Days 2–3)

```dart
import 'package:flutter/material.dart';

// Entry point — every Flutter app starts here
void main() {
  runApp(const MyApp());
}

// Root Widget
class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'My First App',
      debugShowCheckedModeBanner: false,
      theme: ThemeData(
        colorSchemeSeed: Colors.blue,
        useMaterial3: true,
      ),
      home: const HomeScreen(),
    );
  }
}

// Home Screen
class HomeScreen extends StatelessWidget {
  const HomeScreen({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      // App bar at top
      appBar: AppBar(
        title: const Text('Hello Flutter! 🎉'),
      ),
      // Main content
      body: const Center(
        child: Text(
          'Mera Pehla Flutter App!',
          style: TextStyle(fontSize: 24),
        ),
      ),
      // Floating action button
      floatingActionButton: FloatingActionButton(
        onPressed: () {
          print('Button pressed!');
        },
        child: const Icon(Icons.add),
      ),
    );
  }
}
```

#### 🔴 Stateless vs Stateful Widgets (Days 4–5)

```
┌──────────────────────┬──────────────────────────┐
│   STATELESS WIDGET   │    STATEFUL WIDGET       │
├──────────────────────┼──────────────────────────┤
│ Data doesn't change  │ Data CAN change          │
│ Built once           │ Rebuilt when state changes│
│ Like a poster on wall│ Like a scoreboard        │
│ Uses: Text, Icon,    │ Uses: Forms, Counters,   │
│   static layouts     │   dynamic content        │
│                      │                          │
│ class MyWidget       │ class MyWidget            │
│   extends            │   extends                │
│   StatelessWidget    │   StatefulWidget         │
└──────────────────────┴──────────────────────────┘
```

```dart
// ──────── STATEFUL WIDGET EXAMPLE ────────
// Classic Counter App (Flutter's "Hello World")

class CounterScreen extends StatefulWidget {
  const CounterScreen({super.key});

  @override
  State<CounterScreen> createState() => _CounterScreenState();
}

class _CounterScreenState extends State<CounterScreen> {
  int _counter = 0;  // This is the STATE

  void _increment() {
    setState(() {     // setState tells Flutter to REBUILD
      _counter++;
    });
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: const Text('Counter App')),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            const Text('You pressed the button:'),
            Text(
              '$_counter times',
              style: Theme.of(context).textTheme.headlineMedium,
            ),
          ],
        ),
      ),
      floatingActionButton: FloatingActionButton(
        onPressed: _increment,
        child: const Icon(Icons.add),
      ),
    );
  }
}
```

#### 🔴 Flutter CLI Commands (Day 6)

```bash
# Commands you'll use DAILY
flutter create my_app        # Create new project
flutter run                  # Run app on device/emulator
flutter run -d chrome        # Run on Chrome (web)
flutter hot reload           # 'r' in terminal (instant refresh)
flutter hot restart          # 'R' in terminal (full restart)
flutter pub get              # Install dependencies
flutter pub add [package]    # Add a package
flutter clean                # Clean build files
flutter build apk            # Build Android APK
flutter build ios            # Build iOS (Mac only)
flutter doctor               # Check setup status
flutter analyze              # Check code for errors

# FVM (Flutter Version Manager) — 🟡 Learn Later
# Useful when working on multiple projects needing different Flutter versions
```

#### 🟡 Working with Assets (Day 7)

```yaml
# pubspec.yaml — add your assets here
flutter:
  assets:
    - assets/images/
    - assets/icons/
    - assets/data/
  
  fonts:
    - family: Poppins
      fonts:
        - asset: assets/fonts/Poppins-Regular.ttf
        - asset: assets/fonts/Poppins-Bold.ttf
          weight: 700
```

```dart
// Using assets in code
Image.asset('assets/images/logo.png')

// Using custom fonts
Text(
  'Hello',
  style: TextStyle(fontFamily: 'Poppins'),
)
```

**📋 Week 2 Mini-Project: Profile Card App**
```
Build a personal profile card that shows:
✅ Your photo (from assets)
✅ Name, college, year
✅ Skills as chips/tags
✅ Social links (tap to open)
✅ Dark/Light theme toggle (StatefulWidget)
```

---

### 📅 Week 3: Core Widgets & Layouts

#### 🔴 Layout Widgets — The Building Blocks

```
Widget Family Tree:
┌────────────────────────────────────────────────────────┐
│                    LAYOUT WIDGETS                      │
├────────────────┬──────────────┬────────────────────────┤
│  SINGLE CHILD  │ MULTI CHILD  │  SLIVER (scrollable)  │
├────────────────┼──────────────┼────────────────────────┤
│ Container      │ Row          │ SliverList             │
│ Padding        │ Column       │ SliverGrid             │
│ Center         │ Stack        │ SliverAppBar           │
│ Align          │ Wrap         │ CustomScrollView       │
│ SizedBox       │ ListView     │                        │
│ Expanded       │ GridView     │                        │
│ Flexible       │              │                        │
│ Card           │              │                        │
└────────────────┴──────────────┴────────────────────────┘
```

```dart
// ──────── ROW & COLUMN (Most used layouts) ────────

// 🧒 Analogy:
// Row = Train coaches (side by side → horizontal)
// Column = Stack of tiffin boxes (top to bottom → vertical)

class LayoutExample extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Column(
      mainAxisAlignment: MainAxisAlignment.center,     // ↕ Vertical
      crossAxisAlignment: CrossAxisAlignment.start,    // ↔ Horizontal
      children: [
        // Row inside Column
        Row(
          mainAxisAlignment: MainAxisAlignment.spaceEvenly,
          children: [
            _buildCard('DSA', Icons.code, Colors.blue),
            _buildCard('Flutter', Icons.phone_android, Colors.green),
            _buildCard('Firebase', Icons.cloud, Colors.orange),
          ],
        ),
        const SizedBox(height: 20),  // Spacing (better than Padding)
        const Text('My Skills', style: TextStyle(fontSize: 24)),
      ],
    );
  }

  Widget _buildCard(String title, IconData icon, Color color) {
    return Card(
      child: Padding(
        padding: const EdgeInsets.all(16),
        child: Column(
          children: [
            Icon(icon, size: 40, color: color),
            const SizedBox(height: 8),
            Text(title),
          ],
        ),
      ),
    );
  }
}
```

```dart
// ──────── CONTAINER (Swiss Army Knife widget) ────────

Container(
  width: 200,
  height: 100,
  margin: const EdgeInsets.all(10),
  padding: const EdgeInsets.symmetric(horizontal: 16, vertical: 8),
  decoration: BoxDecoration(
    color: Colors.blue.shade50,
    borderRadius: BorderRadius.circular(12),
    border: Border.all(color: Colors.blue),
    boxShadow: [
      BoxShadow(
        color: Colors.black.withOpacity(0.1),
        blurRadius: 10,
        offset: const Offset(0, 4),
      ),
    ],
  ),
  child: const Center(
    child: Text('Styled Container'),
  ),
)
```

```dart
// ──────── STACK (Overlapping widgets) ────────
// 🧒 Like placing stickers on top of each other

Stack(
  alignment: Alignment.center,
  children: [
    // Bottom layer
    Container(width: 200, height: 200, color: Colors.red),
    // Middle layer
    Container(width: 150, height: 150, color: Colors.green),
    // Top layer
    Container(width: 100, height: 100, color: Colors.blue),
    // Positioned widget
    Positioned(
      bottom: 10,
      right: 10,
      child: Icon(Icons.star, color: Colors.yellow),
    ),
  ],
)
```

#### 🔴 Responsive Design

```dart
// ──────── Making apps responsive ────────

class ResponsiveLayout extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    // Get screen dimensions
    final screenWidth = MediaQuery.of(context).size.width;
    final screenHeight = MediaQuery.of(context).size.height;
    
    return Scaffold(
      body: LayoutBuilder(
        builder: (context, constraints) {
          if (constraints.maxWidth > 900) {
            return _buildDesktopLayout();    // Desktop
          } else if (constraints.maxWidth > 600) {
            return _buildTabletLayout();     // Tablet
          } else {
            return _buildMobileLayout();     // Mobile
          }
        },
      ),
    );
  }
}

// Also use these for responsive sizing:
// - Expanded & Flexible (flex-based)
// - FractionallySizedBox (percentage-based)
// - AspectRatio (ratio-based)
// - MediaQuery (screen info)
```

#### 🔴 Lists & Scrolling

```dart
// ──────── ListView (Most common scrollable) ────────

// Method 1: For small, known lists
ListView(
  children: [
    ListTile(title: Text('Item 1')),
    ListTile(title: Text('Item 2')),
    ListTile(title: Text('Item 3')),
  ],
)

// Method 2: For large/dynamic lists (EFFICIENT — lazy loading)
ListView.builder(
  itemCount: 1000,
  itemBuilder: (context, index) {
    return ListTile(
      leading: CircleAvatar(child: Text('${index + 1}')),
      title: Text('Student ${index + 1}'),
      subtitle: Text('BTech CSE'),
      trailing: const Icon(Icons.arrow_forward_ios),
      onTap: () {
        // Navigate to detail
      },
    );
  },
)

// Method 3: Grid layout
GridView.builder(
  gridDelegate: const SliverGridDelegateWithFixedCrossAxisCount(
    crossAxisCount: 2,      // 2 columns
    crossAxisSpacing: 10,
    mainAxisSpacing: 10,
  ),
  itemCount: 20,
  itemBuilder: (context, index) {
    return Card(child: Center(child: Text('Item $index')));
  },
)
```

#### 🟡 Navigation

```dart
// ──────── Screen Navigation ────────

// Method 1: Simple push/pop
Navigator.push(
  context,
  MaterialPageRoute(builder: (context) => const DetailScreen()),
);

Navigator.pop(context); // Go back

// Method 2: Named routes (better for larger apps)
// In MaterialApp:
MaterialApp(
  routes: {
    '/': (context) => HomeScreen(),
    '/detail': (context) => DetailScreen(),
    '/profile': (context) => ProfileScreen(),
  },
)

// Navigate with:
Navigator.pushNamed(context, '/detail');

// Method 3: GoRouter (recommended for production)
// flutter pub add go_router
```

**📋 Week 3 Mini-Project: Student Directory App**
```
Build an app with:
✅ A list of students (ListView.builder)
✅ Each student has: name, branch, CGPA, photo
✅ Tap on student → navigate to detail screen
✅ Detail screen shows full profile
✅ Responsive layout (different for phone & tablet)
✅ Use proper folder structure
```

#### 📁 Recommended Folder Structure (Start Using Now)
```
lib/
├── main.dart
├── models/          # Data classes
│   └── student.dart
├── screens/         # Full screens/pages
│   ├── home_screen.dart
│   └── detail_screen.dart
├── widgets/         # Reusable UI components
│   ├── student_card.dart
│   └── custom_button.dart
├── services/        # API calls, database
│   └── api_service.dart
├── providers/       # State management
│   └── student_provider.dart
├── utils/           # Constants, helpers
│   ├── constants.dart
│   └── helpers.dart
└── theme/           # App theming
    └── app_theme.dart
```

---

## PHASE 2: UI MASTERY (Weeks 4–6)
### 🎯 Goal: *Build beautiful, production-quality UIs*

---

### 📅 Week 4: Material & Cupertino Widgets

#### 🔴 Material Design Widgets

```dart
// ──────── ESSENTIAL MATERIAL WIDGETS ────────

Scaffold(
  appBar: AppBar(
    title: Text('App'),
    actions: [IconButton(icon: Icon(Icons.search), onPressed: () {})],
  ),
  drawer: Drawer(...),              // Side menu
  bottomNavigationBar: BottomNavigationBar(
    items: [
      BottomNavigationBarItem(icon: Icon(Icons.home), label: 'Home'),
      BottomNavigationBarItem(icon: Icon(Icons.search), label: 'Search'),
      BottomNavigationBarItem(icon: Icon(Icons.person), label: 'Profile'),
    ],
    currentIndex: _selectedIndex,
    onTap: (index) => setState(() => _selectedIndex = index),
  ),
  body: _pages[_selectedIndex],
)

// Buttons
ElevatedButton(onPressed: () {}, child: Text('Elevated'))
TextButton(onPressed: () {}, child: Text('Text'))
OutlinedButton(onPressed: () {}, child: Text('Outlined'))
IconButton(onPressed: () {}, icon: Icon(Icons.star))
FloatingActionButton(onPressed: () {}, child: Icon(Icons.add))

// Input
TextField(
  controller: _controller,
  decoration: InputDecoration(
    labelText: 'Enter name',
    hintText: 'e.g., Rahul',
    prefixIcon: Icon(Icons.person),
    border: OutlineInputBorder(),
  ),
  onChanged: (value) => print(value),
)

// Dialogs & Snackbars
showDialog(context: context, builder: (ctx) => AlertDialog(...));
ScaffoldMessenger.of(context).showSnackBar(SnackBar(content: Text('Done!')));
```

#### 🟡 Cupertino (iOS-style) Widgets

```dart
// For iOS-native look
CupertinoApp(...)
CupertinoPageScaffold(...)
CupertinoButton(child: Text('iOS Button'), onPressed: () {})
CupertinoTextField(placeholder: 'Search...')
CupertinoSwitch(value: _isOn, onChanged: (v) => setState(() => _isOn = v))
CupertinoAlertDialog(...)

// Platform-adaptive approach
import 'dart:io';
if (Platform.isIOS) → use Cupertino
if (Platform.isAndroid) → use Material
```

#### 🔴 Forms & Validation

```dart
class LoginForm extends StatefulWidget {
  @override
  State<LoginForm> createState() => _LoginFormState();
}

class _LoginFormState extends State<LoginForm> {
  final _formKey = GlobalKey<FormState>();
  final _emailController = TextEditingController();
  final _passwordController = TextEditingController();

  @override
  void dispose() {
    _emailController.dispose();
    _passwordController.dispose();
    super.dispose();
  }

  @override
  Widget build(BuildContext context) {
    return Form(
      key: _formKey,
      child: Column(
        children: [
          TextFormField(
            controller: _emailController,
            decoration: InputDecoration(labelText: 'Email'),
            validator: (value) {
              if (value == null || value.isEmpty) {
                return 'Email is required';
              }
              if (!value.contains('@')) {
                return 'Enter a valid email';
              }
              return null; // Valid
            },
          ),
          TextFormField(
            controller: _passwordController,
            obscureText: true,
            decoration: InputDecoration(labelText: 'Password'),
            validator: (value) {
              if (value == null || value.length < 6) {
                return 'Password must be 6+ characters';
              }
              return null;
            },
          ),
          ElevatedButton(
            onPressed: () {
              if (_formKey.currentState!.validate()) {
                // Form is valid — proceed
                print('Email: ${_emailController.text}');
              }
            },
            child: Text('Login'),
          ),
        ],
      ),
    );
  }
}
```

**📋 Week 4 Mini-Project: Login + Registration UI**
```
✅ Login screen with email/password validation
✅ Registration screen with name, email, phone, password
✅ Bottom navigation with 3-4 tabs
✅ Drawer menu with profile header
✅ Dark mode / Light mode toggle
✅ Use Material 3 theming
```

---

### 📅 Week 5: Theming, Styling & Inherited Widgets

#### 🔴 App-wide Theming

```dart
MaterialApp(
  theme: ThemeData(
    colorSchemeSeed: Colors.deepPurple,
    useMaterial3: true,
    brightness: Brightness.light,
    textTheme: TextTheme(
      headlineLarge: TextStyle(fontFamily: 'Poppins', fontWeight: FontWeight.bold),
      bodyMedium: TextStyle(fontFamily: 'Poppins'),
    ),
    elevatedButtonTheme: ElevatedButtonThemeData(
      style: ElevatedButton.styleFrom(
        padding: EdgeInsets.symmetric(horizontal: 24, vertical: 12),
        shape: RoundedRectangleBorder(borderRadius: BorderRadius.circular(8)),
      ),
    ),
  ),
  darkTheme: ThemeData(
    colorSchemeSeed: Colors.deepPurple,
    useMaterial3: true,
    brightness: Brightness.dark,
  ),
  themeMode: ThemeMode.system, // Follow system setting
)

// Access theme anywhere:
Theme.of(context).colorScheme.primary
Theme.of(context).textTheme.headlineLarge
```

#### 🟡 InheritedWidget (Foundation of State Management)

```dart
// InheritedWidget = Pass data DOWN the widget tree
// without passing through every constructor
//
// 🧒 Analogy: Like a college notice board — any student
// can read it without principal telling each one personally

class UserData extends InheritedWidget {
  final String username;
  final String email;

  const UserData({
    required this.username,
    required this.email,
    required Widget child,
  }) : super(child: child);

  static UserData of(BuildContext context) {
    return context.dependOnInheritedWidgetOfExactType<UserData>()!;
  }

  @override
  bool updateShouldNotify(UserData oldWidget) {
    return username != oldWidget.username || email != oldWidget.email;
  }
}

// Usage: Wrap your app/screen
UserData(
  username: 'Rahul',
  email: 'rahul@email.com',
  child: MyScreen(),
)

// Access anywhere below in tree:
final user = UserData.of(context);
Text(user.username);
```

---

### 📅 Week 6: Version Control + Design Principles

#### 🔴 Git & GitHub (Essential for ALL Projects)

```bash
# Daily Git workflow
git init
git add .
git commit -m "feat: add login screen with validation"
git remote add origin https://github.com/username/app.git
git push -u origin main

# Commit message convention (looks professional)
feat: add new feature
fix: bug fix
docs: documentation changes
style: formatting, missing semicolons
refactor: code restructuring
test: adding tests
```

#### 🟡 Design Principles (Write Better Code)

```
OOP in Dart:
├── Encapsulation  → Private fields with underscore: _name
├── Inheritance    → class Dog extends Animal
├── Polymorphism   → @override methods
├── Abstraction    → abstract class Shape { double area(); }

SOLID Principles (at awareness level for now):
├── S → Single Responsibility (1 class = 1 job)
├── O → Open/Closed (extend, don't modify)
├── L → Liskov Substitution (child replaces parent)
├── I → Interface Segregation (small interfaces)
└── D → Dependency Inversion (depend on abstractions)

Design Patterns (learn these gradually):
├── Singleton    → Single instance (database connection)
├── Factory      → Object creation logic
├── Observer     → State management basis
├── Repository   → Data access layer
└── MVC/MVVM     → Architecture patterns
```

#### 🔴 Package Manager — pub.dev

```yaml
# pubspec.yaml — adding packages

dependencies:
  flutter:
    sdk: flutter
  
  # Most commonly used packages:
  http: ^1.1.0              # API calls
  dio: ^5.3.0               # Better API calls
  provider: ^6.1.0          # State management
  shared_preferences: ^2.2.0 # Local storage
  go_router: ^12.0.0        # Navigation
  flutter_bloc: ^8.1.3      # BLoC state management
  google_fonts: ^6.1.0      # Fonts
  cached_network_image: ^3.3.0  # Image caching
  intl: ^0.18.0             # Date/number formatting
  url_launcher: ^6.2.0      # Open URLs
  shimmer: ^3.0.0           # Loading effects
```

```bash
# Install packages
flutter pub add provider
flutter pub add http
flutter pub get      # Install all dependencies
```

**📋 Week 6 Project: UI Clone Challenge**
```
Clone ONE of these popular app UIs:
✅ Swiggy/Zomato home screen
✅ WhatsApp chat list + chat screen
✅ Instagram profile page
✅ Spotify home screen

Requirements:
- Pixel-perfect as much as possible
- Responsive design
- Custom theme
- Proper folder structure
- Push to GitHub with good README
```

---

## PHASE 3: REAL-WORLD SKILLS (Weeks 7–10)
### 🎯 Goal: *APIs, Storage, State Management — Build Real Apps*

---

### 📅 Week 7: Working with APIs

#### 🔴 Async/Await & Futures

```dart
// ──────── FUTURES (Promises in Dart) ────────
//
// 🧒 Analogy: Like ordering food on Swiggy
// You place order (Future) → wait → food arrives (resolved)
// If restaurant closed → error (rejected)

Future<String> fetchUserName() async {
  // Simulating API call with delay
  await Future.delayed(Duration(seconds: 2));
  return 'Rahul';
}

void main() async {
  print('Fetching...');
  String name = await fetchUserName();
  print('Got: $name');
  
  // Error handling
  try {
    var data = await fetchUserName();
    print(data);
  } catch (e) {
    print('Error: $e');
  }
}
```

#### 🔴 HTTP Requests & JSON

```dart
import 'dart:convert';
import 'package:http/http.dart' as http;

// ──────── MODEL CLASS ────────
class User {
  final int id;
  final String name;
  final String email;

  User({required this.id, required this.name, required this.email});

  // From JSON (deserialization)
  factory User.fromJson(Map<String, dynamic> json) {
    return User(
      id: json['id'],
      name: json['name'],
      email: json['email'],
    );
  }

  // To JSON (serialization)
  Map<String, dynamic> toJson() {
    return {'id': id, 'name': name, 'email': email};
  }
}

// ──────── API SERVICE ────────
class ApiService {
  static const baseUrl = 'https://jsonplaceholder.typicode.com';

  // GET request
  Future<List<User>> fetchUsers() async {
    final response = await http.get(Uri.parse('$baseUrl/users'));
    
    if (response.statusCode == 200) {
      List<dynamic> jsonList = json.decode(response.body);
      return jsonList.map((json) => User.fromJson(json)).toList();
    } else {
      throw Exception('Failed to load users');
    }
  }

  // POST request
  Future<User> createUser(String name, String email) async {
    final response = await http.post(
      Uri.parse('$baseUrl/users'),
      headers: {'Content-Type': 'application/json'},
      body: json.encode({'name': name, 'email': email}),
    );
    
    if (response.statusCode == 201) {
      return User.fromJson(json.decode(response.body));
    } else {
      throw Exception('Failed to create user');
    }
  }
}
```

```dart
// ──────── USING API IN WIDGET ────────

class UsersScreen extends StatefulWidget {
  @override
  State<UsersScreen> createState() => _UsersScreenState();
}

class _UsersScreenState extends State<UsersScreen> {
  late Future<List<User>> _usersFuture;

  @override
  void initState() {
    super.initState();
    _usersFuture = ApiService().fetchUsers();
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('Users')),
      body: FutureBuilder<List<User>>(
        future: _usersFuture,
        builder: (context, snapshot) {
          // Loading state
          if (snapshot.connectionState == ConnectionState.waiting) {
            return Center(child: CircularProgressIndicator());
          }
          // Error state
          if (snapshot.hasError) {
            return Center(child: Text('Error: ${snapshot.error}'));
          }
          // Success state
          final users = snapshot.data!;
          return ListView.builder(
            itemCount: users.length,
            itemBuilder: (context, index) {
              return ListTile(
                title: Text(users[index].name),
                subtitle: Text(users[index].email),
              );
            },
          );
        },
      ),
    );
  }
}
```

#### 🟡 WebSockets & GraphQL (Learn Later)

```
WebSockets → Real-time data (chat apps, live scores)
GraphQL    → Alternative to REST (query exactly what you need)
             Package: graphql_flutter

Learn these when you need them for a specific project.
```

---

### 📅 Week 8: State Management 🔴🔴🔴

> ⚠️ **This is the MOST IMPORTANT topic in Flutter.**
> State management is what separates beginner from intermediate devs.

```
STATE MANAGEMENT OPTIONS:
┌────────────────────┬──────────┬──────────────┬───────────────┐
│ Solution           │ Learning │ Best For     │ Popularity    │
│                    │ Curve    │              │ (India 2024)  │
├────────────────────┼──────────┼──────────────┼───────────────┤
│ setState           │ ⭐       │ Small widgets │ Basics        │
│ Provider           │ ⭐⭐     │ Medium apps  │ ⭐⭐⭐⭐⭐   │
│ Riverpod           │ ⭐⭐⭐   │ All sizes    │ ⭐⭐⭐⭐     │
│ BLoC               │ ⭐⭐⭐⭐ │ Large/Enterprise│ ⭐⭐⭐⭐   │
│ GetX               │ ⭐⭐     │ Quick MVPs   │ ⭐⭐⭐       │
│ ChangeNotifier     │ ⭐⭐     │ Simple state │ Built-in      │
│ ValueNotifier      │ ⭐       │ Single values│ Built-in      │
└────────────────────┴──────────┴──────────────┴───────────────┘

📌 RECOMMENDATION:
   Learn Provider FIRST → then Riverpod or BLoC
   (Provider is enough for placements & most projects)
```

#### 🔴 Provider (Learn This First)

```dart
// Step 1: Create a ChangeNotifier class
class CartProvider extends ChangeNotifier {
  final List<String> _items = [];
  
  List<String> get items => List.unmodifiable(_items);
  int get itemCount => _items.length;
  
  void addItem(String item) {
    _items.add(item);
    notifyListeners();  // Tell all listeners to rebuild
  }
  
  void removeItem(String item) {
    _items.remove(item);
    notifyListeners();
  }
  
  void clearCart() {
    _items.clear();
    notifyListeners();
  }
}

// Step 2: Provide it at the top of widget tree
void main() {
  runApp(
    MultiProvider(
      providers: [
        ChangeNotifierProvider(create: (_) => CartProvider()),
        ChangeNotifierProvider(create: (_) => AuthProvider()),
        // Add more providers here
      ],
      child: MyApp(),
    ),
  );
}

// Step 3: Consume it anywhere in the tree
class CartScreen extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    // Method 1: context.watch (rebuilds on change)
    final cart = context.watch<CartProvider>();
    
    // Method 2: context.read (doesn't rebuild — for actions)
    // Use in onPressed, not in build method
    
    // Method 3: Consumer (rebuilds only this part)
    return Scaffold(
      appBar: AppBar(
        title: Text('Cart (${cart.itemCount})'),
      ),
      body: ListView.builder(
        itemCount: cart.items.length,
        itemBuilder: (context, index) {
          return ListTile(
            title: Text(cart.items[index]),
            trailing: IconButton(
              icon: Icon(Icons.delete),
              onPressed: () {
                context.read<CartProvider>().removeItem(cart.items[index]);
              },
            ),
          );
        },
      ),
      floatingActionButton: FloatingActionButton(
        onPressed: () {
          context.read<CartProvider>().addItem('Item ${cart.itemCount + 1}');
        },
        child: Icon(Icons.add),
      ),
    );
  }
}
```

#### 🟡 BLoC Pattern (Learn After Provider)

```dart
// BLoC = Business Logic Component
// Separates UI from business logic completely
//
// Events → BLoC → States
// (Input)         (Output)

// flutter pub add flutter_bloc

// ──── Events ────
abstract class CounterEvent {}
class IncrementEvent extends CounterEvent {}
class DecrementEvent extends CounterEvent {}

// ──── States ────
class CounterState {
  final int count;
  CounterState(this.count);
}

// ──── BLoC ────
class CounterBloc extends Bloc<CounterEvent, CounterState> {
  CounterBloc() : super(CounterState(0)) {
    on<IncrementEvent>((event, emit) => emit(CounterState(state.count + 1)));
    on<DecrementEvent>((event, emit) => emit(CounterState(state.count - 1)));
  }
}

// ──── UI ────
BlocBuilder<CounterBloc, CounterState>(
  builder: (context, state) {
    return Text('Count: ${state.count}');
  },
)
```

---

### 📅 Week 9: Local Storage + Firebase

#### 🔴 Shared Preferences (Key-Value Storage)

```dart
import 'package:shared_preferences/shared_preferences.dart';

// Save data
Future<void> saveSettings() async {
  final prefs = await SharedPreferences.getInstance();
  await prefs.setString('username', 'Rahul');
  await prefs.setBool('darkMode', true);
  await prefs.setInt('loginCount', 5);
}

// Read data
Future<void> loadSettings() async {
  final prefs = await SharedPreferences.getInstance();
  String? username = prefs.getString('username');
  bool darkMode = prefs.getBool('darkMode') ?? false;
}

// Use for: Theme preference, onboarding status, 
// auth tokens, small settings
```

#### 🟡 SQLite (Structured Local Database)

```dart
// flutter pub add sqflite path
// Use for: Offline-first apps, complex local data, 
// caching API responses

// Better alternative: Use 'drift' package (type-safe SQLite)
// flutter pub add drift
```

#### 🔴 Firebase Integration

```
Firebase Services You Should Know:
┌───────────────────────┬──────────────────────────────┐
│ Service               │ Use Case                     │
├───────────────────────┼──────────────────────────────┤
│ 🔐 Authentication    │ Login (Google, Email, Phone)  │
│ 📄 Cloud Firestore   │ NoSQL database (real-time)   │
│ 📦 Cloud Storage     │ Upload images/files          │
│ 🔔 Push Notifications│ FCM messaging                │
│ ⚙️ Remote Config     │ Change app behavior remotely │
│ ☁️ Cloud Functions   │ Backend logic (serverless)   │
│ 📊 Analytics         │ User behavior tracking       │
│ 🐛 Crashlytics       │ Crash reporting              │
└───────────────────────┴──────────────────────────────┘

Setup: Use FlutterFire CLI
  → dart pub global activate flutterfire_cli
  → flutterfire configure
```

```dart
// ──────── FIREBASE AUTH EXAMPLE ────────

import 'package:firebase_auth/firebase_auth.dart';

class AuthService {
  final FirebaseAuth _auth = FirebaseAuth.instance;
  
  // Get current user
  User? get currentUser => _auth.currentUser;
  
  // Stream of auth changes
  Stream<User?> get authStateChanges => _auth.authStateChanges();
  
  // Email/Password Sign Up
  Future<User?> signUp(String email, String password) async {
    try {
      final credential = await _auth.createUserWithEmailAndPassword(
        email: email,
        password: password,
      );
      return credential.user;
    } on FirebaseAuthException catch (e) {
      throw e.message ?? 'Sign up failed';
    }
  }
  
  // Sign In
  Future<User?> signIn(String email, String password) async {
    try {
      final credential = await _auth.signInWithEmailAndPassword(
        email: email,
        password: password,
      );
      return credential.user;
    } on FirebaseAuthException catch (e) {
      throw e.message ?? 'Sign in failed';
    }
  }
  
  // Sign Out
  Future<void> signOut() async => await _auth.signOut();
  
  // Google Sign In
  Future<User?> signInWithGoogle() async {
    // flutter pub add google_sign_in
    final googleUser = await GoogleSignIn().signIn();
    final googleAuth = await googleUser?.authentication;
    final credential = GoogleAuthProvider.credential(
      accessToken: googleAuth?.accessToken,
      idToken: googleAuth?.idToken,
    );
    final result = await _auth.signInWithCredential(credential);
    return result.user;
  }
}
```

```dart
// ──────── FIRESTORE EXAMPLE ────────

import 'package:cloud_firestore/cloud_firestore.dart';

class DatabaseService {
  final FirebaseFirestore _db = FirebaseFirestore.instance;
  
  // Create
  Future<void> addStudent(Map<String, dynamic> data) async {
    await _db.collection('students').add(data);
  }
  
  // Read (one-time)
  Future<List<Map<String, dynamic>>> getStudents() async {
    final snapshot = await _db.collection('students').get();
    return snapshot.docs.map((doc) => doc.data()).toList();
  }
  
  // Read (real-time stream)
  Stream<QuerySnapshot> streamStudents() {
    return _db.collection('students')
      .orderBy('name')
      .snapshots();
  }
  
  // Update
  Future<void> updateStudent(String docId, Map<String, dynamic> data) async {
    await _db.collection('students').doc(docId).update(data);
  }
  
  // Delete
  Future<void> deleteStudent(String docId) async {
    await _db.collection('students').doc(docId).delete();
  }
}

// In UI — Real-time listener:
StreamBuilder<QuerySnapshot>(
  stream: DatabaseService().streamStudents(),
  builder: (context, snapshot) {
    if (!snapshot.hasData) return CircularProgressIndicator();
    final docs = snapshot.data!.docs;
    return ListView.builder(
      itemCount: docs.length,
      itemBuilder: (context, index) {
        final data = docs[index].data() as Map<String, dynamic>;
        return ListTile(title: Text(data['name']));
      },
    );
  },
)
```

**📋 Week 9 Project: Notes App with Firebase**
```
✅ Firebase Auth (Email + Google Sign In)
✅ Firestore to store notes
✅ CRUD operations (Create, Read, Update, Delete)
✅ Real-time sync across devices
✅ User-specific notes (each user sees only their notes)
✅ Offline support
✅ Provider for state management
```

---

### 📅 Week 10: Advanced Dart + Streams

#### 🔴 Streams (Real-time Data Flow)

```dart
// 🧒 Analogy: 
// Future = One-time Swiggy order (you get food once)
// Stream = Netflix subscription (continuous flow of content)

// ──── Creating Streams ────

// Method 1: Stream.periodic
Stream<int> counterStream() {
  return Stream.periodic(Duration(seconds: 1), (count) => count);
}

// Method 2: StreamController
final controller = StreamController<String>();
controller.sink.add('Hello');   // Add data
controller.stream.listen((data) => print(data)); // Listen
controller.close();             // Clean up

// Method 3: async* generator
Stream<int> fibonacci() async* {
  int a = 0, b = 1;
  while (true) {
    yield a;   // Emit value
    final next = a + b;
    a = b;
    b = next;
    await Future.delayed(Duration(seconds: 1));
  }
}

// ──── Using Streams in Flutter ────
StreamBuilder<int>(
  stream: counterStream(),
  builder: (context, snapshot) {
    if (!snapshot.hasData) return CircularProgressIndicator();
    return Text('Count: ${snapshot.data}');
  },
)
```

#### 🟡 Isolates (Background Processing)

```dart
// 🧒 Analogy: Main thread = Main chef
// Isolate = Hiring another chef for heavy work
// They don't share kitchen (memory) — communicate via messages

import 'dart:isolate';

// Heavy computation in background
Future<int> heavyComputation(int n) async {
  return await Isolate.run(() {
    // This runs in a separate thread
    int sum = 0;
    for (int i = 0; i < n; i++) {
      sum += i;
    }
    return sum;
  });
}

// Flutter provides compute() helper
final result = await compute(expensiveFunction, inputData);
```

#### 🟡 Functional Programming in Dart

```dart
// Lambdas, Higher-order functions, Method chaining

var students = [
  {'name': 'Rahul', 'cgpa': 8.5},
  {'name': 'Priya', 'cgpa': 9.2},
  {'name': 'Amit', 'cgpa': 7.8},
];

// Chain operations
var topStudents = students
    .where((s) => (s['cgpa'] as double) > 8.0)  // Filter
    .map((s) => s['name'])                        // Transform
    .toList()                                     // Collect
    ..sort();                                     // Sort in place

print(topStudents); // [Priya, Rahul]
```

---

## PHASE 4: ADVANCED + PORTFOLIO PROJECTS (Weeks 11–14)
### 🎯 Goal: *Build impressive projects, learn animations, architecture*

---

### 📅 Week 11: Animations

```dart
// ──────── IMPLICIT ANIMATIONS (Easy) ────────
// Flutter handles the animation for you

AnimatedContainer(
  duration: Duration(milliseconds: 300),
  curve: Curves.easeInOut,
  width: _expanded ? 300 : 100,
  height: _expanded ? 300 : 100,
  color: _expanded ? Colors.blue : Colors.red,
  child: Center(child: Text('Tap me')),
)

AnimatedOpacity(
  opacity: _visible ? 1.0 : 0.0,
  duration: Duration(milliseconds: 500),
  child: Text('I fade in and out'),
)

// ──────── HERO ANIMATION (Page transitions) ────────
// Source screen
Hero(
  tag: 'profile-pic',
  child: CircleAvatar(backgroundImage: AssetImage('pic.jpg')),
)

// Destination screen
Hero(
  tag: 'profile-pic',  // Same tag!
  child: Image.asset('pic.jpg'),
)

// ──────── EXPLICIT ANIMATIONS (Full control) ────────
class PulseAnimation extends StatefulWidget {
  @override
  State<PulseAnimation> createState() => _PulseAnimationState();
}

class _PulseAnimationState extends State<PulseAnimation>
    with SingleTickerProviderStateMixin {
  late AnimationController _controller;
  late Animation<double> _animation;

  @override
  void initState() {
    super.initState();
    _controller = AnimationController(
      duration: Duration(seconds: 2),
      vsync: this,
    )..repeat(reverse: true);
    
    _animation = Tween<double>(begin: 0.8, end: 1.2).animate(
      CurvedAnimation(parent: _controller, curve: Curves.easeInOut),
    );
  }

  @override
  void dispose() {
    _controller.dispose();
    super.dispose();
  }

  @override
  Widget build(BuildContext context) {
    return ScaleTransition(
      scale: _animation,
      child: FlutterLogo(size: 100),
    );
  }
}
```

---

### 📅 Week 12: Architecture & Reactive Programming

#### 🟡 Clean Architecture Pattern

```
┌─────────────────────────────────────────────┐
│              PRESENTATION LAYER              │
│  (UI / Widgets / Screens / BLoC/Provider)   │
├─────────────────────────────────────────────┤
│               DOMAIN LAYER                   │
│  (Use Cases / Entities / Repository Interfaces)│
├─────────────────────────────────────────────┤
│                DATA LAYER                    │
│  (Repository Impl / API / Local DB / Models) │
└─────────────────────────────────────────────┘

Folder structure:
lib/
├── core/           # Shared utilities
├── features/
│   ├── auth/
│   │   ├── data/
│   │   │   ├── models/
│   │   │   ├── repositories/
│   │   │   └── datasources/
│   │   ├── domain/
│   │   │   ├── entities/
│   │   │   ├── repositories/
│   │   │   └── usecases/
│   │   └── presentation/
│   │       ├── screens/
│   │       ├── widgets/
│   │       └── bloc/
│   └── home/
│       ├── data/
│       ├── domain/
│       └── presentation/
└── main.dart
```

#### 🟢 RxDart (Reactive Programming)

```dart
// flutter pub add rxdart
// Learn this if using BLoC or building complex stream logic

import 'package:rxdart/rxdart.dart';

// BehaviorSubject — holds last value
final subject = BehaviorSubject<int>.seeded(0);
subject.add(1);
subject.add(2);
// New listener immediately gets value 2

// Debounce — great for search
searchController.stream
    .debounceTime(Duration(milliseconds: 300))
    .listen((query) => searchAPI(query));
```

---

### 📅 Weeks 13–14: PORTFOLIO PROJECTS 🏆

Pick **TWO** projects from below. These go on your resume.

```
┌──────────────────────────────────────────────────────────────┐
│                    PROJECT IDEAS                              │
├───────────┬──────────────────────────────────────────────────┤
│ LEVEL     │ PROJECT                                          │
├───────────┼──────────────────────────────────────────────────┤
│ 🟡 Inter  │ 📰 News App (API + Categories + Bookmarks)      │
│           │ 🛒 E-Commerce App (Cart + Payment UI + Firebase) │
│           │ 💬 Chat App (Firebase + Real-time + Push Notif)  │
│           │ 🎵 Music Player (Audio + Playlists + UI)         │
├───────────┼──────────────────────────────────────────────────┤
│ 🔴 Adv    │ 📊 Expense Tracker (Charts + SQLite + Export)    │
│           │ 🍕 Food Delivery Clone (Maps + Auth + Orders)    │
│           │ 📝 Collaborative Notes (Real-time + Rich Text)   │
│           │ 🏥 Health Tracker (Sensors + Charts + Reminders) │
│           │ 📚 College Buddy (Attendance + Notes + Schedule) │
└───────────┴──────────────────────────────────────────────────┘
```

> **For each project, build with:**
> ✅ Clean architecture / organized folder structure
> ✅ State management (Provider or BLoC)
> ✅ API integration or Firebase
> ✅ Error handling & loading states
> ✅ Responsive design
> ✅ Professional README on GitHub
> ✅ Screenshots/GIFs in README

---

## PHASE 5: PRODUCTION READY (Weeks 15–16)
### 🎯 Goal: *Testing, CI/CD, Deployment — Ship Real Apps*

---

### 📅 Week 15: Testing & Dev Tools

```dart
// ──────── UNIT TESTING ────────
// test/calculator_test.dart

import 'package:test/test.dart';

void main() {
  group('Calculator', () {
    test('adds two numbers', () {
      expect(add(2, 3), equals(5));
    });

    test('handles negative numbers', () {
      expect(add(-1, 1), equals(0));
    });
  });
}

// ──────── WIDGET TESTING ────────
import 'package:flutter_test/flutter_test.dart';

void main() {
  testWidgets('Counter increments', (WidgetTester tester) async {
    await tester.pumpWidget(MyApp());
    
    // Verify initial state
    expect(find.text('0'), findsOneWidget);
    
    // Tap button
    await tester.tap(find.byIcon(Icons.add));
    await tester.pump();
    
    // Verify new state
    expect(find.text('1'), findsOneWidget);
  });
}

// Run tests: flutter test
```

```
Dev Tools (Built into Flutter):
├── Flutter Inspector   → Widget tree visualization
├── Flutter Outline     → Widget hierarchy
├── Memory Allocation   → Memory profiling
├── Performance Overlay → FPS & rendering
├── Network Tab         → API call monitoring
└── Logging             → Debug prints & errors

Access: flutter run → press 'D' → opens DevTools in browser
```

---

### 📅 Week 16: CI/CD & Deployment

```yaml
# ──────── GITHUB ACTIONS (CI/CD) ────────
# .github/workflows/flutter.yml

name: Flutter CI
on:
  push:
    branches: [main]
  pull_request:
    branches: [main]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: subosito/flutter-action@v2
        with:
          flutter-version: '3.16.0'
      - run: flutter pub get
      - run: flutter analyze
      - run: flutter test
      - run: flutter build apk --release
```

```bash
# ──────── DEPLOYMENT ────────

# Android APK
flutter build apk --release
# Output: build/app/outputs/flutter-apk/app-release.apk

# Android App Bundle (for Play Store)
flutter build appbundle --release

# iOS (Mac only)
flutter build ios --release

# Web
flutter build web
# Deploy to: Firebase Hosting, Vercel, Netlify

# Play Store Deployment:
# 1. Create keystore
# 2. Configure signing in android/app/build.gradle
# 3. Build app bundle
# 4. Upload to Google Play Console
# 5. Fill listing, screenshots, description
# 6. Submit for review

# Firebase App Distribution (for beta testing)
# Codemagic / Bitrise (automated CI/CD platforms)
```

---

## 📊 COMPLETE TIMELINE OVERVIEW

```
Week  │ Topic                        │ Build
──────┼──────────────────────────────┼──────────────────────
  1   │ Dart + Setup                 │ CLI Calculator
  2   │ Flutter Basics               │ Profile Card App
  3   │ Widgets & Layouts            │ Student Directory
  4   │ Material/Cupertino + Forms   │ Login/Register UI
  5   │ Theming + InheritedWidget    │ Themed App
  6   │ Git + Design Principles      │ UI Clone (Swiggy/WhatsApp)
  7   │ APIs + JSON                  │ Weather/News App
  8   │ State Management (Provider)  │ Todo App with Provider
  9   │ Firebase + Storage           │ Notes App (Full CRUD)
 10   │ Streams + Advanced Dart      │ Real-time Dashboard
 11   │ Animations                   │ Animated Onboarding
 12   │ Architecture + RxDart        │ Refactor previous project
13-14 │ PORTFOLIO PROJECTS           │ 2 Impressive Projects
 15   │ Testing + Dev Tools          │ Add tests to projects
 16   │ CI/CD + Deployment           │ Publish on Play Store
```

---

## 📚 BEST RESOURCES (Curated)

| Resource | Type | Best For |
|---|---|---|
| **[flutter.dev/docs](https://flutter.dev/docs)** | Official Docs | Reference (THE best) |
| **[Vandad Nahavandipoor](https://youtube.com/@user-vp6ps6mv2u)** | YouTube | Free full course |
| **[The Flutter Way](https://youtube.com/@TheFlutterWay)** | YouTube | Beautiful UI tutorials |
| **[Rivaan Ranawat](https://youtube.com/@RivaanRanawat)** | YouTube | Full project tutorials |
| **[FilledStacks](https://youtube.com/@filledstacks)** | YouTube | Architecture & best practices |
| **[CodeWithAndrea](https://codewithandrea.com)** | Blog + YouTube | Advanced patterns |
| **[Reso Coder](https://youtube.com/@ResoCoder)** | YouTube | Clean architecture |
| **[dart.dev/guides](https://dart.dev/guides)** | Official | Dart language deep dive |
| **[pub.dev](https://pub.dev)** | Package Hub | Find packages |
| **[roadmap.sh/flutter](https://roadmap.sh/flutter)** | Roadmap | Visual overview |
| **[flutter_examples (GitHub)](https://github.com/nicholasgasior/gf-flutter-cookbook)** | GitHub | Code samples |

### 🇮🇳 Hindi Resources
| Channel | Best For |
|---|---|
| **Rivaan Ranawat** | Complete Flutter projects |
| **CodeWithHarry (Flutter playlist)** | Beginner-friendly Hindi |
| **Desi Programmer** | Flutter + Firebase |

---

## 🏆 HOW THIS LOOKS ON RESUME

```
SKILLS:
  Flutter | Dart | Firebase | REST APIs | Provider/BLoC
  Git | CI/CD | SQLite | Material Design

PROJECTS:
  📱 FoodExpress — Food Delivery App
     • Built with Flutter, Firebase Auth, Firestore, Google Maps
     • Provider state management, 15+ screens, real-time order tracking
     • 500+ lines of tested code, deployed on Play Store
     • Tech: Flutter, Dart, Firebase, Provider, Google Maps API

  📱 SmartNotes — Collaborative Notes App
     • Real-time collaboration using Firebase Firestore streams
     • Rich text editor, offline support, push notifications
     • Clean architecture with BLoC pattern
     • Tech: Flutter, Dart, Firebase, BLoC, SharedPreferences
```

---

## ⏭️ WHAT'S NEXT?

After completing this roadmap:
```
→ "LEARN React Native"          — Cross-platform comparison
→ "PROJECT [your idea]"         — Build your dream app
→ "RESUME"                      — Optimize for Flutter roles
→ "INTERVIEW [company name]"    — Prep for Flutter-specific interviews
→ "COMPARE Flutter vs React Native vs Kotlin" — Technology decisions
```

---

