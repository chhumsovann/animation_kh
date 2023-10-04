# Animation Kh library

Animation Kh make your application have animation looking smoothly and beautifully.
This is a animation library for Flutter that provides animation on widget and list that you can use in your app.
Animation Kh is opensource library developed by <a href="https://www.youtube.com/@vann-dev">Vann Dev</a>

<br>

![Demo](lib/demo/demo_animation_kh.gif)

<br>

## Installation

1. Add the latest version of package to your pubspec.yaml (and run`dart pub get`):
```yaml
dependencies:
  animation_kh: ^0.0.1
```
2. Import the package and use it in your Flutter App.
```dart
import 'package:animation_kh/animation_kh.dart';
```

## Example
For example, create animation on widget

```dart

class MyClass extends StatefulWidget {
  const MyClass({Key? key}) : super(key: key);

  @override
  State<MyClass> createState() => _MyClassState();
}

class _MyClassState extends State<MyClass> with TickerProviderStateMixin {
  AnimationController? animationController;

  @override
  void initState() {
    super.initState();
    animationController = AnimationController(
      vsync: this,
      duration: const Duration(milliseconds: 500),
    );
  }

  @override
  Widget build(BuildContext context) {
    return Column(
      children: [
        /// animation on title or text widget
        AnimationKh(
          animationController: animationController,
          slideDirection: SlideDirection.fromRight,
          child: Text("Hello world"),
        ),

        /// animation on icon widget
        AnimationKh(
          animationController: animationController,
          slideDirection: SlideDirection.fromRight,
          child: Padding(
            padding: const EdgeInsets.only(right: 12),
            child: CircleAvatar(
              backgroundColor: Theme.of(context).colorFF2A2(context),
              child: IconButton(
                padding: const EdgeInsets.all(0),
                onPressed: () {},
                icon: Icon(Icons.favorite),
              ),
            ),
          ),
        ),
      ],
    );
  }
}
```

## Example
For example, create animation on list

```dart
class MyClass extends StatefulWidget {
  const MyClass({Key? key}) : super(key: key);

  @override
  State<MyClass> createState() => _MyClassState();
}

class _MyClassState extends State<MyClass> with TickerProviderStateMixin {
  AnimationController? animationController;

  @override
  void initState() {
    super.initState();
    animationController = AnimationController(
      vsync: this,
      duration: const Duration(milliseconds: 500),
    );
  }

  @override
  Widget build(BuildContext context) {
    return ListView(
      children: List.generate(
        10,
            (index) => AnimationKh(
          animationController: animationController,
          position: index,
          slideDirection: SlideDirection.fromBottom,
          itemCount: 10,
          child: ListTile(
            leading: const Icon(Icons.home),
            title: Text(index.toString()),
          ),
        ),
      ),
    );
  }
}

```

## LICENSE

