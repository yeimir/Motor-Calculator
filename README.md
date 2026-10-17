# Protecciones Motores (APK)

Proyecto Capacitor listo para generar el APK. La app está en `www/index.html`.

## Opción A: sin PC potente (GitHub Actions)
1. Crea un repositorio nuevo en GitHub y sube todo el contenido de esta carpeta (incluida la carpeta oculta `.github`).
2. Ve a la pestaña **Actions** → **Build APK** → **Run workflow** (también corre solo al hacer push a `main`).
3. Al terminar, abre la ejecución y descarga el artefacto **protecciones-motores-apk** (ZIP con `app-debug.apk`).
4. Pasa el APK al teléfono e instálalo (permite "instalar apps desconocidas").

## Opción B: en tu PC
Requisitos: Node 20+, JDK 17 y Android SDK (Android Studio).
```
npm install
npx cap add android
npx cap sync android
cd android && ./gradlew assembleDebug
```
APK en `android/app/build/outputs/apk/debug/app-debug.apk`.
También puedes abrirlo con `npx cap open android` y usar Build > Build APK.

## Actualizar la app
Edita `www/index.html`, luego `npx cap sync android` y vuelve a compilar (o haz push si usas Actions).

## Versión de publicación (Play Store)
El APK debug sirve para uso propio. Para publicar necesitas un keystore y `./gradlew bundleRelease` firmado.

## Icono
Coloca `assets/icon.png` (1024×1024) y ejecuta `npx @capacitor/assets generate --android`.
