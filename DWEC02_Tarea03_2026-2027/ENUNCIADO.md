# DWEC02 - Tarea 03
## Gestor de incidencias técnicas

### ENUNCIADO DE LA TAREA

Vamos a desarrollar una aplicación para gestionar las incidencias técnicas registradas por un servicio de soporte. La aplicación permitirá añadir, borrar, visualizar y filtrar incidencias.

La interfaz HTML y los estilos se proporcionan ya preparados. La lógica deberá desarrollarse en JavaScript.

## 1. Plantilla proporcionada

Se entregan:

```text
DWEC02_Tarea03/
├── index.html
├── index.js
└── styles.css
```

No se deberá modificar la estructura del HTML, salvo para añadir la etiqueta `<script>` necesaria para enlazar `index.js`.

Los botones llaman a:

```javascript
agregarIncidencia()
borrarIncidencia()
mostrarIncidencias()
filtrarIncidencias()
```

Estas funciones deberán existir. Puedes crear todas las funciones auxiliares que necesites.

## 2. Objeto gestor `soporte`

Crea un objeto llamado `soporte` con, como mínimo:

- `numeroIncidencias`: número de incidencias almacenadas.
- `incidencias`: array que almacenará objetos incidencia.

También tendrá al menos los métodos:

- `agregarIncidencia()`
- `borrarIncidencia()`

Los métodos actualizarán correctamente `numeroIncidencias`. Utiliza `this` para trabajar con las propiedades del objeto.

## 3. Objeto incidencia

Cada incidencia tendrá:

- `codigo`
- `equipo`
- `prioridad`
- `tecnicos`
- `etiquetas`
- `descripcion`

`tecnicos` y `etiquetas` serán arrays.

Ejemplo conceptual:

```javascript
{
    codigo: "INC-104",
    equipo: "AULA2-PC14",
    prioridad: "Alta",
    tecnicos: ["Ana López", "Iker Ruiz"],
    etiquetas: ["red", "windows"],
    descripcion: "El equipo no obtiene dirección IP."
}
```

## 4. Conversión de técnicos y etiquetas

Los campos se introducen separados por comas.

```text
Ana López, Iker Ruiz
```

deberá transformarse en:

```javascript
["Ana López", "Iker Ruiz"]
```

Elimina espacios sobrantes. Las etiquetas deberán almacenarse en minúsculas.

## 5. Agregar incidencias

Al pulsar **"Agregar incidencia"**:

1. Recoge los datos del formulario.
2. Crea un objeto incidencia.
3. Añádelo a `soporte.incidencias`.
4. Actualiza `soporte.numeroIncidencias`.
5. Actualiza el contador `numeroIncidencias` del DOM.
6. Muestra en consola un mensaje confirmando el alta.

No podrán existir dos incidencias con el mismo `codigo`. La comparación no distinguirá mayúsculas y minúsculas. Si el código ya existe, se mostrará un `alert()` y no se añadirá.

## 6. Borrar incidencias

Al pulsar **"Borrar incidencia"** se pedirá mediante `prompt()` el código.

Si existe:

- Se eliminará únicamente esa incidencia.
- Se actualizará el contador.
- Se mostrará un mensaje en consola.
- Se volverá a mostrar la tabla actualizada.

Si no existe, se informará mediante `alert()`.

La búsqueda tampoco distinguirá mayúsculas y minúsculas.

## 7. Visualizar incidencias

Al pulsar **"Visualizar incidencias"** se mostrarán todas las incidencias dentro de:

```html
<div id="datos"></div>
```

La tabla deberá crearse desde JavaScript y tendrá, como mínimo:

- Código
- Equipo
- Prioridad
- Técnicos
- Etiquetas
- Descripción

Los arrays se mostrarán como texto legible utilizando comas.

Antes de visualizar, las incidencias se ordenarán:

1. Alta
2. Media
3. Baja

Dentro de la misma prioridad se ordenarán alfabéticamente por `codigo`.

La ordenación utilizada para mostrar la tabla no deberá alterar permanentemente el orden original de `soporte.incidencias`.

## 8. Filtrar incidencias

Al pulsar **"Filtrar incidencias"** se pedirá mediante `prompt()`:

```text
campo:valor
```

Ejemplos:

```text
prioridad:alta
equipo:aula2
tecnicos:ana
etiquetas:red
codigo:104
descripcion:impresora
```

Se podrá filtrar por:

- `codigo`
- `equipo`
- `prioridad`
- `tecnicos`
- `etiquetas`
- `descripcion`

La búsqueda no distinguirá mayúsculas y minúsculas y admitirá coincidencias parciales.

Por ejemplo, `tecnicos:ana` deberá encontrar una incidencia con `"Ana López"` dentro del array de técnicos.

Los resultados se mostrarán con la misma tabla. Si no hay coincidencias, se indicará. Si el campo no es válido, también se informará.

## 9. Arrays y funciones

Utiliza de forma razonable los métodos estudiados. Puedes emplear, entre otros:

```javascript
find()
findIndex()
some()
filter()
sort()
map()
includes()
join()
```

No es obligatorio utilizar todos ellos.

## 10. Manipulación del DOM

Desde JavaScript deberán modificarse:

- El contador.
- El área de resultados.
- La tabla.
- Los mensajes cuando no existan resultados.

La tabla no podrá estar escrita manualmente en el HTML.

## 11. Restricciones

No se permite:

- Sustituir `soporte.incidencias` por variables independientes.
- Permitir códigos duplicados.
- Guardar `tecnicos` o `etiquetas` como un único string.
- Escribir manualmente en HTML los resultados.
- Crear una solución específica para unos pocos filtros.
- Modificar el HTML para evitar implementar operaciones desde JavaScript.

## 12. Documentación

Incluye `documentacion.md` explicando brevemente:

- La estructura de `soporte`.
- La estructura de una incidencia.
- La conversión de técnicos y etiquetas en arrays.
- El control de duplicados.
- El borrado.
- La ordenación.
- La creación de la tabla.
- El filtro `campo:valor`, especialmente en propiedades que son arrays.

No es necesario copiar todo el código.

## 13. Entrega

```text
DWEC02_Tarea03/
├── index.html
├── index.js
├── styles.css
└── documentacion.md
```

Nombre del ZIP:

```text
Apellido1_Apellido2_Nombre_DWEC02_Tarea03.zip
```
