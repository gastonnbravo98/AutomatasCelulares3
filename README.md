# Autómatas Celulares — Demo interactiva

Esta aplicación es una pequeña demostración visual de tres conceptos relacionados entre sí: autómatas celulares, convolución con kernel y el Juego de la Vida de Conway. Todo está integrado en una sola página HTML con una interfaz interactiva para explorar cada tema.

## ¿Qué es este proyecto?

El proyecto presenta una grilla bidimensional donde cada celda puede estar viva o muerta. La evolución del sistema depende del estado de las celdas vecinas y de una regla local que se aplica de forma simultánea a toda la grilla.

La demo está pensada para enseñar visualmente cómo:

1. una regla local genera un comportamiento global,
2. la idea de vecindad y kernel se vuelve matemática y computacional,
3. el Juego de la Vida produce patrones complejos a partir de reglas muy simples.

---

## 1) Autómata celular

### Idea general

Un autómata celular es un conjunto de celdas organizadas en una grilla. Cada celda tiene un estado, normalmente:

- 0 = muerta
- 1 = viva

En cada paso, todas las celdas se actualizan al mismo tiempo según una regla local. Es decir, cada celda observa a sus vecinos y decide su próximo estado.

### Regla usada en la demostración

En esta demo, la regla es la de “mayoría”:

- se cuenta la celda actual más sus ocho vecinas,
- si hay 5 o más celdas vivas en ese conjunto, la celda viva en la siguiente generación,
- si no, muere.

Esto permite ver cómo una regla simple puede dar lugar a comportamientos interesantes en una grilla.

### Interacción

En la primera sección de la app se puede:

- hacer clic sobre la grilla para dibujar un patrón inicial,
- calcular la siguiente generación,
- avanzar paso a paso,
- reproducir de forma automática,
- aleatorizar la grilla,
- limpiar la simulación.

### Concepto clave

La característica central es que la evolución de cada celda depende solo del entorno inmediato, no del estado global del sistema.

---

## 2) Convolución con kernel 3x3

### Idea general

La convolución es una operación matemática usada para procesar imágenes, señales y grillas. En este caso, se usa una ventana pequeña de 3x3 llamada kernel.

El kernel se desliza sobre la grilla, celda por celda, y en cada posición se suma la cantidad de vecinos vivos que están dentro de esa ventana.

### Kernel de la demo

El kernel tiene esta forma:

- el centro vale 0,
- las 8 posiciones alrededor valen 1,

por lo que la suma total representa la cantidad de vecinos vivos alrededor de la celda evaluada.

### ¿Qué se visualiza?

La segunda pestaña de la aplicación muestra:

- la grilla de entrada,
- el kernel sobre la celda actual,
- el conteo de vecinos vivos,
- un mapa de resultados con valores del 0 al 8.

También hay dos modos de borde:

- modo normal: fuera de la grilla no se cuenta,
- modo toroidal: los bordes se conectan entre sí como si la grilla fuera un toro.

### Concepto clave

La convolución permite convertir una grilla en otra grilla de valores donde cada posición representa la cantidad de vecindad activa alrededor de esa celda.

---

## 3) Juego de la Vida de Conway

### Idea general

El Juego de la Vida es un caso particular de autómata celular inventado por John Conway. Tiene reglas muy simples, pero da lugar a comportamientos muy ricos y sorprendentes.

### Reglas de Conway

Para cada celda:

- si está viva y tiene 2 o 3 vecinas vivas, sigue viva,
- si está muerta y tiene exactamente 3 vecinas vivas, nace,
- en cualquier otro caso, muere o permanece muerta.

Estas reglas se conocen como B3/S23:

- B = nace con 3 vecinos,
- S = sobrevive con 2 o 3 vecinos.

### Patrones clásicos

La aplicación incluye varios patrones bien conocidos:

- Glider (deslizador)
- Blinker (parpadeante)
- Toad (sapo)
- Beacon (faro)

También se puede dibujar libremente sobre la grilla y activar la reproducción automática.

### Concepto clave

Conway demostró que reglas locales muy sencillas pueden producir patrones estables, oscilantes y móviles, incluso sin ninguna inteligencia externa.

---
