### Diseño y Nuevos Medios → Clase 02 → 16/08/2023

# HTML5 + CSS3 + p5.js

### Teoría (para la casa)

Ya pudimos reconocer la diferencia entre los lenguajes de descripción y el lenguaje de programación. Para comenzar a profundizar en un lenguaje de programación aprovechamos [p5.js](https://p5js.org/es/):

> ¡**p5.js** es una biblioteca de JavaScript para la programación creativa, que busca hacer que programar sea accesible e inclusivo para artistas, diseñadores, educadores, principiantes y cualquier otra persona! **p5.js** es gratuito y de código abierto porque creemos que el software y las herramientas para aprenderlo deben ser accesibles para todos.

Esta biblioteca fue creada por [Lauren McCarthy](http://lauren-mccarthy.com/) y es desarrollada por una comunidad de colaboradores, con apoyo de [Processing Foundation](https://processingfoundation.org/) y [NYU ITP](https://forms.tisch.nyu.edu/page/s/itp-landing). Entre los colaboradores hay 2 chilenos, que se han encargado de la traducción de referencias, tutoriales y [un libro](https://processingfoundation.press/product/introduccion-a-p5-js/) al castellano; ellos son: [Guillermo Montecinos](https://guillemontecinos.cl/) y [Aarón Montoya-Moraga](https://montoyamoraga.io/).

[p5.js](https://p5js.org/es/) es una reinterpretación de [Processing](https://processing.org/) para la web. Consideremos que cuando se trabaja en Processing cada *sketch* tiene su `void setup()` y `void draw()`. Hay un `setup` que se ejecuta una única vez, en la partida. Hay un `draw` que por defecto se ejecuta una y otra vez. Ahora, cambiemos el `void` de [Java](https://es.wikipedia.org/wiki/Java_(lenguaje_de_programaci%C3%B3n)) por el `function` de [JavaScript](https://es.wikipedia.org/wiki/JavaScript), y tenemos:

```
function setup(){
  //colocas acá lo que se ejecuta una única vez
}

function draw(){
  //colocas acá lo que necesitas dibujar una y otra vez
}
```

Tal como Processing, [p5.js](https://p5js.org/es/) ofrece

> un conjunto completo de funcionalidades para dibujar. Sin embargo, no estás limitado solo a dibujar en tu lienzo. Puedes tomar toda la página del navegador como tu bosquejo, incluyendo los objetos HTML5 para texto, entrada, video, cámara web y sonido.

Y puedes tomar toda la página del navegador por el [Modelo de Objeto de Documento (DOM)](https://developer.mozilla.org/es/docs/Glossary/DOM): **A través del DOM, los programas escritos en JavaScript pueden acceder y modificar el contenido, estructura y estilo a la vista**.

Con el DOM podemos manipular una página así como cuando *photoshopeamos* una imagen. Si capturaste una imagen con 3 elementos y agregas un cuarto *photoshopénadolo*, en ningún caso modificas el fenómeno capturado, pero todos podrán ver una imagen con 4 elementos. 

Por la manipulación del DOM **podríamos encontrar inconcruencias entre** dos vista: la del **código fuente de la página** y la de los **elementos de la página**. Estirando la analogía: En el código fuente de la página ves el fenómeno tal como fue capturado, mientras que en la vista de elementos de la misma página está lo *photoshopeado* (lo que tenemos a la vista en toda la página del navegador).

Para que esta diferencia quede muy clara, aprovechen:

https://profesorfaco.github.io/dno037-2023-2/clase-02/ejemplo.html

Revisen las diferencias entre la vista del **código fuente de la página** y la de los **elementos de la página**

Noten que en el código fuente faltan contenidos que sí están en la visualización y en los elementos de la página.

Esto es así porque los contenidos depende de consultas programadas:

- Consulta por el momento en que se carga la página, con el [constructor `Date()`](https://developer.mozilla.org/es/docs/Web/JavaScript/Referencia/Objetos_globales/Date)

- Consulta a una [API swiftie](https://taylorswiftapi.onrender.com/get), con la función [loadJSON() de p5.js](https://p5js.org/es/reference/#/p5/loadJSON)

La primera consulta nos permitirá trabajar con [la sentencia `if...else`](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Statements/if...else). Y la segunda nos permitirá asomarnos por primera vez a [JSON](https://www.json.org/json-es.html), un formato ligero de intercambio de datos.

Pero antes del asomarnos a tal formato ligero de intercambio de datos, conviene saber algunas cosas sobre datos en programación.

Partamos con el número 18261884. 

Si nos entregan tal número, sin contexto alguno, resultaría inútil. Pero es distinto de la siguiente manera: 

| País      |  Población       | Superficie     |
|:----------|:-----------------|:---------------|
| Chile     | 18261884         | 756102         |

Entendiendo cómo funciona una tabla, contamos con una clara orientación para la utilización de tal número como dato sobre algo concreto: La población en Chile. 

Además del dato de la población de Chile, contamos con su superficie. Si dividimos el primer dato por el segundo, obtenemos la densidad de la población en Chile. El resultado de aquella división es 24,15267252.

Los números 18261884 y 24,15267252 tienen una diferencia que corresponde apuntar:

- **18261884** es un número entero, un `int` (del inglés *integer*).

- **24,15267252** es un número de coma flotante, un `float` (del inglés *floating point number*; y no se olviden de esta diferencia, lo que para nosotros es coma, *for them* es punto, y el *coding* se hace en *english*).

A estos dos tipos de datos, podemos agregar: 

- **true** o **false** como las dos opciones posibles de un [tipo de dato lógico](https://es.wikipedia.org/wiki/Tipo_de_dato_l%C3%B3gico) (bool: *boolean*)

- **"A"** como un carácter (char: *character*)

- **"ALGUNAS PALABRAS"** como una cadena de caracteres (en inglés: *string*)

¡En el tipo de dato numérico y booleano no se usan comillas, pero cuando se tienen caracteres aislados o en cadena, sí!

Mencionamos `int`, `float`, `bool`, `char` y `string`, porque son palabras que en lenguajes de programación más clásicos se reservan para **declarar que tal variable almacenará tal tipo de dato. Pero en JavaScript podemos crear toda variables con una única palabra reservada,`var`**. También podemos usar `let` y `const`. Para entender la diferencia, nos conviene consultar el artículo [Var, let y const. ¿Donde, cuando y por qué?](https://medium.com/@tatymolys/var-let-y-const-donde-cuando-y-por-qu%C3%A9-d4a0ee66883b).

Usando únicamente `var`, en JavaScript podemos asignar como contenido de la variable todas las siguientes alternativas:

```
var a = 18261884;
var b = 24.15267252;
var c = true;
var d = "siguiente";
var e = ["siguiente", "repüyen", "seguente", "suivant", "next", "Nächster", "次の", "다음의"];
var f = {
    mom: "Luann Van Houten",
    dad: "Kirk Van Houten",
    child: "Milhouse Van Houten"
};
var g = {
    mom: "Marge Simpson",
    dad: "Homer Simpson",
    children: ["Bart Simpson", "Lisa Simpson", "Maggie Simpson"]
};
var h = [
    {
        mom: "Luann",
        dad: "Kirk",
        children: ["Milhouse"]
    },
    {
        mom: "Marge",
        dad: "Homer",
        children: ["Bart", "Lisa", "Maggie"]
    },
    {
        mom: "Manjula",
        dad: "Apu",
        children: ["Poonam", "Sashi", "Pria", "Uma", "Anoop", "Sandeep", "Nabendu", "Gheet"]
    }
];
```
**Lo que cambia viene después del signo igual `=`, que en este caso está asignando contenido a cada variable.** 

Las variables `a`, `b` y `c` no requieren comillas. La variable `d`, que contiene una cadena de caracteres (*string*) sí usa comillas. 

La variable `e`, que contiene un arreglo, usa paréntesis cuadrado y cada elemento, por tratarse de un *string*, usa comillas (si fuesen números o booleanos no las usarían). 

La variable `f`, que contiene un objeto, usa paréntesis de llave que en su interior contiene pares de `nombre:valor`. 

Las variables `g` y `h` son mezclas de las anteriores.

Las variables de nombre `f`, `g` y `h` pueden verse como un **JSON**. Lo que les faltan son unas comillas que podemos ver, por ejemplo, antes de los dos puntos en `"quote"`, `"song"` y `"album"`:

```
{"quote":"I'm shining like fireworks over your sad, empty town.","song":"Dear John","album":"Speak Now"}
```

- - - - - - - - - - - - -

### Práctica (para la clase)

Antes de llevar los [documentos preparados](https://profesorfaco.github.io/dno037-2023-1/clase-02) al editor de código fuente en su computador, conviene:

- revisar el [método `querySelector`](https://developer.mozilla.org/es/docs/Web/API/Element/querySelector);

- tener a mano la [página de referencias de **p5.js**](https://p5js.org/es/reference/); y

- contar con una extensión que permita ver JSON de manera más ordenada en su navegador web. Para Chrome: [JSON Formatter](https://chrome.google.com/webstore/detail/json-formatter/mhimpmpmffogbmmkmajibklelopddmjf?hl=es) o [JSON Viewer](https://chrome.google.com/webstore/detail/json-viewer/gbmdgpbipfallnflgajpaliibnhdgobh?hl=es). Para Firefox: [JSON Lite](https://addons.mozilla.org/es/firefox/addon/json-lite/) o [Basic JSON Formatter](https://addons.mozilla.org/es/firefox/addon/basic-json-formatter/).

#### Ejercicio

El ejercicio se completa cuando cada estudiante publica, [con GitHub Pages](https://docs.github.com/es/free-pro-team@latest/github/working-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site), su versión ajustada del sitio web contenido en esta carpeta de repositorio.

El ejercicio completo puede ser evaluado con:

- **0 punto** → no logrado.

- **1 punto** → logrado.

- - - - - - - 

###### [← CLASE ANTERIOR](https://github.com/profesorfaco/dno037-2023-2/tree/main/clase-01) — [SIGUIENTE CLASE →](https://github.com/profesorfaco/dno037-2023-2/tree/main/clase-03)

