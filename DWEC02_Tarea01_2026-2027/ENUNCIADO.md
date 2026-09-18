# DWEC02 - Tarea 01
## Generador de identidad visual

### ENUNCIADO DE LA TAREA

En la plantilla facilitada aparece una tarjeta que representa una identidad visual. Inicialmente contiene un nombre, un código identificador y dos colores.

El objetivo de la tarea es que, al pulsar el botón **"Generar identidad"**, se cree una nueva identidad de forma aleatoria y se actualicen los datos y el aspecto de la tarjeta.

La solución deberá utilizar objetos definidos por el usuario, arrays, métodos, `this`, objetos predefinidos de JavaScript y manipulación del DOM.

---

## 1. Plantilla proporcionada

Se entregan los siguientes archivos:

```text
DWEC02_Tarea01/
├── index.html
├── index.js
└── styles.css
```

El archivo `index.html` contiene toda la estructura de la interfaz y `styles.css` contiene los estilos necesarios.

No se deberá modificar la estructura HTML, salvo para añadir la etiqueta `<script>` necesaria para enlazar el archivo `index.js`.

En el archivo `index.js` se proporcionan varios arrays y la función:

```javascript
function generarIdentidad() {
    // Completar
}
```

No se pueden eliminar, renombrar ni modificar los arrays proporcionados ni la función `generarIdentidad()`.

---

## 2. Objeto `identidadVisual`

Crea un objeto llamado:

```javascript
identidadVisual
```

El objeto deberá contener, como mínimo, las siguientes propiedades:

- `colorFondo`
- `colorTexto`
- `codigo`
- `nombre`

Al cargar la página, estas propiedades deberán representar los valores iniciales que aparecen en la plantilla.

El objeto deberá contener también los métodos necesarios para generar una identidad nueva.

Dentro de sus métodos deberás utilizar `this` para acceder o modificar las propiedades del propio objeto.

---

## 3. Color de fondo

El método correspondiente deberá generar un color hexadecimal aleatorio con el formato:

```text
#A1B2C3
```

Para generarlo deberás utilizar obligatoriamente el array `hex` suministrado en la plantilla y `Math.random()`.

No se permite utilizar una lista de colores completos previamente preparada.

### Restricción

En los seis caracteres que forman el código hexadecimal no podrá aparecer un mismo símbolo más de dos veces.

Ejemplos válidos:

```text
#A1A2B3
#55B2D6
#01F01A
```

Ejemplos no válidos:

```text
#AAA123
#111ABC
```

La comprobación deberá realizarse durante el proceso de generación del color.

---

## 4. Color del texto

Genera también aleatoriamente el color del texto de la tarjeta.

Deberá:

- Tener formato hexadecimal.
- Generarse utilizando el array `hex`.
- Ser distinto del color de fondo generado.

No es necesario calcular automáticamente el contraste entre ambos colores.

---

## 5. Código identificador

Cada identidad tendrá un código de 6 caracteres.

Ejemplo:

```text
X7P2K9
```

El código se generará utilizando el array `caracteresCodigo` facilitado en la plantilla.

También deberá cumplirse que un mismo carácter no aparezca más de dos veces dentro del código.

El resultado se almacenará en la propiedad `codigo` del objeto.

---

## 6. Nombre de la identidad

El nombre deberá obtenerse utilizando los arrays:

```javascript
adjetivos
sustantivos
```

Deberás seleccionar aleatoriamente un elemento de cada array y combinarlos para formar el nombre.

Ejemplos:

```text
NÓMADA PIXEL
VECTORIAL BYTE
LÓGICO KERNEL
```

No se permite crear una lista previa de nombres completos.

---

## 7. Método de generación

El objeto deberá disponer de un método que genere una identidad completa.

Ese método deberá actualizar, al menos:

- `colorFondo`
- `colorTexto`
- `codigo`
- `nombre`

La generación de los distintos datos podrá dividirse en varios métodos si lo consideras conveniente.

---

## 8. Actualización del DOM

Al pulsar el botón **"Generar identidad"**, la función `generarIdentidad()` deberá utilizar el objeto creado y actualizar la página.

Como mínimo deberán cambiar:

- El color de fondo de la tarjeta.
- El color del texto de la tarjeta.
- El nombre de la identidad.
- El código identificador.
- El texto donde se muestra el color de fondo.
- El texto donde se muestra el color del texto.
- El título superior de la página.

El título superior deberá incorporar el nombre generado.

Por ejemplo:

```text
IDENTIDAD: NÓMADA PIXEL
```

Deberás acceder a los elementos del documento utilizando métodos del DOM como:

```javascript
document.getElementById()
```

o:

```javascript
document.querySelector()
```

---

## 9. Organización del código

Utiliza comentarios breves para separar las partes principales de la solución.

La solución deberá hacer un uso razonable de:

- Propiedades.
- Métodos.
- `this`.
- Arrays.
- Estructuras repetitivas.
- Condicionales.
- `Math.random()`.
- Manipulación del DOM.

No se valorará únicamente que el resultado visual funcione. También se tendrá en cuenta que la solución esté construida utilizando correctamente los contenidos de la unidad.

---

## 10. Restricciones

No se permite:

- Eliminar o renombrar los arrays facilitados.
- Eliminar o renombrar `generarIdentidad()`.
- Sustituir los arrays proporcionados por otros.
- Crear una lista de colores completos.
- Crear una lista de nombres completos.
- Resolver la actividad únicamente mediante variables independientes, sin crear el objeto solicitado.
- Modificar la estructura de la página para evitar realizar desde JavaScript las operaciones solicitadas.

---

## 11. Documentación

Incluye un archivo `documentacion.md` en la entrega.

Deberá contener una breve explicación de la solución, indicando:

- Las propiedades y métodos del objeto creado.
- Cómo se genera un color hexadecimal.
- Cómo se impide que un carácter aparezca más de dos veces.
- Cómo se genera el código identificador.
- Cómo se obtiene aleatoriamente el nombre.
- Qué elementos del DOM se modifican al generar una identidad.

No es necesario copiar todo el código dentro de la documentación.

---

## 12. Entrega

La entrega deberá contener:

```text
DWEC02_Tarea01/
├── index.html
├── index.js
├── styles.css
└── documentacion.md
```

Comprime todos los archivos en un único fichero.

El archivo se nombrará:

```text
Apellido1_Apellido2_Nombre_DWEC02_Tarea01.zip
```

