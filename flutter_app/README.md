# EchoFind - Flutter App

Encuentra objetos perdidos en tu casa con un simple audio.

## Descripción

Localiza rápidamente tus objetos perdidos dentro de tu hogar utilizando un audio grabado previamente como 'código de búsqueda'.

## Requisitos

- Flutter 3.x
- Dart 3.x
- Firebase project configurado

## Setup

1. Clona el repo
2. `flutter pub get`
3. Copia `.env.example` a `.env` y configura credenciales
4. `flutter run`

## Estructura

- `lib/` - Código fuente
  - `screens/` - Pantallas de la app
  - `services/` - Servicios (Firebase, API)
  - `models/` - Modelos de datos
  - `providers/` - Estado (Riverpod)
  - `config/` - Configuración
  - `utils/` - Utilidades

## Development

```bash
flutter run -d emulator  # Android
flutter run -d simulator # iOS
flutter run -d chrome    # Web
```

## Testing

```bash
flutter test
```

## Deployment

```bash
flutter build apk     # Android
flutter build ios     # iOS
flutter build web     # Web
```
