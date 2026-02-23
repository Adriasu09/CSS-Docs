### Flexbox

- Proporciona una forma eficiente de disponer, alinear y distribuir el espacio entre los elementos de un contenedor.
- La idea principal: dar al contenedor la posibilidad de modificar la anchura/altura (y el orden) de sus elementos para aprovechar al máximo el espacio disponible.

#### **Flex box container properties**

- `display: flex`
  - define un contenedor flex

- `flex-direction: row | row-reverse | column | column-reverse;`
  - establece el eje principal
  - define la dirección de colocación de los niños

- `flex-wrap: nowrap | wrap | wrap-reverse;`
  - permita que los artículos se envuelvan o se desenvuelvan según sea necesario

- `justify-content`
  - define la alineación a lo largo del eje principal
  - eje X para la fila, eje Y para la columna

- `align-items`
  - define la alineación a lo largo del eje transversal
  - eje Y para fila, eje X para columna - opuesto a `justify-content`.

#### **Flexbox Examples**

- Este es el código que utilizaremos para demostrar cómo funciona flex box

```html
<div class="flex-container">
  <div class="flex-item">1</div>
  <div class="flex-item">2</div>
  <div class="flex-item">3</div>
  <div class="flex-item">4</div>
  <div class="flex-item">5</div>
  <div class="flex-item">6</div>
</div>
```

```css
.flex-container {
  display: flex;
  padding: 20px;
  margin: 0;
  list-style: none;
  background: orange;
}

.flex-item {
  background: tomato;
  padding: 5px;
  width: 200px;
  height: 150px;
  margin-top: 10px;
  line-height: 150px;
  color: white;
  font-weight: bold;
  font-size: 3em;
  text-align: center;
}
```

- Este es el resultado del código anterior
  ![](/source/assets/1stOutput.png)

```css
.flex-container {
  display: flex;
  flex-direction: column;
}
```

![](/source/assets/2ndOutput.png)

```css
.flex-container {
  display: flex;
  flex-direction: column-reverse;
}
```

![](/source/assets/3rdOutput.png)

```css
.flex-container {
  display: flex;
  flex-direction: row;
  justify-content: center;
}
```

![](/source/assets/4thOutput.png)

```css
.flex-container {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}
```

![](/source/assets/5thOutput.png)

```html
<div class="flex-container">
  <div class="flex-item second">1</div>
  <div class="flex-item first">2</div>
  <div class="flex-item third">3</div>
</div>
```

```css
.first {
  order: 1;
}

.second {
  order: 2;
}

.third {
  order: 3;
}
```

![](/source/assets/6thOutput.png)

```html
<div class="flex-container">
  <div class="flex-item second">1</div>
  <div class="flex-item first">2</div>
  <div class="flex-item third">3</div>
</div>
```

```css
.first {
  flex-grow: 1;
}

.second {
  flex-grow: 2;
}

.third {
  flex-grow: 3;
}
```

![](/source/assets/7thOutput.png)

```html
<div class="flex-container">
  <div class="flex-item second">1</div>
  <div class="flex-item first">2</div>
  <div class="flex-item third">3</div>
</div>
```

```css
.first {
  flex-basis: 500px;
}
```

![](/source/assets/8thOutput.png)
