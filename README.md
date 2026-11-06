# Dolores AR

App turística con realidad aumentada para Dolores Hidalgo (GPS + brújula + cámara + modelo 3D + pasaporte).
Hecha con TDD. Desarrollo Móvil Integral · UTNG · Prof. Anastacio Rodríguez García.

## Arranque (VS Code)

```
flutter create . --project-name dolores_ar   # genera android/, ios/ (no pisa lib/ ni test/)
flutter pub get
flutter test                                  # sin teléfono, corre en segundos
flutter run                                   # en teléfono real; "Modo demo" funciona sin GPS
```

## Permisos (hazlo después de `flutter create .`)

**Android** · `android/app/src/main/AndroidManifest.xml`, dentro de `<manifest>` y antes de `<application>`:
```xml
<uses-permission android:name="android.permission.INTERNET"/>
<uses-permission android:name="android.permission.CAMERA"/>
<uses-permission android:name="android.permission.ACCESS_FINE_LOCATION"/>
<uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION"/>
<uses-feature android:name="android.hardware.camera" android:required="false"/>
```
En `android/app/build.gradle(.kts)` usa `minSdk = 24` (o `minSdkVersion 24`).

**iPhone** · `ios/Runner/Info.plist`:
```xml
<key>NSCameraUsageDescription</key>
<string>Usamos la cámara para mostrarte los lugares históricos a tu alrededor.</string>
<key>NSLocationWhenInUseUsageDescription</key>
<string>Usamos tu ubicación solo mientras la app está abierta, para saber qué lugares tienes cerca.</string>
```

## Estructura
- `lib/dominio/` matemáticas y reglas en Dart puro (geo, motor_ar, pasaporte, catálogo, contratos)
- `lib/datos/` fuentes reales (geolocator, flutter_compass) y simuladas (modo demo)
- `lib/presentacion/` ViewModel y pantallas (cámara, AR, inicio, modelo 3D)
- `test/` pruebas de geo, motor, pasaporte y ViewModel

Nota: las coordenadas de `catalogo.dart` son aproximadas; corrígelas con tu GPS en campo (Ronda 9).
