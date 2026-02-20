### Media queries

- Se introdujo en `CSS3`.
- Utiliza la regla `@media` para incluir CSS sólo si se cumple una determinada condición.

![](/source/assets/mediaQueries.png)

- Las consultas de medios le permiten apuntar a cualquier plataforma que desee y escribir estilos específicos para esa plataforma.
- Así es como se escriben los estilos responsive
  - Diferentes estilos para ordenadores de sobremesa, tabletas y móviles
- Ejemplo sencillo

```css
// If the browser window is smaller than 500px, the background color will
change to lightblue:

@media only screen and (max-width: 500px) {
  body {
    background-color: lightblue;
  }
}
```

- A continuación se indican los puntos de ruptura para los dispositivos de su interés

```css
/* Extra small phones */
@media only screen and (max-width: 600px) {
}

/* Portrait tablets and large phones */
@media only screen and (min-width: 600px) {
}

/* Landscape tablets */
@media only screen and (min-width: 768px) {
}

/* Laptops/desktops */
@media only screen and (min-width: 992px) {
}

/* Large laptops and desktops */
@media only screen and (min-width: 1200px) {
}
```

#### **Always Design for Mobile First**

- Esto significa que el estilo para móviles primero
- A continuación, incluir estilos de escritorio en las consultas de los medios de comunicación

```css
/* Default styles for mobile phones */
.mobile-styles {
  width: 100%;
}

/* Styles for desktop in media queries */
@media only screen and (min-width: 768px) {
  /* Style For desktop: */
  .desktop-styles {
    width: 100%;
  }
}
```

#### **Orientation: Portrait / Landscape**

- Se trata de consultas que se aplican en función de la orientación del navegador/dispositivo

```css
@media only screen and (orientation: landscape) {
  body {
    background-color: lightblue;
  }
}
```

### Let's talk about the sizes - `px` vs `em` vs `rem`

- Los `pixels` son ignorantes, evítalos
- Si estás configurando todos tus tamaños de fuente, tamaños de elementos y espaciado en píxeles, no estás tratando al usuario final con respeto.
  - Los usuarios tendrán que hacer zoom con ctrl más +/- dependiendo del dispositivo en el que se encuentren
- Los `REMs` son una forma de establecer el tamaño de la fuente basándose en el tamaño de la fuente del elemento HTML raíz.
- Permite escalar rápidamente todo un proyecto cambiando el tamaño de la fuente raíz.
- `em` es relativo al tamaño de fuente de su padre directo o más cercano.
  - Cuando se tienen estilos anidados se hace difícil rastrear los ems.
  - Esto es lo que solucionan los REM: el tamaño siempre se refiere a la raíz.
- Tanto `pixels` como `REMs` para media queries fallan en varios navegadores cuando se usa el zoom del navegador, y `EMs` es la mejor opción que tenemos.

#### **How to calculate PX from REM**

EJEMPLO: El tamaño de la fuente HTML es de 10px, el tamaño de la fuente del párrafo es de 1,6rem.

Entonces el tamaño en píxeles es `1.6rem * 10px = 16px`.

### More on `rem` vs `em`

- Tanto `rem` como `em` son unidades relativas
- `rem` sólo es relativo al tamaño de fuente HTML (raíz).
- `rem` se utiliza habitualmente para los márgenes, los rellenos y, a veces, también para el tamaño de la fuente.
- `em` es relativo al tamaño de fuente de su padre directo o más cercano.
- se recomienda el uso de `em` para consultas de medios

### 💻 [Ejercicios](./ejercicios/README.md)
