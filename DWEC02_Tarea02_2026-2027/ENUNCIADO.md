# DWEC02 - Tarea 02
## Gestor de proyectos web

### ENUNCIADO DE LA TAREA

En la plantilla facilitada aparece un formulario para registrar un proyecto web y una zona destinada a analizar las tecnologías utilizadas en él.

El objetivo de la actividad es crear, a partir de los datos del formulario, un objeto JavaScript que represente el proyecto. Después se utilizarán sus propiedades y métodos para consultar información, abrir su repositorio y comparar su conjunto de tecnologías con varias listas proporcionadas.

La actividad trabajará especialmente con objetos, métodos, arrays, `Date`, funciones, objetos del navegador y manipulación del DOM.

---

## 1. Plantilla proporcionada

Se entregan:

```text
DWEC02_Tarea02/
├── index.html
├── index.js
└── styles.css
```

La estructura HTML y los estilos ya están preparados.

No se deberá modificar la estructura principal del HTML, salvo para añadir la etiqueta `<script>` necesaria para enlazar `index.js`.

En `index.js` se proporcionan dos arrays:

```javascript
tecnologiasEmpresa
tecnologiasExperimentales
```

y las siguientes funciones:

```javascript
crearProyecto()
mostrarResumen()
abrirRepositorio()
comprobarTecnologias()
comprobarExperimentales()
```

No se podrán eliminar ni renombrar estos elementos.

Se pueden crear todas las funciones auxiliares que sean necesarias.

---

## 2. Creación del objeto proyecto

Al pulsar el botón **"Crear proyecto"**, se creará un objeto llamado `proyecto` utilizando la información introducida en el formulario.

El objeto deberá contener las siguientes propiedades:

- `nombre` - string con el nombre del proyecto.
- `responsable` - string con el nombre de la persona responsable.
- `fechaEntrega` - objeto `Date`.
- `diasRestantes` - número entero con los días que faltan hasta la fecha de entrega.
- `horasEstimadas` - número entero.
- `presupuesto` - número.
- `costeHora` - presupuesto dividido entre las horas estimadas.
- `prioridad` - string calculado en función de los días restantes.
- `tecnologias` - array de strings.
- `urlRepositorio` - string con la URL completa.

No es necesario realizar validaciones complejas. Se supondrá que los datos introducidos respetan el formato solicitado.

---

## 3. Fecha de entrega y días restantes

La fecha introducida deberá convertirse en un objeto `Date`.

Utilizando la fecha actual del sistema, calcula cuántos días faltan hasta la entrega del proyecto.

El resultado se almacenará en:

```javascript
proyecto.diasRestantes
```

Para esta operación deberás utilizar las posibilidades que ofrece el objeto `Date`.

---

## 4. Prioridad del proyecto

La propiedad `prioridad` se calculará a partir de `diasRestantes`:

- 7 días o menos: `"Urgente"`.
- Más de 7 y hasta 30 días: `"Próxima"`.
- Más de 30 días: `"Planificada"`.

La prioridad debe calcularse automáticamente al crear el objeto.

---

## 5. Coste por hora

Calcula el coste aproximado por hora mediante:

```text
presupuesto / horas estimadas
```

El resultado se almacenará en:

```javascript
proyecto.costeHora
```

Cuando se muestre al usuario deberá aparecer con dos decimales.

---

## 6. Tecnologías del proyecto

El formulario permite introducir varias tecnologías separadas por comas.

Por ejemplo:

```text
JavaScript, React, Node, MySQL
```

A partir de ese texto deberás crear un array.

Antes de almacenarlo:

- Elimina los espacios sobrantes de cada elemento.
- Convierte los nombres a minúsculas.

El resultado del ejemplo anterior deberá ser equivalente a:

```javascript
[
    'javascript',
    'react',
    'node',
    'mysql'
]
```

Esta transformación deberá realizarse mediante código JavaScript, no manualmente.

---

## 7. Métodos del objeto

El objeto `proyecto` tendrá al menos dos métodos.

### `resumen()`

Mostrará mediante `alert()` un resumen redactado del proyecto.

Deberá incluir como mínimo:

- Nombre.
- Responsable.
- Fecha de entrega.
- Días restantes.
- Horas estimadas.
- Presupuesto.
- Coste por hora.
- Prioridad.
- Tecnologías.

Si posteriormente se ha creado la propiedad `tecnologiasCompatibles`, también deberá aparecer en el resumen.

### `abrirRepositorio()`

Abrirá en una nueva ventana o pestaña la URL almacenada en `urlRepositorio`.

Deberás utilizar las posibilidades del objeto `window`.

Dentro de los métodos del objeto deberás utilizar `this` para acceder a sus propiedades.

---

## 8. Botón "Mostrar resumen"

Después de crear el proyecto aparecerá el botón **"Mostrar resumen"**.

Al pulsarlo deberá ejecutarse el método `resumen()` del objeto `proyecto`.

---

## 9. Botón "Abrir repositorio"

Después de crear el proyecto aparecerá también el botón **"Abrir repositorio"**.

Antes de abrir la URL deberá preguntarse al usuario mediante `confirm()` si realmente desea continuar.

- Si acepta, se llamará al método `abrirRepositorio()`.
- Si cancela, no se abrirá ninguna página.

---

## 10. Comprobar tecnologías compatibles

El array `tecnologiasEmpresa` contiene las tecnologías que utiliza habitualmente la empresa.

Al pulsar **"Comprobar tecnologías"** deberás comparar las tecnologías del proyecto con dicho array.

Si existen coincidencias:

1. Se añadirá dinámicamente al objeto `proyecto` una nueva propiedad llamada:

```javascript
tecnologiasCompatibles
```

2. La propiedad contendrá un array únicamente con las tecnologías coincidentes.

3. Las coincidencias se mostrarán ordenadas alfabéticamente.

4. El resultado se mostrará en el elemento:

```html
<div id="resultadoCompatibilidad"></div>
```

Ejemplo:

```text
Tecnologías compatibles: javascript, mysql, react
```

Si no existe ninguna coincidencia, se mostrará un mensaje indicándolo.

La propiedad `tecnologiasCompatibles` solo deberá existir cuando haya al menos una coincidencia.

---

## 11. Tecnologías experimentales

Después de realizar la comprobación anterior aparecerá el botón **"Tecnologías experimentales"**.

El array `tecnologiasExperimentales` contiene tecnologías que la empresa considera experimentales.

Al pulsar el botón deberás comprobar cuántas de las tecnologías utilizadas por el proyecto aparecen también en este array.

Deberás mostrar:

- El número de tecnologías experimentales encontradas.
- Sus nombres, si existe alguna.

El resultado se mostrará en:

```html
<div id="resultadoExperimentales"></div>
```

Ejemplo:

```text
El proyecto utiliza 2 tecnologías experimentales: astro, svelte
```

Si no existe ninguna, deberá indicarse igualmente.

---

## 12. Organización del código

Puedes crear funciones auxiliares para evitar repetir código.

La solución deberá utilizar de forma razonable contenidos como:

- Objetos definidos por el usuario.
- Propiedades y métodos.
- `this`.
- `Date`.
- Arrays.
- Métodos de arrays.
- Funciones.
- `window`.
- `confirm()`.
- Manipulación del DOM.

Se valorará tanto el funcionamiento como la organización y claridad de la solución.

---

## 13. Restricciones

No se permite:

- Eliminar o renombrar los arrays proporcionados.
- Eliminar o renombrar las funciones facilitadas.
- Sustituir las listas proporcionadas por otras.
- Resolver las tecnologías mediante strings independientes en lugar de arrays.
- Evitar la creación del objeto `proyecto`.
- Modificar la estructura HTML para realizar manualmente tareas que deben resolverse desde JavaScript.

---

## 14. Documentación

Incluye un archivo `documentacion.md`.

Deberá explicar brevemente:

- Qué propiedades y métodos tiene el objeto `proyecto`.
- Cómo se calcula `diasRestantes`.
- Cómo se calcula la prioridad.
- Cómo se transforma el texto de tecnologías en un array normalizado.
- Cómo se obtiene `tecnologiasCompatibles`.
- Cómo se añaden propiedades nuevas al objeto.
- Cómo se utilizan `confirm()` y `window.open()`.
- Cómo se cuentan las tecnologías experimentales.

No es necesario copiar todo el código.

---

## 15. Entrega

La entrega deberá contener:

```text
DWEC02_Tarea02/
├── index.html
├── index.js
├── styles.css
└── documentacion.md
```

El fichero comprimido se nombrará:

```text
Apellido1_Apellido2_Nombre_DWEC02_Tarea02.zip
```

---