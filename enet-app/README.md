# Enet Fiber Perú — App Android

App Android (WebView) que envuelve el sitio https://enet.com.pe/

## Qué incluye
- Splash screen con los colores de la marca
- Barra de progreso de carga
- Pantalla de "sin conexión" con botón de reintentar
- Deslizar hacia abajo para refrescar
- Botón "atrás" del teléfono navega dentro del sitio (no cierra la app de golpe)
- Enlaces a WhatsApp, Facebook, Instagram y TikTok se abren en sus propias apps
- Reproducción de video en pantalla completa (para los canales en vivo de Enet Play)
- Solo carga páginas dentro de enet.com.pe; cualquier otro enlace se abre externamente

## Cómo abrir el proyecto
1. Instala **Android Studio** (última versión estable): https://developer.android.com/studio
2. Abre Android Studio → "Open" → selecciona la carpeta `enet-app`
3. Espera a que sincronice Gradle (la primera vez descarga dependencias, requiere internet)
4. Conecta un celular Android (o usa un emulador) y presiona ▶ Run

## Reemplazar el ícono por el logo real
Los íconos actuales son un marcador de posición con los colores de la marca (azul, celeste, amarillo).
Para usar tu logo real:
1. En Android Studio: clic derecho en `app/res` → New → Image Asset
2. Selecciona tu archivo (por ejemplo `LOGO_ENET.png` o `ENET_BLANCO_OK.png`)
3. Genera los íconos — reemplazará automáticamente los archivos en `mipmap-*`

## Cambiar el paquete (applicationId)
Antes de publicar en Play Store, si quieres otro identificador distinto a `pe.com.enet.app`,
cámbialo en `app/build.gradle.kts` (`applicationId`) y en la carpeta de paquete de `MainActivity.kt`.
Una vez publicado en la Play Store, el paquete **no se puede cambiar**.

## Generar el APK / AAB para publicar
- Build → Generate Signed App Bundle / APK
- Necesitarás crear una clave de firma (keystore) la primera vez — Android Studio te guía en el proceso
- Para subir a Play Store se requiere el formato **AAB** (Android App Bundle)

## Cuenta de Google Play Console
Para publicar necesitas una cuenta de desarrollador (pago único de $25 USD):
https://play.google.com/console
