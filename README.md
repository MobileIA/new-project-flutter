# Nuevo proyecto en Flutter
Pasos para la creación de un proyecto en Flutter.

1. Crear proyecto
```bash
flutter create name_project
```
2. Abrir emulador de iOS:
```bash
open -a Simulator
```
3. Agregar paquetes, abrir archivo: "pubspec.yaml" y debajo de dependencies agregar:
```yaml
transparent_image:
cached_network_image:
http:
```

# Como enviar información de un Screen a otro:
1. Configuración del screen para recibir:
```dart
class CenterDetailScreen extends StatefulWidget {

  final Commerce commerce;

  CenterDetailScreen({Key key, @required this.commerce}) : super(key: key);

  @override
  CenterDetailState createState() => new CenterDetailState();
}
```
2. Abrir pantalla con el objeto:
```dart
Navigator.push(
    context,
    MaterialPageRoute(
        builder: (context) => CenterDetailScreen(commerce: commerce),
    ),
);
```

# Otras Librerias:
- Custom Bottom Bar Animate:
https://pub.dev/packages/bottom_navy_bar
- Simple Animations:
https://pub.dev/packages/simple_animations
- Animación de ListViews:
https://pub.dev/packages/flutter_staggered_animations
- Carrousel de imgenes:
https://pub.dev/packages/carousel_slider
- Listado con funcionalidad con Slides para los costados, para eliminar y/o agregar otras acciones:
https://pub.dev/packages/flutter_slidable



LInks para ver:
https://flutter.dev/docs/cookbook/lists/mixed-list
https://flutter.dev/docs/cookbook/lists/floating-app-bar
https://flutter.dev/docs/cookbook/maintenance/error-reporting
https://flutter.dev/docs/cookbook/navigation/hero-animations
https://flutter.dev/docs/cookbook/navigation/navigation-basics
https://flutter.dev/docs/cookbook/navigation/named-routes
https://flutter.dev/docs/cookbook/navigation/navigate-with-arguments
https://flutter.dev/docs/cookbook/navigation/returning-data
https://flutter.dev/docs/cookbook/navigation/passing-data
https://flutter.dev/docs/cookbook/networking/fetch-data
https://flutter.dev/docs/cookbook/networking/send-data
https://flutter.dev/docs/cookbook/networking/authenticated-requests
https://flutter.dev/docs/cookbook/networking/background-parsing
https://flutter.dev/docs/cookbook/networking/web-sockets
https://flutter.dev/docs/cookbook/persistence/sqlite
https://flutter.dev/docs/cookbook/persistence/reading-writing-files
https://flutter.dev/docs/cookbook/persistence/key-value
https://flutter.dev/docs/cookbook/plugins/play-video
https://flutter.dev/docs/cookbook/plugins/picture-using-camera
https://flutter.dev/docs/cookbook/testing/integration/introduction
https://flutter.dev/docs/cookbook/testing/integration/profiling
https://flutter.dev/docs/cookbook/testing/integration/scrolling
https://flutter.dev/docs/cookbook/testing/unit/introduction
https://flutter.dev/docs/cookbook/testing/unit/mocking
https://flutter.dev/docs/cookbook/testing/widget/introduction
https://flutter.dev/docs/cookbook/testing/widget/finders
https://flutter.dev/docs/cookbook/testing/widget/tap-drag
https://pub.dev/packages/flutter_facebook_login
https://pub.dev/packages/firebase_analytics
https://pub.dev/packages/firebase_messaging
https://flutter-es.io/docs/development/packages-and-plugins/developing-packages
https://flutter-es.io/docs/development/ui/interactive
https://flutter-es.io/docs/development/ui/layout
https://flutter.dev/docs/deployment/android
https://pub.dev/packages/googleapis
https://dev.to/acanteror/chopper-retrofit-para-flutter-1-lo-basico-3nk
https://medium.com/free-code-camp/app-architecture-mvvm-in-flutter-using-dart-streams-26f6bd6ae4b6
https://pub.dev/packages/intro_slider
https://pub.dev/packages/intro_views_flutter
https://pub.dev/packages/modal_progress_hud
https://pub.dev/packages/progress_dialog