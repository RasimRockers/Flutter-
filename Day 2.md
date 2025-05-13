```dart
import 'package:flutter/material.dart';

void main() {
  runApp(MaterialApp(
    home: MyApp()));
}

class MyApp extends StatefulWidget {                                  
  const MyApp({super.key});

  @override
  State<MyApp> createState() => _MyAppState();
}

class _MyAppState extends State<MyApp> {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
    backgroundColor: Color.fromARGB(255, 221, 218, 220),
    appBar:AppBar(
      backgroundColor: Colors.red,
      title: Text("BEC Demo"),
    ),
    drawer: Drawer(
      child: ListView(
        children: [
          DrawerHeader(
            child: Text("Flutter Widgets",
            style: TextStyle(fontSize: 35,fontWeight: FontWeight.bold,color: Colors.white,),),
            decoration: BoxDecoration(color: Color.fromARGB(255, 219, 48, 36)),
          ),
          Divider(height: 0.5,),
          ListTile(
            title: Text("Navigation Bar"),
            onTap: (){
              Navigator.of(context).push(MaterialPageRoute(builder: (context)=> nextpage()));
            },
          ), 
          Divider(height: 0.5,),
          ListTile(
            title: Text("FloatingActionButton"),
            onTap: (){
              Navigator.of(context).push(MaterialPageRoute(builder: (context)=> FloatingActionButtonpage()));
            },
          ),
          Divider(height: 0.5,),
          ListTile(
            title: Text("BottomNavigationBar"),
            onTap: (){
              Navigator.of(context).push(MaterialPageRoute(builder: (context)=> BottomNavigationBarpage()));
            },
          ),
          Divider(height: 0.5,),
          ListTile(
            title: Text("Image"),
            onTap: (){
              Navigator.of(context).push(MaterialPageRoute(builder: (context)=> Imagepage()));
            },
          ),
          Divider(height: 0.5,),
          ListTile(
            title: Text("Buttons"),
            onTap: (){
              Navigator.of(context).push(MaterialPageRoute(builder: (context)=> Buttonspage()));
            },),
            Divider(height: 0.5,),
          ListTile(
            title: Text("Icons"),
            onTap: (){
              Navigator.of(context).push(MaterialPageRoute(builder: (context)=> Iconspage()));
            },
          ), 
        ],
      ),
    ),
    );
  }
}

class nextpage extends StatelessWidget {
  const nextpage({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text("Navigatioan To Next Page"),
      ),
    );
  }
}

class FloatingActionButtonpage extends StatelessWidget {
  const FloatingActionButtonpage({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text("FloatingActionButton"),
      ),
      floatingActionButton: FloatingActionButton(
        child: Icon(Icons.add),
        onPressed: (){

        },
      ),
      floatingActionButtonLocation: FloatingActionButtonLocation.centerDocked,
      
    );
  }
}


class BottomNavigationBarpage extends StatefulWidget {
  const BottomNavigationBarpage({super.key});

  @override
  State<BottomNavigationBarpage> createState() => _BottomNavigationBarpageState();
}

class _BottomNavigationBarpageState extends State<BottomNavigationBarpage> {
  int _press = 0;
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text("BottomNavigationBar"),
      ),
      bottomNavigationBar: BottomNavigationBar(
        currentIndex: _press,
        items: [
          BottomNavigationBarItem(
            label: "Home",
            icon: Icon(Icons.home),
          ),
          BottomNavigationBarItem(
            label: "Search",
            icon: Icon(Icons.search),
          ),
        ],
        onTap: (int Index){
          setState(() {
                _press = Index;
                    }); 
        },
      ),
    );
  }
}

class Imagepage extends StatelessWidget {
  const Imagepage({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text("Image"),
      ),
      body : Center( 
        child :Column(
          crossAxisAlignment: CrossAxisAlignment.center,
          mainAxisAlignment: MainAxisAlignment.center,
        children: [Image.network('https://as2.ftcdn.net/v2/jpg/05/60/89/51/1000_F_560895109_gDZfUM1GDqw8CYdJIg4YF9xl4ByCFSat.jpg',height: 250,width: 175,),]
      ),
      ),
      
    );
  }
}


class Buttonspage extends StatefulWidget {
  const Buttonspage({super.key});

  @override
  State<Buttonspage> createState() => _ButtonspageState();
}

class _ButtonspageState extends State<Buttonspage> {
  bool _isSwitched = false;
  double _sliderValue = 20;
  bool _isChecked = false;
  int _selectedRadio = 1;
  String _dropdownValue = 'One';
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text("Buttons"),
      ),
      
      body: SingleChildScrollView(
        child: Padding(
          padding: const EdgeInsets.all(16.0),
          child: Column(
            children: [ ElevatedButton(onPressed: () {}, child: Text('Elevated Button')),
              OutlinedButton(onPressed: () {}, child: Text('Outlined Button')),
              TextButton(onPressed: () {}, child: Text('Text Button')),

              Divider(),

              TextField(decoration: InputDecoration(labelText: 'Enter text')),
              Switch(
                value: _isSwitched,
                onChanged: (val) => setState(() => _isSwitched = val),
              ),
              Checkbox(
                value: _isChecked,
                onChanged: (val) => setState(() => _isChecked = val!),
              ),
              Radio(
                value: 1,
                groupValue: _selectedRadio,
                onChanged: (val) => setState(() => _selectedRadio = val!),
              ),
              Slider(
                value: _sliderValue,
                min: 0,
                max: 100,
                onChanged: (val) => setState(() => _sliderValue = val),
              ),
              DropdownButton<String>(
                value: _dropdownValue,
                items: <String>['One', 'Two', 'Three']
                    .map((e) => DropdownMenuItem(child: Text(e), value: e))
                    .toList(),
                onChanged: (val) => setState(() => _dropdownValue = val!),
              ),
              ],),
              ),
              ),

    );
  }
}

class Iconspage extends StatefulWidget {
  const Iconspage({super.key});

  @override
  State<Iconspage> createState() => _IconspageState();
}

class _IconspageState extends State<Iconspage> {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text("Icons"),
      ),
      body: SingleChildScrollView(
        child: Column(
        children: [
          FloatingActionButton(
            child: Icon(Icons.add),
            onPressed: (){},
          ),
          FloatingActionButton(
            child: Icon(Icons.remove),
            onPressed: (){},
          ),
          FloatingActionButton(
            child: Icon(Icons.home),
            onPressed: (){},
          ),
          FloatingActionButton(
            child: Icon(Icons.search),
            onPressed: (){},
          ),
          FloatingActionButton(
            child: Icon(Icons.people),
            onPressed: (){},
          ),
          FloatingActionButton(
            child: Icon(Icons.move_down),
            onPressed: (){},
          ),
          FloatingActionButton(
            child: Icon(Icons.move_up),
            onPressed: (){},
          ),FloatingActionButton(
            child: Icon(Icons.inbox),
            onPressed: (){},
          ),
          FloatingActionButton(
            child: Icon(Icons.telegram),
            onPressed: (){},
          ),
          FloatingActionButton(
            child: Icon(Icons.catching_pokemon),
            onPressed: (){},
          ),
          FloatingActionButton(
            child: Icon(Icons.chat_bubble),
            onPressed: (){},
          ),
          FloatingActionButton(
            child: Icon(Icons.cell_tower),
            onPressed: (){},
          ),
          FloatingActionButton(
            child: Icon(Icons.cabin),
            onPressed: (){},
          ),
        ],
      ),
      ),
    );
  }
}
```
