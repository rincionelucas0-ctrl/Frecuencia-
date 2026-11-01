FRECUENCIA — PAQUETE PARA VERCEL
================================

ARCHIVOS
- index.html : web pública para los oyentes.
- admin.html : panel del locutor, compatible con micrófono de Android.
- config.js  : configuración compartida entre la web y el panel.
- servidor/  : archivos de ejemplo para preparar el servidor de audio MediaMTX.

ESTADO HONESTO
La web y el panel están preparados como frontend estático. La transmisión real NO funcionará hasta que exista un servidor de audio accesible públicamente, con HTTPS, WebRTC y configuración de red adecuada. Vercel publica los archivos de la web, pero no reemplaza ese servidor de audio.

PUBLICAR LA WEB EN VERCEL
1. Subí los archivos index.html, admin.html y config.js a un repositorio de GitHub (en la raíz del repositorio, no dentro de una carpeta adicional).
2. En Vercel elegí Add New Project e importá ese repositorio.
3. Deploy. No hace falta comando de build para estos archivos HTML estáticos.
4. La web pública será la URL que te entregue Vercel.
5. El panel se abre agregando /admin.html al final de esa URL.

CONFIGURAR AUDIO CUANDO HAYA SERVIDOR
1. Abrí config.js.
2. Cambiá serverUrl: "" por la URL HTTPS real del servidor, por ejemplo https://radio.tudominio.com.
3. Conservá channel: "frecuencia" salvo que configures otro canal en MediaMTX.
4. Volvé a publicar el proyecto en Vercel.
5. En /admin.html, poné la misma URL y canal, guardá y tocá SALIR EN VIVO.
6. Abrí la página pública en otro dispositivo y tocá ESCUCHAR EN VIVO.

SEGURIDAD
- No agregues claves privadas ni tokens secretos a config.js: ese archivo es público.
- No expongas un servidor de publicación sin autenticación real. El token del formulario solo se manda en el encabezado; no activa autenticación si el servidor no fue configurado para verificarlo.
- Usá HTTPS. El navegador exige un contexto seguro para permitir el micrófono.
- La transmisión por navegador puede requerir puertos UDP/TCP y configuración ICE según la red.

MÚSICA
Esta versión envía el micrófono. No mezcla automáticamente música almacenada en el teléfono. Para salir con voz y música a la vez hace falta una app de mezcla/fuente de audio compatible.
