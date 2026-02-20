## Module 3 - Display and position your elements

### Box model

![boxModel](/assets/boxModel.png)

- Imagina una caja que envuelve cada elemento HTML
  - Esto se refiere al modelo de caja
- Tiene márgenes, bordes, rellenos y el contenido real.
- Todo en una página web es una caja en la que se puede controlar el tamaño, la posición, el fondo, etc.

### Margins

- Los márgenes se utilizan para crear espacio alrededor de los elementos, fuera de su borde.

```html
<div>
  <p class="myParagraph">My Paragraph</p>
</div>
```

```css
/* styles */
.myParagraph {
  margin: 20px;
}
```

- `margin: 20px;` gives the `p` element margin of `20px` around it from all the sides

#### **Margin On Individual Sides**

- También puede dar margen a los elementos de cualquier lado si lo desea.

```css
margin-top
margin-right
margin-bottom
margin-left
```

#### **Margin Shorthands**

- Este atajo se puede utilizar para dar margen en todos los lados

```css
p {
  margin: 20px;
}
```

- El ejemplo de abajo dar margen 20px superior
- Y dar margen 40px izquierda y derecha

```css
p {
  margin: 20px 40px;
}
```

- El ejemplo de abajo da margen `20px` superior
- Y dar margen `40px` izquierda y derecha
- Y dar margen `50px` abajo

```css
p {
  margin: 20px 40px 50px;
}
```

#### **Auto Margin**

- El valor `auto` de margin establece el elemento horizontalmente centrado dentro de su contenedor
- Abajo `div` ocupará 200px de ancho y el espacio restante se dividirá equitativamente entre el margen izquierdo y derecho

```css
div {
  width: 200px
  margin: auto;
}
```

### Paddings

- Los márgenes se utilizan para generar espacio alrededor del contenido del elemento en cuestión, dentro de su borde.

```html
<div class="myDiv">
  <p>My Paragraph</p>
</div>
```

```css
/* styles */
.myDiv {
  padding: 20px;
}
```

- `padding: 20px;` da al elemento `div` un relleno de `20px`.
- Así que, básicamente, habrá un espacio de `20px` entre `p` y `div` en todos los lados.

#### **Padding On Individual Sides**

- También puede dar relleno a los elementos en cualquier lado en particular si lo desea

```css
padding-top
padding-right
padding-bottom
padding-left
```

#### **Padding Shorthands**

- Para acolchar todos los lados

```css
div {
  padding: 20px;
}
```

- El siguiente ejemplo da padding `20px` arriba y abajo
- Y dar padding `40px` izquierda y derecha
-

```css
div {
  padding: 20px 40px;
}
```

- El siguiente ejemplo da padding `20px` top
- Y dar padding `40px` izquierda y derecha
- Y dar padding `50px` abajo

```css
div {
  padding: 20px 40px 50px;
}
```

### Display

#### **Block**

- Esta propiedad estira el elemento de izquierda a derecha todo lo que puede
- Por defecto es block para `div`, `p`, `form`, `header`, `footer`, `section` (y algunos más)
- Estos elementos no pueden colocarse en la misma línea horizontal con ningún otro modo de visualización.
  - Excepto cuando están floated
- Como se muestra en la ilustración -> cada elemento se estira y ocupa toda la fila

#### **Inline**

- El elemento Inline se sitúa en línea
  - Sin interrumpir el flujo de otros elementos
- Como se muestra en la ilustración -> cada elemento ocupa sólo el espacio que necesita
  - El elemento pasa a la siguiente fila si no hay espacio suficiente
- `span`, `em`, `b` son ejemplos de elementos en línea
- Sólo ocupan el ancho necesario
- No respetan el relleno vertical
  - Sin anchura
  - Sin altura
  - Simplemente los ignoran
- Se respetan el margen horizontal y el relleno
- Ignoran el margen vertical y el relleno vertical

#### **Inline-block**

- Es igual que los elementos inline
- PERO respetan la anchura y la altura
- Básicamente, combinan las propiedades de los elementos de bloque y de los elementos en línea.
- El elemento puede aparecer en la misma línea horizontal que otros elementos.
- Así que, como muestra la ilustración, si ajustas la anchura puedes poner todos los elementos juntos en una sola fila.

#### **None**

- Estos elementos no aparecerán en la página en absoluto Pero todavía se puede interactuar con ella a través de DOM
- NO hay espacio asignado en la página

#### **Visibility Hidden**

- Se le asigna espacio en la página
- La etiqueta se muestra en el DOM
- El elemento no es visible

```css
div {
  visibility: hidden;
}
```

#### **Flex**

- La propiedad Flex permite modificar la anchura y la altura de los elementos para adaptarlos al espacio disponible.
- Se utiliza para adaptarse a todo tipo de dispositivos de visualización y tamaños de pantalla.
- Rellena el espacio disponible
  - O se encoge para evitar el exceso

### Positions

#### **Static**

- Es el valor por defecto para cada elemento
- Honestamente, no significa mucho.
  - Sólo significa que se insertará en la página como lo haría normalmente.
- Como se muestra en las ilustraciones los bloques simplemente caen en su posición por defecto
- Úsalo cuando quieras quitar la posición aplicada forzosamente al elemento
- NOTA: `z-index` no funciona con ellos

#### **Relative**

- El elemento es relativo a sí mismo
- Echa un vistazo al siguiente ejemplo

```html
<div class=myDiv""></div>
```

```css
.myDiv {
  position: relative;
  top: 10px;
  left: 10px;
}
```

- Ahora, se deslizará hacia abajo y a la izquierda por `10px` de donde normalmente sería
  - Consulte la ilustración anterior
- Sin esa propiedad "top" - sólo habría seguido `position: static`.

#### **Absolute**

- Esta propiedad es muy potente
- Le permite colocar el elemento exactamente donde desee
- Usando top, left, bottom. y right para establecer la ubicación
- **RECUERDE:** estos valores son relativos a su padre.
  - Donde el padre es absoluto o relativo
  - Si no hay tal padre, entonces se comprobará de nuevo a la etiqueta HTML y colocarlo absoluto a la propia página web
- Por lo tanto, los elementos se eliminan del "flujo" de la página web
- No se ven afectados por otros elementos
- Y no afecta a otros elementos
- **NOTA:** Su uso excesivo o inadecuado puede limitar la flexibilidad de su sitio web.

```html
<div class=myDiv""></div>
```

<div class=myDiv""></div>

```css
.myDiv {
  position: absolute;
  top: 10px;
  left: 10px;
}
```

- El `div` de arriba se deslizará hacia abajo y a la izquierda en `10px` desde su padre
  - Asumiendo que el padre tiene una posición absoluta o relativa

#### **Fixed**

- Posición relativa a la ventana gráfica
- Útil en encabezados o pies de página xed
- Por favor, consulte la ilustración de arriba para una mejor visualización

```html
<div class=myDiv""></div>
```

```css
.myDiv {
  position: fixed;
}
```
