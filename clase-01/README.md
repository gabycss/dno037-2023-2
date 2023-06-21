### Diseño y Nuevos Medios → Clase 01 → 09/08/2023

# HTML5 + CSS3 + p5.js

### Teoría (para la casa)

Escribir "código fuente" implica describir y/o programar. 

Para reconocer los lenguajes de descripción y programación que son claves para el desarollo de sitios web profesionales o prototipos avanzados de aplicaciones web, trabajaremos con un editor de código fuente ([Sublime Text](https://www.sublimetext.com/) o [Phoenix Code Editor](https://phcode.dev/)).

El editor de código fuente nos darán indicaciones para poder describir y/o programar respuesta a las siguientes preguntas, cada una con un lenguaje distinto:

- **¿Qué es lo que contiene la página? Se responde con HTML (HyperText Markup Language)**. Lenguaje estándar que describe la estructura de las páginas web. HTML5 es la versión más reciente de este lenguaje. El bloque constructivo más básico del HTML es el elemento. Cada elemento de HTML se escribe, generalmente, entre etiquetas: `<etiqueta>contenido</etiqueta>` → Podemos complementar esta breve introducción a HTML con una revisión de la página: https://developer.mozilla.org/es/docs/Learn/Getting_started_with_the_web/HTML_basics

- **¿Cómo se muestra lo que contiene la página? Se responde con CSS (Cascading Style Sheets)**. Lenguaje estándar que describe la presentación de las páginas web. CSS3 es la versión más reciente de este lenguaje. Su unidad más básica es la regla. Cada regla se inicia con un selector, seguido de paréntesis de llave `{…}`. Tal paréntesis contiene un bloque de declaraciones. En tal bloque, cada declaración se separa de otra mediante punto y coma `;`. Una declaración se compone del par `propiedad: valor`. Con todo lo dicho, una regla se escribirá, generalmente, de la siguiente manera: `selector{ propiedad: valor; }`  →  Podemos complementar esta breve introducción a CSS con una revisión de la página: https://developer.mozilla.org/es/docs/Learn/Getting_started_with_the_web/CSS_basics (no es necesario realizar el ejercicio que allí se propone).

- **¿Qué hace la página? Se responde con JS (JavaScript)**. Lenguaje de programación que controla el comportamiento de las páginas web. Con JS se pueden escribir secuencias de instrucciones con las que una computadora realizará una tarea determinada. Su estructura puede variar dependiendo de la lógica de cada instrucción, la [versión](https://www.w3schools.com/js/js_versions.asp) en uso, la *library* en la que nos apoyemos para resolver algo específico, o el *framework* de programación con el que se levanta todo el trabajo → Podemos complementar esta breve introducción a JS con una revisión de la página: https://developer.mozilla.org/es/docs/Learn/JavaScript/First_steps/What_is_JavaScript

Los lenguajes de descripción pueden dominarse en un menor tiempo que los lenguajes de programación; HTML puede dominarse tan pronto se memorizan [los elementos HTML](https://developer.mozilla.org/es/docs/Web/HTML/Element) y sus [atributos](https://developer.mozilla.org/es/docs/Web/HTML/Attributes); CSS podría exigir algo más que HTML, porque implica memorizar propiedades, valores y sus unidades, además de [los selectores](https://developer.mozilla.org/es/docs/Web/CSS/CSS_Selectors) (para seleccionar elementos del HTML por tipo, atributo, identidad, clase, pseudoclase y un largo etcétera). 

Pero JavaScript, y la programación en general, puede tomarnos mucho más tiempo; una cosa es describir qué mostrar y cómo mostrarlo, y otra es estructurar instrucciones ajustadas a circunstancias y objetivos:

![meme](https://user-images.githubusercontent.com/7999767/156002975-2dfbf580-f6e2-4bd8-8e40-7110457a4cb4.png)

- - - - - - - - - - - - - - 

### Práctica (para la clase)

Para reconocer los lenguajes mencionados más arriba, podemos aprovechar los documentos contenidos en esta carpeta, comenzando con https://profesorfaco.github.io/dno037-2023-2/clase-01/index.html

Si nos asomamos a su código fuente, allí encontraremos la estructura típica de toda página HTML: 

```
<!DOCTYPE html>
<html lang="es">
    <head>…</head>
    <body>…</body>
</html>
```

Dentro de la cabeza (`<head></head>`), podemos ver un **link** cuya **ref**erencia es un [style.css](https://profesorfaco.github.io/dno037-2023-2/clase-01/style.css) que se **rel**aciona con la página como una **stylesheet**.

Allí podemos leer la estructura típica de toda hoja de estilo CSS, donde encontramos una serie de reglas con la misma estructura de un selector antes de unos paréntesis de llave que contienen declaraciones separadas por punto y coma:  `* { margin: 0; padding: 0; }`

Ahora volvamos al https://profesorfaco.github.io/dno037-2023-2/clase-01/index.html

En su código fuente leamos las líneas al final del cuerpo (`<body></body>`), dentro de unas etiquetas de script (`<script></script>`). 

Allí podemos ver una [variable de JavaScript](https://developer.mozilla.org/es/docs/Learn/JavaScript/First_steps/Variables#%C2%BFqu%C3%A9_es_una_variable); esta variable se llama `palabras` y contiene un arreglo con 8 cadenas de caracteres entre comillas. 

```
var palabras = ["siguiente", "repüyen", "seguente", "suivant", "next", "Nächster", "次の", "다음의"];
```

Cada cadena de caracteres, contenida entre comillas, tiene una posición dentro del arreglo. Las posiciones se identifican con un número, partiendo a la izquierda con el 0. Considerando lo recién dicho, `palabras[0]` refiere a `siguiente` y `palabras[7]` refiere a `다음의` 

El contenido de la variable se aprovecha para programar algo sencillo, con la ayuda de [p5.js](https://p5js.org/es/get-started/): una bibliteca de JS que reinterpreta Processing para la Web.

Para continuar reconociendo los lenguajes mencionados más arriba, y seguir aprovechando los documentos contenidos en esta carpeta, pasemos a https://profesorfaco.github.io/dno037-2023-2/clase-01/page.html, donde se programa algo más con p5.js (`<script></script>`).

**Llegando a este punto, ya conviene llevar los [documentos preparados](https://profesorfaco.github.io/dno037-2023-2/clase-01) al editor de código fuente en su computador.** 

Abriendo los documentos preparados en el editor de código fuente en su computador, podrá hacer los ajustes que el profesor indicará. 

Para no perderse, es muy recomendable poner atención y presentar sus dudas de inmediato. Por favor preséntelas al profesor. No a compañeros; así no les quita la posibilidad de concentrarse ni cae en "el juego del teléfono" o la trampa del "según yo…" (porque todo es según lo que corresponde al lenguaje en cuestión).

#### Importante

La práctica se completa cuando cada estudiante publica, [con GitHub Pages](https://docs.github.com/es/free-pro-team@latest/github/working-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site), su versión ajustada del sitio web contenido en esta carpeta de repositorio.

El ejercicio completo puede ser evaluado con:

- **0 punto** → no logrado.

- **1 punto** → logrado.

- - - - - - - 

###### [SIGUIENTE CLASE →](https://github.com/profesorfaco/dno037-2023-2/tree/main/clase-02)
