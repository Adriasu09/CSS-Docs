- 💻 [CSS Intermedio](../cssIntermedio/README.md)

# Transiciones

Te permite modificar propiedades de manera suavizada en un tiempo determinado.

[Transition](https://www.w3schools.com/css/css3_transitions.asp)

- `transition`
- `transition-delay`
- `transition-duration`
- `transition-property`
- `transition-timing-function`
  - [ejemplos suavidad](https://www.joshwcomeau.com/animation/css-transitions/)
- `animation-iteration-count`
  - [ejemplos iteraciones](https://www.w3schools.com/cssref/css3_pr_animation-iteration-count.php)

`transition: <propiedad> <duracion> <suavidad> <espera>;`

```css
#buttonShop {
  transition: color 1s ease-in 1s;
}
```

I. Propiedad -> Cualquiera que se le esté aplicando.  
II. Duración -> Cantidad de tiempo que tardará la animación en efectuarse.  
III. Suavidad -> Si se quiere que tenga más velocidad en un momento de la animación o si es lineal.  
IV. Espera -> El tiempo que tardará en iniciar la animación.  
V. Iteraciones -> Es la cantidad de veces que se ejecutará la animación (puede ser `infinite`).

<ins>Ejemplo</ins>:

```css
div {
  width: 100px;
  height: 100px;
  background: red;
  transition: width 2s;
  animation-iteration-count: 2;
}

div:hover {
  width: 300px;
}
```
