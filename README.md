# Xperia Battery Companion — app Android complementaria

**Autor:** SuperCreeper'sXperiaTeam  
**Aplicación:** Android nativa, interfaz en español y widget de pantalla de inicio.

## Integración con Magisk
La aplicación lee con autorización root el CSV generado por el módulo instalado en `/data/local/tmp/xperia_battery_companion/battery_log.csv`. El módulo 1.2 ya registra muestras y genera las alertas de batería baja/crítica. La aplicación muestra el historial, calcula una autonomía aproximada a partir de las muestras disponibles y ofrece un widget actualizable.

## Requisitos para compilar
- Android Studio, JDK 17 y Android SDK 34.
- Módulo Xperia Battery Companion 1.2 instalado en Magisk.
- Conceder acceso root a la aplicación cuando Magisk lo solicite.

## Compilar
1. Extrae el ZIP y abre la carpeta `XperiaBatteryCompanionApp` en Android Studio.
2. Espera a que Gradle sincronice.
3. Selecciona **Build > Build APK(s)**.
4. Instala el APK de `app/build/outputs/apk/debug/`.
5. Para añadir el widget, mantén pulsada la pantalla de inicio y entra en Widgets > Batería Xperia.

## Limitaciones importantes
- Este entorno no tiene Android SDK/Gradle instalados, así que no se ha podido generar ni probar un APK aquí. Este ZIP es código fuente listo para abrir en Android Studio, no un APK.
- La estimación requiere al menos 30 minutos de muestras y una caída detectable del porcentaje. Es aproximada.
- El widget del sistema se actualiza periódicamente (Android puede retrasar las actualizaciones); al tocarlo abre la aplicación.
- Las alertas automáticas las emite el módulo Magisk; la aplicación incluye además una notificación de prueba.
- La conversión raw/100 sigue siendo experimental y no equivale a una calibración real de la batería.


## Icono de la app
Se ha añadido el dibujo original de Creeper sin modificar como `app/src/main/res/drawable-nodpi/creeper_icon.png` y se ha configurado como icono de la aplicación en el manifiesto.
