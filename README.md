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

## Compilar el APK sin instalar nada (GitHub Actions)
Este proyecto incluye un workflow (`.github/workflows/build-apk.yml`) que compila el APK
automáticamente en la nube. Pasos:

1. Crea una cuenta gratis en https://github.com (si no tienes una)
2. Crea un repositorio nuevo: botón verde "New" → nómbralo, por ejemplo `enet-fiber-app` → puede ser privado → "Create repository"
3. En la página del repo recién creado, usa la opción "uploading an existing file" (o arrastra la carpeta completa `enet-app` con drag-and-drop al navegador)
4. Sube **todos** los archivos y carpetas del proyecto (incluyendo la carpeta oculta `.github`) y confirma el commit
5. Ve a la pestaña **Actions** de tu repositorio — el workflow "Compilar APK" empieza a correr solo (tarda 2-4 minutos)
6. Cuando termine (ícono verde ✔), entra a esa ejecución y baja hasta "Artifacts" → descarga `enet-fiber-app-debug` (es un .zip que contiene el `app-debug.apk`)
7. Pasa ese .apk a tu celular (por WhatsApp, Drive, USB, etc.) y ábrelo para instalarlo — recuerda aceptar "instalar apps de fuentes desconocidas"

> Nota: este APK generado así es de **depuración** (debug), sirve perfecto para probar la app pero no es el que se sube a la Play Store — para eso se necesita un AAB firmado con un keystore (ver Android Studio: Build → Generate Signed App Bundle).

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
