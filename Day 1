## 📘 Flutter Widget Notes

### 1. **StatelessWidget**

* A widget that **does not store any state** (immutable).
* Used for static content that doesn’t change dynamically.

```dart
class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Text('Rasim Rockers'),
    );
  }
}
```

* `StatelessWidget` is ideal when the UI doesn't need to update after it's built.

---

### 2. **StatefulWidget**

* A widget that can **hold and manage state** (mutable).
* Use `setState()` to update the UI when internal state changes.

```dart
class MyApp extends StatefulWidget {
  @override
  State<MyApp> createState() => _MyAppState();
}

class _MyAppState extends State<MyApp> {
  String Name = 'Raja Ram';

  void clickme() {
    setState(() {
      Name = 'Rasim Rockers';
    });
  }

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
        home: Column(
      children: [
        Text('$Name'),
        FloatingActionButton(child: Icon(Icons.add), onPressed: clickme),
      ],
    ));
  }
}
```

---

### 3. **AppBar Basics**

#### Basic AppBar with title:

```dart
appBar: AppBar(title: Text("Rasim Rockers"))
```

#### Dynamic AppBar title with `setState()`:

* Updates the AppBar title when the menu icon is pressed.

```dart
appBar: AppBar(
  leading: IconButton(
    icon: Icon(Icons.menu),
    onPressed: () {
      setState(() {
        Name = 'Pooja';
      });
    },
  ),
  title: Text("$Name"),
)
```

---

### 4. **AppBar with Actions (Icons on the Right)**

```dart
appBar: AppBar(
  title: Text(Name),
  actions: [
    IconButton(icon: Icon(Icons.more), onPressed: () {}),
    IconButton(icon: Icon(Icons.search), onPressed: () {}),
  ],
)
```

* Icons like More, Search, Home, etc., can be added in the `actions` list.

---

### 5. **AppBar with Bottom Widget**

Use `PreferredSize` to add a widget below the AppBar.

```dart
bottom: PreferredSize(
  preferredSize: Size.fromHeight(75.0),
  child: Container(
    color: Colors.yellow,
    height: 75.0,
    child: Center(
      child: Text(
        'Rasim Rockers',
        style: TextStyle(color: Colors.white, fontSize: 25.0),
      ),
    ),
  ),
)
```

* Useful for adding tabs or banners under the AppBar.

---

### 6. **Complete Example with Body and Stylized Bottom AppBar**

```dart
body: Center(
  child: Text(
    'RajaRam',
    style: TextStyle(fontSize: 30.0, color: Colors.red),
  ),
)
```

* `body` holds the main screen content below the AppBar.

---

## 📝 Summary Table

| Widget Type     | Use Case                       | Updates UI?              | Example           |
| --------------- | ------------------------------ | ------------------------ | ----------------- |
| StatelessWidget | Static content                 | ❌ No                     | `Text('Hello')`   |
| StatefulWidget  | Dynamic content with state     | ✅ Yes                    | `setState()`      |
| AppBar          | Top bar of Scaffold            | ✅ Yes (if state changes) | `AppBar(...)`     |
| IconButton      | Clickable icon                 | ✅ Yes                    | `IconButton(...)` |
| PreferredSize   | Custom bottom widget in AppBar | ✅ Yes                    | `bottom:`         |

---

