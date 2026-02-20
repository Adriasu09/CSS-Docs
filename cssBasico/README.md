Styling your WebPage

- [Create a CSS File](#crear-un-archivo-css)
- [Then add your style in your `index.html` file](#a-continuación-añada-su-estilo-en-el-archivo-indexhtml)
- [Now let's create the body of your Valentine's Day card](#ahora-vamos-a-crear-el-cuerpo-de-tu-tarjeta-de-san-valentín)
- [Now let's add your first style](#ahora-vamos-a-añadir-tu-primer-estilo)
- [Selectors](#selectors)
  - [.class](#class)
  - [child .class](#child-class)
  - [#id](#id)
  - [element tag](#element-tag)
  - [Mix n match](#mix-n-match)
  - [Id and Class](#id-and-class)
  - [Element and Class](#element-and-class)
- [Advanced Selectors](#advanced-selectors)
  - [adjacent selector](#adjacent-selector)
  - [attributes selector](#attributes-selector)
- [Backgrounds](#backgrounds)
- [Colors](#colors)
- [Borders](#borders)
- [Fun with Border Radius](#fun-with-border-radius)
  - [Shapes](#shapes)
  - [Shorthand](#shorthand)
  - [Circle and leaf](#circle-and-leaf)
  - [Circle](#circle)
  - [Leaf](#leaf)

### Crear un archivo CSS

- Cree un archivo `style.css` dentro de la carpeta `principal`.
- Sus estilos irán en este archivo `style.css`.

### A continuación, vincule su archivo de estilo en el archivo `index.html`.

- Debe utilizar la etiqueta de enlace para incluir su archivo de estilo dentro de su archivo HTML

```html
<head>
  <meta charset="utf-8" />
  <title>Valentine Gift</title>

  <link rel="stylesheet" type="text/css" href="style.css" />
</head>
```

### Ahora vamos a crear el cuerpo de tu tarjeta de San Valentín

- Reemplace la etiqueta `body` en su `index.html` le para que coincida con el siguiente código
- Usted está agregando `card` DIV que será el contenedor de su tarjeta de felicitación. Añadiremos los estilos más tarde.
- Dentro del DIV `card` añade dos etiquetas H1 - Estos son tus encabezados  
   - H1 son los encabezados más grandes disponibles  
   - También puedes cambiar el tamaño de letra según tus necesidades.
- También asignamos las `clases` apropiadas a nuestro HTML para que podamos darles estilo más tarde.  
   - Aprenderás sobre las clases más adelante

```html
<body>
  <div class="card">
    <h1 class="quote">You're the CSS to my HTML</h1>

    <h1 class="message">Happy Codding's Day</h1>
  </div>
</body>
```

### Ahora vamos a añadir tu primer estilo

- Vamos a añadir estilos para su tarjeta de felicitaciones.
- Estamos utilizando .card - class selector para agarrar la tarjeta DIV y darle estilo
- Aquí sólo estamos estableciendo un bonito rojo `border: 10px sólido #E53038;`
- `height: 100vh;` se hace para que coincida con la altura de la etiqueta del cuerpo - que es la altura de la vista completa del puerto.
- `display: flex;` hace que esta `card` DIV sea un flex-box.
  - Sólo estamos haciendo que todos nuestros `flex-children` se alineen en posición vertical y horizontalmente centrados en una columna.
  - NOTA: Aprenderemos sobre ex-box en la sección posterior.

```css
.card {
  border: 10px solid #e53038;
  height: 300px;
  width: 300px;
  padding: 20px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
```

#### **Selectors**

- En términos simples, los selectores se utilizan para tomar un elemento y aplicarle estilos.
- Hay diferentes tipos de selectores.

#### **.class**

- Selecciona todos los elementos con el nombre de clase dado
- Escribe un punto (.) seguido del nombre de la clase
- Seleccionará todos los p con class="myClass"

```html
<p class="myClass">This is a paragraph</p>
```

```css
.myClass {
  background-color: yellow;
```

#### **child .class**

- Puede apuntar a un elemento hijo utilizando una jerarquía de clases

```css
// syntax

.parent .child {
  background-color: yellow;
}
```

- Debe escribir el nombre de la clase padre seguido de un espacio, y a continuación el nombre de la clase hija.
- El siguiente ejemplo añadirá `background-color: yellow` al párrafo

```html
<div class="parent">
  <p class="child">This is a paragraph</p>
</div>
```

```css
.parent .child {
  background-color: yellow;
}
```

#### **#id**

- Seleccionamos los elementos añadiendo `#` seguido del atributo `id` del elemento
- Estilizar el elemento con el atributo `id` dado
- En el siguiente ejemplo `myParagraph` es el id del párrafo

```html
<p id="myParagraph">This is a paragraph</p>
```

```css
#myParagraph {
  background-color: yellow;
}
```

#### **element tag**

- Puedes seleccionar directamente un elemento por su nombre de etiqueta y aplicar los estilos
- En este caso no tienes que mencionar el `id` o la `class` - simplemente escribe el nombre del elemento en tus estilos y añádele propiedades.
- El siguiente ejemplo tomará todos los elementos `p` y les aplicará el estilo

```html
<p>This is a paragraph</p>
```

```css
p {
  background-color: yellow;
}
```

#### **Mix n match**

- Los selectores mencionados son las formas básicas y más comunes de seleccionar elementos y aplicarles estilos.
- También puede combinar cualquiera de los selectores anteriores para aplicar los estilos

#### **Id and Class**

- `id="miParrafo"` forma el selector Id
- `class="miClase"` forma el selector de clase

```html
<p id="myParagraph" class="myClass">This is a paragraph</p>
```

```css
#myParagraph.myClass {
  background-color: yellow;
}
```

#### **Element and Class**

- `p` se utiliza como selector de elemento
- `class="myClass"` forma el selector de clase

```html
<p class="myClass">This is a paragraph</p>
```

```css
p.myClass {
  background-color: yellow;
}
```

### Advanced Selectors

#### **adjacent selector**

- Selecciona sólo el elemento precedido por el elemento anterior.
- En este caso, sólo el primer párrafo después de cada ul tendrá texto rojo.

```html
<ul></ul>
<p></p>
```

```css
ul + p {
  color: red;
}
```

#### **attributes selector**

- Sólo seleccionará las etiquetas de anclaje que tengan un atributo title

```css
a[title] {
  color: green;
}
```

- Aplicará estilo a todas las etiquetas de anclaje que enlacen a `https://www.gammatech.school/`.

```css
a[href="https://www.gammatech.school/"] {
  color: #1f6053; /* green */
}
```

- La estrella designa que el valor que procede debe aparecer en alguna parte del valor del atributo

```css
a[href*="mma"] {
  color: #1f6053;
}
```

- El atributo "contiene" un valor
- Debe ser una palabra entera

```css
[title~="cat"] {
  border: 5px solid yellow;
}
```

```css
<img src="cat1.jpg" title="small cat" width="150" height="113"> //
selected
<img src="cat2.gif" title="catssss" width="224" height="162"> // NOT
selected

<img src="dog.gif" title="dog" width="200" height="358"> // NOT selected
```

- El atributo "contiene" un valor
- NO tiene que ser una palabra entera

```css
[title*="cat"] {
  border: 5px solid yellow;
}
```

```css
<img src="cat1.jpg" title="small cat" width="150" height="113"> //
selected
<img src="cat2.gif" title="catssss" width="224" height="162"> // selected
<img src="dog.gif" title="dog" width="200" height="358"> // NOT selected
```

- Valor del atributo "empieza por"
- El valor TIENE que ser una palabra entera
  - O una palabra entera
  - O palabra seguida de -

```css
[title|="cat"] {
  border: 5px solid yellow;
}
```

```html
<img src="cat1.jpg" title="cat-like small" width="150" height="113" /> //
selected <img src="cat2.gif" title="cat" width="224" height="162" /> // selected
<img src="dog.gif" title="dog" width="200" height="358" /> // NOT selected
```

- Valor del atributo "empieza por"
- El valor NO tiene que ser una palabra entera

```css
[title^="ca"] {
  border: 5px solid yellow;
}
```

```html
<img src="cat1.jpg" title="cat-like small" width="150" height="113" /> //
selected <img src="cat2.gif" title="cat" width="224" height="162" /> // selected
<img src="dog.gif" title="dog" width="200" height="358" /> // NOT selected
```

- Valor del atributo "termina con"
- El valor NO tiene que ser una palabra entera

```css
[title$="at"] {
  border: 5px solid yellow;
}
```

```html
<img src="cat1.jpg" title="cat-like small" width="150" height="113" /> // NOT
selected <img src="cat2.gif" title="cat" width="224" height="162" /> // selected
<img src="dog.gif" title="dog" width="200" height="358" /> // NOT selected
```

### Selectores combinados o de relación

Los combinadores Css son signos gráficos, o caracteres especiales, o palabras o expresiones reservadas utilizados en el nombre del selector para formar los selectores css complejos. Estos selectores css aumentan precisión del selector al relacionar varios de ellos en función de que cumplan alguna condición (que es la definida por el combinador).

```css
div > p {
}
```

- <a href="https://www.w3schools.com/css/css_combinators.asp" target="_blank">Selectores combinados o de relación</a>

---

### Backgrounds

- Puedes establecer diferentes fondos para tus elementos
- El fondo de un elemento es el tamaño total del elemento, incluyendo el relleno y el borde (pero no el margen).
- A continuación se muestra la lista de todas las propiedades de fondo

```css
background-color
background-image
background-position
background-size
background-repeat
background-origin
background-clip
background-attachment
```

- Puede definir todas las propiedades con una sola declaración
- Estas son algunas de las propiedades de fondo más utilizadas
- Añade el color de fondo `lightblue`
- Añade la imagen de fondo `myImage.png`
- Establece `no-repeat` background, lo que significa que no repetirá la imagen de fondo.
  - Por defecto se repite tanto vertical como horizontalmente.
- Establece la posición de fondo `center`.

```css
body {
  background: lightblue url("myImage.png") no-repeat center;
}
```

### Colors

- La propiedad color especifica el color del texto
- Puede especificar la propiedad color en diferentes elementos utilizando diferentes tipos de selectores
- Puede especificar colores por su nombre, su valor hexadecimal o su valor RGB

```css
h1 {
  color: red;
}

h1.myClass {
  color: #02af00;
}

h1#myId {
  color: rgb(111, 111, 111);
}
```

### Borders

- Puedes añadir bordes a tus elementos HTML
- A continuación se muestra la lista de todas las propiedades de borde

```css
border-width
border-style (required)
border-color
```

- En el siguiente ejemplo
- `5px` es el ancho del borde
- `solid` es el estilo del borde
  - Otros ejemplos son `dotted`, `double`, `dashed`.
- `red` es el color del borde
  - Puedes especificar los colores por su nombre, su valor hexadecimal o su valor RGB.

```css
h1 {
  border: 5px solid red;
}
```

### Fun with Border Radius

#### **Shapes**

- Los bordes también tienen otra propiedad llamada `border-radius` con la que puedes dar diferentes formas a tus elementos
- Si el radio del borde es del 50%, el cuadrado se convertirá en un círculo.

```css
.square {
  border-radius: none;
}

.circle {
  border-radius: 50%;
}
```

#### **Shorthand**

- Si se establece un valor, este radio se aplica a las 4 esquinas.
- Si se establecen dos valores, el primero se aplica a las esquinas superior izquierda e inferior derecha, el segundo a las esquinas superior derecha e inferior izquierda.
- Si se establecen tres valores, el segundo se aplica a las esquinas superior derecha e inferior izquierda.
- Si se establecen cuatro valores, se aplicarán a las esquinas superior izquierda, superior derecha, inferior derecha e inferior izquierda (en ese orden).

```html
<div class="card one">
  <h1 class="">One</h1>
</div>
<div class="card two">
  <h1 class="">Two</h1>
</div>
<div class="card three">
  <h1 class="">Three</h1>
</div>
<div class="card four">
  <h1 class="">Four</h1>
</div>
```

```css
// all 4 corners
.one {
  border-radius: 50%;
}

.two {
  border-radius: 10% 20%;
}
// 10% top-left and bottom-right,  20% top-right and bottom-left

.three {
  border-radius: 10% 20% 30%;
}
// 10% top-left, 20% top-right and also bottom-left, 30% bottom-right

.four {
  border-radius: 10% 20% 30% 40%;
}
// top-left, top-right, bottom-right, bottom-left corner (in that order)



.card {
  border: 10px solid #e53038;
  height: 100px;
  width: 100px;
  padding: 20px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  margin-bottom: 20px;
}
```

### **Circle and leaf**

#### **Circle**

```css
.circle {
  border-radius: 50%;
}
```

#### **Leaf**

```css
.leaf {
  border-radius: 5px 20px 5px;
}
```

---

Ejercicio básico para aprender los selectores:  
<a href="https://flukeout.github.io/" target="_blank">CSS Dinner</a>
