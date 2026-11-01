FRECUENCIA RADIO ONLINE — DOCUMENTACIÓN DE PRUEBA
================================================

ARCHIVOS
- index.html: página pública de oyentes (LiveKit).
- admin.html: panel del DJ (LiveKit, micrófono y mezcla local con un archivo de música).
- config.js: sala y servidor de tokens de desarrollo.

PUBLICAR EN VERCEL
1. Subí estos tres archivos a la raíz del proyecto existente, conservando sus nombres.
2. No reemplaces otros archivos del proyecto que no estén incluidos en este paquete.
3. Publicá un nuevo deployment.
4. Panel DJ: /admin.html. Oyentes: /.

TRANSMISIÓN
- La web y el panel usan LiveKit Cloud Development Token Server y la sala configurada como “frecuencia”.
- En el panel, iniciá la transmisión y aceptá el permiso del micrófono.
- Podés ajustar el volumen del micrófono, silenciarlo y seleccionar un archivo de audio local para mezclarlo con la voz.
- En otro dispositivo, abrí la web pública y tocá ESCUCHAR EN VIVO.
- Usá auriculares para evitar acoples. La reproducción puede requerir interacción del usuario por las políticas del navegador.

SEGURIDAD Y LIMITACIONES
- El ID del servidor de tokens de desarrollo está expuesto en config.js. Es exclusivamente para pruebas; no es apropiado para una radio pública abierta.
- No hay API Secret en el frontend. Para producción hace falta un backend propio que emita tokens con permisos limitados y autenticación del DJ.
- La música local se mezcla en el navegador del DJ mientras la pestaña permanece abierta; probá el formato de audio en tu Android.
- La reconexión automática del oyente vuelve a solicitar credenciales al servidor de desarrollo.
- Este paquete no implementa todavía chat, votaciones, donaciones, notificaciones push, entrevistas ni programación.
- No se debe considerar validada la transmisión hasta probar audio real entre dos dispositivos y confirmar permisos/credenciales de LiveKit.
