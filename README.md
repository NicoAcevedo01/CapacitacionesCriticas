# Control de Capacitaciones

Aplicación web liviana (HTML + JS, sin backend) para consultar qué capacitaciones de seguridad
(Trabajos en caliente, Espacio confinado, Trabajo en altura, Corte y Bloqueo) tiene cada
colaborador, su estado y fecha, a partir de la tabla "Base" en Excel.

## Cómo probarla en tu computadora

1. Abrí `index.html` con doble clic (funciona sin servidor).
2. Va a mostrar datos de ejemplo. Tocá **"Cargar Excel (Base)"** y elegí tu archivo `.xlsx`
   real para reemplazar los datos de demo.
3. Los datos quedan guardados en el navegador (localStorage), así que la próxima vez que abras
   la página no hace falta volver a cargar el Excel — hasta que subas uno nuevo.

## Columnas que espera el Excel (hoja "Base")

| Columna | Uso |
|---|---|
| `PANADERIA` | Filtro de sede |
| `SECTOR` | Filtro de sector/puesto |
| `LEGAJO` | Búsqueda por legajo |
| `NOMBRE Y APELLIDO` | Búsqueda por nombre |
| `Capacitacion` | Nombre de la capacitación (una fila por capacitación y colaborador) |
| `Requiere capacitacion` | `SI` / `NO` |
| `Estado capacitacion` | `SIN PROGRAMAR` / `PROGRAMADO` / `VIGENTE` / `N/A` |
| `FECHA` | Fecha asociada a la capacitación |
| `VIGENCIA2` | Vigencia general (`VIGENTE` / `SIN FECHA` / `NO APLICA`) |

Si tu Excel tiene una hoja llamada exactamente `Base`, la app la usa automáticamente;
si no, toma la primera hoja del archivo.

## Publicar en GitHub Pages

1. Creá un repositorio nuevo en GitHub (puede ser privado o público).
2. Subí estos 3 archivos a la raíz del repo: `index.html`, `data.js`, `README.md`.
3. En el repo, andá a **Settings → Pages**.
4. En "Source" elegí la rama `main` (o `master`) y la carpeta `/ (root)`. Guardá.
5. GitHub te va a dar una URL tipo `https://tu-usuario.github.io/tu-repo/`. Abrila —
   ahí ya podés cargar tu Excel real desde el botón, igual que en local.

## Nota sobre la "fecha de revisión"

Tu pedido menciona dos momentos: **capacitación** y **revisión posterior** (verificar que el
colaborador aplica lo aprendido). El Excel actual tiene una sola columna de fecha (`FECHA`) y
un estado (`Estado capacitacion`: sin programar → programado → vigente), pero no una columna
separada para la fecha de revisión.

Si querés trackear la revisión como un paso aparte, se puede agregar sin mucho esfuerzo:
- Agregando una columna `Fecha revisión` (y opcionalmente `Estado revisión`) al Excel, y
- Ajustando la app para mostrarla como una segunda columna en la tabla de cada colaborador.

Avisame si querés que lo sume ahora.
