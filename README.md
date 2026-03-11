# EchoFind

Encuentra objetos perdidos en tu casa con un simple audio.

## Descripción

Localiza rápidamente tus objetos perdidos dentro de tu hogar utilizando un audio grabado previamente como 'código de búsqueda'.

**Público objetivo:** Hombres y mujeres de 25-45 años, propietarios de viviendas, con familias o mascotas, que a menudo pierden objetos pequeños dentro de su hogar. Frecuencia de uso: diaria/semanal.  
**Nicho:** Productividad del Hogar / Localización

## Características MVP

- Grabación de Audio: Permite al usuario grabar un audio corto como 'código de búsqueda'.
- Búsqueda por Audio: Permite al usuario reproducir el audio grabado y la app detecta si está cerca.
- Historial de Búsquedas: Guarda los audios grabados para futuras búsquedas.
- Gestión de Perfiles: Almacena información del usuario (nombre, email).
- Limitación de Audios: MVP - 3 audios guardados.

## Tech Stack

- **Mobile:** Flutter + Dart
- **Backend:** Cloud Functions for Firebase
- **Base de datos:** Cloud Firestore
- **Autenticación:** Firebase Auth
- **Hosting:** Firebase Hosting

## Estructura del proyecto

```
echofindapp/
├── flutter_app/          # App móvil Flutter
│   ├── lib/
│   │   ├── main.dart
│   │   ├── screens/      # Pantallas del MVP
│   │   ├── widgets/      # Componentes reutilizables
│   │   ├── providers/    # State management (Riverpod)
│   │   ├── repositories/ # Acceso a datos
│   │   └── models/       # Modelos de datos
│   ├── pubspec.yaml
│   └── .env.example
├── functions/            # Cloud Functions backend
│   ├── src/
│   │   ├── index.ts
│   │   ├── routes.ts
│   │   └── services/
│   ├── package.json
│   └── .env.example
├── docs/                 # Documentación
│   ├── FUNCTIONAL.md     # Documento funcional
│   ├── TECHNICAL.md      # Documento técnico
│   └── API.md            # Especificación API
└── README.md
```

## Setup

### Requisitos previos

- Flutter 3.x + Dart 3.x
- Node.js 18+
- Firebase CLI
- Git

### Instalación local

#### 1. Clonar el repo
```bash
git clone <repo-url>
cd echofindapp
```

#### 2. Setup de la app Flutter
```bash
cd flutter_app
flutter pub get
cp .env.example .env
# Editar .env con credenciales locales
flutter run
```

#### 3. Setup de Firebase Functions
```bash
cd functions
npm install
cp .env.example .env
# Editar .env con Firebase project ID y credenciales
npm run serve  # Emulador local
```

#### 4. Conectar Firebase

```bash
# En flutter_app/
dart pub global activate flutterfire_cli
flutterfire configure --project=<YOUR_PROJECT_ID>
```

## Desarrollo

### App Flutter

```bash
cd flutter_app
flutter run -d chrome   # Web
flutter run -d emulator # Android
flutter run -d simulator # iOS
```

### Backend Functions

```bash
cd functions
npm run serve  # Emulador local
npm run deploy # Deploy a Firebase
```

## Testing

```bash
# Unit tests
flutter test

# Integration tests
flutter test --tags=integration
```

## Despliegue

```bash
# Build y deploy a Firebase Hosting
flutter build web
firebase deploy --only hosting

# Deploy functions
firebase deploy --only functions
```

## Estructura de datos (Firestore)

### users
```
userId: string
├── email: string
├── createdAt: timestamp
└── lastActiveAt: timestamp
```

### main_items (adaptar según tu dominio)
```
itemId: string
├── userId: string (referencia)
├── title: string
├── description: string
├── createdAt: timestamp
└── metadata: map
```

## APIs disponibles

Ver [docs/API.md](docs/API.md) para especificación completa de endpoints.

## Contribuir

1. Fork el repo
2. Crea una rama para tu feature
3. Commit y push
4. Abre un pull request

## Licencia

MIT

## Contacto

Equipo de desarrollo
