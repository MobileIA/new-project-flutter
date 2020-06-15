# Nuevo proyecto en Flutter
Pasos para la creación de un proyecto en Flutter.

* Activar commands:
```bash
source $HOME/.bash_profile
```

1. Crear proyecto
```bash
flutter create --org com.agencycoda name_project
```
2. Abrir emulador de iOS:
```bash
open -a Simulator
```
3. Agregar paquetes, abrir archivo: "pubspec.yaml" y debajo de dependencies agregar:
```yaml
flutter_clean_architecture: ^3.0.2
transparent_image:
cached_network_image:
http:
```

# Estructura de carpetas:
```folders
screens/
tabs/
widgets/
utils/
```

# Como Crear una pantalla/Screen:
1. Crear archivo carpeta: 'screens/name_screen'
2. Crear archivo Controller: 'screens/name_screen/name.controller.dart'
```dart
import 'package:flutter_clean_architecture/flutter_clean_architecture.dart';

class NameController extends Controller {
  
  @override
  void initListeners() {
    // TODO: implement initListeners
  }

}
```
3. Crear archivo View: 'screens/name_screen/name.view.dart'
```dart

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

# Utilizando Chooper (HTTP)
1. Incluir libreria:
```dart
dependencies:
  chopper: ^3.0.2

dev_dependencies:
  build_runner:
  chopper_generator: ^3.0.4
```
2. Ejecutar builder:
```bash
flutter packages pub run build_runner watch
```

# Producción: Compilar Android
1. Crear carpeta "certificates" dentro del proyecto.
2. Crear KeyStore
```bash
keytool -genkey -v -keystore key.jks -keyalg RSA -keysize 2048 -validity 10000 -alias key
```
3. Exportar SHA1:
```bash
keytool -list -v \
-alias myalias -keystore key.jks
```
4. Crear archivo: "/android/key.properties"
```txt
storePassword=password
keyPassword=password
keyAlias=myalias
storeFile=../../certificates/key.jks
```
5. Abrimos archivo "android/app/build.gradle" y arriba de android {
```txt
def keystoreProperties = new Properties()
def keystorePropertiesFile = rootProject.file('key.properties')
if (keystorePropertiesFile.exists()) {
    keystoreProperties.load(new FileInputStream(keystorePropertiesFile))
}
```
6. Reemplazamos buildTyps:
```txt
    signingConfigs {
        release {
            keyAlias keystoreProperties['keyAlias']
            keyPassword keystoreProperties['keyPassword']
            storeFile file(keystoreProperties['storeFile'])
            storePassword keystoreProperties['storePassword']
        }
    }
    buildTypes {
        release {
            signingConfig signingConfigs.release
        }
    }
```
7. Generar APK:
```bash
flutter build apk --release
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
https://pub.dev/packages/intro_views_flutter#-readme-tab-
https://pub.dev/packages/fancy_on_boarding
https://pub.dev/packages/page_view_indicators
https://pub.dev/packages/smooth_page_indicator
https://github.com/AbdulRahmanAlHamali/flutter_pagewise

https://blog.geekyants.com/building-beautiful-ui-with-flutter-3b54ef6947a8
https://medium.com/flutter/zero-to-one-with-flutter-part-two-5aa2f06655cb
https://proandroiddev.com/animations-in-flutter-6e02ee91a0b2
https://github.com/ariedov/flutter_snaplist
https://github.com/faob-dev/folding_cell
https://github.com/aagarwal1012/Liquid-Pull-To-Refresh
https://pub.dev/packages/slide_container
https://github.com/mcrovero/rubber
https://github.com/LanarsInc/direct-select-flutter
https://github.com/xsahil03x/before_after
https://github.com/vintage/scratcher
https://github.com/jaweii/Flutter_beautiful_popup
https://github.com/Origogi/Flutter-Credit-Card-Input-Form
https://github.com/Rahiche/stepper_touch
https://github.com/AndreHaueisen/flushbar
https://github.com/duytq94/flutter-fb-reactions-animation
https://github.com/Ivaskuu/tinder_cards
https://github.com/xqwzts/flutter_radial_menu
https://fidev.io/tickets-challenge-parallax/
https://github.com/Ali-Azmoud/flutter_xlider
https://github.com/rvamsikrishna/flutter_fluid_slider
https://github.com/boeledi/RangeSlider
https://github.com/pedromassango/titled_navigation_bar
https://github.com/pedromassango/bottom_navy_bar
https://github.com/imaNNeoFighT/circular_bottom_navigation
https://github.com/tunitowen/fancy_bottom_navigation
https://github.com/Dn-a/flutter_inner_drawer
https://github.com/RafaelBarbosatec/hidden_drawer_menu
https://github.com/fluttercommunity/flutter_sticky_headers
https://github.com/letsar/flutter_sticky_header
https://github.com/TatsuUkraine/flutter_sticky_infinite_list
https://github.com/dengyin2000/dynamic_widget
https://github.com/NearHuscarl/flutter_login
https://github.com/GeekyAnts/flutter-login-home-animation
https://github.com/aleksanderwozniak/table_calendar
https://github.com/dooboolab/flutter_calendar_carousel
https://github.com/pinkfish/flutter_calendar
https://github.com/skkallayath/photofilters
https://github.com/iamSahdeep/liquid_swipe_flutter
https://github.com/i-protoss/wave // Animaciones de olas
https://github.com/hnvn/flutter_shimmer
https://github.com/roughike/page-transformer
https://github.com/tiagojencmartins/unicornspeeddial
https://github.com/long1eu/material_pickers
https://github.com/hugocbpassos/drag_select_grid_view
https://github.com/simformsolutions/flutter_showcaseview
https://github.com/aliyigitbireroglu/flutter-flick
https://github.com/rvamsikrishna/inview_notifier_list
https://github.com/quire-io/scroll-to-index
https://github.com/hanshengchiu/reorderables
https://github.com/pulyaevskiy/parallax-image
https://github.com/renancaraujo/photo_view
https://github.com/hnvn/flutter_image_cropper
https://github.com/Sh1d0w/multi_image_picker
https://pub.dev/packages/expandable_bottom_bar

https://github.com/Solido/awesome-flutter

https://github.com/xqwzts/flutter_circular_chart
https://github.com/tomialagbe/flutter_ui_challenges
https://github.com/BigMarco254/FlutterTodo
