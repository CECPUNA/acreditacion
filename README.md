# Portal de autoevaluación · Ciencias Políticas UNA

Sitio estático, responsive, sin dependencias, sin compilación y sin analítica. Diseño móvil, navegación accesible, FAQ, novedades, documentos y encuestas configurables. No incluye formularios que recojan datos ni un backend.

## Publicar en GitHub Pages
1. Descomprimí el paquete.
2. Subí `index.html` y `config.js` al directorio que vas a publicar del repositorio. Conservá ambos juntos. Si el repositorio ya tiene un sitio, NO reemplaces su index: usá una carpeta como `acreditacion/`.
3. En Settings → Pages elegí Deploy from a branch, la rama correspondiente y el directorio raíz (o /docs si colocaste los archivos allí). Si el repositorio ya tiene otro método de despliegue, conservá su configuración.
4. Abrí la URL que indique GitHub Pages y probala en celular y computadora.
5. Generá el QR con la URL definitiva, no con un enlace al repositorio. Probá el QR impreso antes de distribuirlo e incluí la dirección legible.

## Editar contenidos
Abrí config.js. No cambies `window.PORTAL_CONFIG`. Usá comillas y comas válidas de JavaScript. Los arrays vacíos muestran avisos claros; no hay encuestas, integrantes ni avances ficticios.

Ejemplo de integrante, dentro de `integrantes: [...]`:
```js
{ nombre: "NOMBRE AUTORIZADO", funcion: "Representación estudiantil" }
```
Ejemplo de encuesta, dentro de `encuestas: [...]`:
```js
{
  titulo: "TÍTULO VALIDADO",
  descripcion: "Finalidad del instrumento aprobado.",
  destinatarios: "Población definida por el comité",
  cierre: "Fecha confirmada",
  duracion: "Tiempo comprobado",
  privacidad: "Explicar si identifica participantes o recoge correos. No prometer anonimato sin verificar.",
  responsable: "Dependencia que administra las respuestas",
  estado: "Abierta",
  activa: true,
  url: "ENLACE_HTTPS_REAL_DEL_FORMULARIO"
}
```
Con `activa: false` el enlace no queda disponible. El sitio no cierra formularios automáticamente: actualizar estado y configuración del formulario al vencer el plazo.

Documento, dentro de `documentos: [...]`:
```js
{ titulo: "Malla curricular", detalle: "Versión vigente · PDF", url: "ENLACE_HTTPS_REAL" }
```
Novedad, dentro de `novedades: [...]` (se muestran en el orden escrito):
```js
{ fecha: "FECHA CONFIRMADA", titulo: "TÍTULO", descripcion: "Avance autorizado y verificable.", url: "" }
```
Actualizá `actualizado` manualmente con la fecha de revisión editorial; no se utiliza la fecha de visita del usuario.

## Antes de lanzar
- Acordar con el comité el carácter del portal, responsables y aprobación editorial. Revisar y ajustar el aviso inicial cuando corresponda; no atribuir aval institucional sin autorización.
- Confirmar denominación de carrera/unidad y autorización de difusión de integrantes.
- Publicar modalidad/fase/estado únicamente con respaldo; enlazar comunicación pública si existe.
- Revisar accesibilidad, permisos de documentos y enlaces desde una sesión sin iniciar.
- Validar formularios, muestra, destinatarios y condiciones de privacidad con el comité.
- No subir respuestas individuales, CI, matrículas, correos, actas reservadas, credenciales ni tokens al repositorio, incluso si no se enlazan desde la página.
- Publicar solo resultados agregados autorizados. No confundir buzón voluntario con encuesta representativa.
- Agregar contacto institucional autorizado.
- No se usan logos ni sellos no proporcionados; la marca gráfica es genérica.
- Los formularios se abren en el proveedor externo y tienen sus propias políticas. El portal no recoge respuestas.

## Estructura
- index.html: interfaz, estilos y lógica de renderizado.
- config.js: contenido editable, siempre público.
- README.md: instrucciones.

No requiere instalar paquetes, claves API, base de datos ni panel administrador. No incluye un QR porque todavía no hay URL definitiva. No fue publicado ni modificado ningún repositorio desde esta conversación.
