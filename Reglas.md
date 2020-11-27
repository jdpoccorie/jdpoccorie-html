# Reglas HTML 

(https://codeguide.co/) - En inglés

__*"Cada línea de código debe parecer escrita por una sola persona, sin importar el número de colaboradores."*__

## Sintaxis

* No use mayúsculas en las etiquetas, incluido el tipo de documento.
* Sangría (2 espacios)
* Utilice siempre comillas dobles, nunca comillas simples, en los atributos
* No incluya una barra al final de los elementos **self closing** o **vacíos**
* No omita las etiquetas de cierre opcionales (ej. `</li>` o `</body>`)

```html
<!doctype html>
<html>
  <head>
    <title>Page title</title>
  </head>
  <body>
    <img src="images/company-logo.png" alt="Company">
    <h1 class="hello-world">Hello, world!</h1>
  </body>
</html>
```

## Atributo Language

`lang`

Se anima a los desarrolladores a especificar un atributo `lang` en el elemento *root* *html*, indicando el idioma del documento. Esto ayuda a las herramientas de sintesis de voz para determinar qué pronunciaciones usar, herramientas de traducción, etc.

Para leer más:
* (https://html.spec.whatwg.org/multipage/semantics.html#the-html-element)
* (https://www.sitepoint.com/iso-2-letter-language-codes/)

## Codificación de caracteres

Asegure rápida y fácilmente la representación adecuada de su contenido declarando una codificación de caracteres explícita.

```html
<head>
  <meta charset="utf-8">
</head>
```

## Incluir CSS y JavaScript

Segun HTML5, no es necesario especificar el atributo `type` cuando se incluyen archivos CSS y JavaScript.

```html
<!-- External CSS -->
<link rel="stylesheet" href="code-guide.css">

<!-- In-document CSS -->
<style>
  /* ... */
</style>

<!-- JavaScript -->
<script src="code-guide.js"></script>
```

## HTML puro

Esfuércese por mantener los estándares y la semántica HTML. Utilice la menor cantidad de marcado, reduzca complejidades siempre que sea posible.

## Orden de los atributos

Los atributos HTML deben venir en este orden particular para facilitar la lectura del código

* `class` (Si se tiene más de una clase separar por dos espacios)
* `id`, `name` (evitar **id** para el CSS, **name** para el backend)
* `data-*` (Son creados por nosotros)
* `src`, `for`, `type`, `href`, `value`
* `title`, `alt` (SEO)
* `role`, `aria-*` (Son etiquetas para accesibilidad)

Las clases por ser excelentes componentes reutilizables deben de ir primero. Los identificadores son más específicos y deben usarse con moderación.

## Atributos booleanos

(https://html.spec.whatwg.org/multipage/common-microsyntaxes.html#boolean-attributes)

Un atributo booleano es aquel que no necesita un valor declarado.

Según la **WHATWG**: *La presencia de un atributo booleano en un elemento representa el valor true y la ausencia del atributo representa su valor false*

**En resumen, no agregue un valor**

```html
<input type="text" disabled>

<input type="checkbox" value="1" checked>

<select>
  <option value="1" selected>1</option>
</select>
```

## Reduzca el marcado

Siempre que sea posible, evite padres superfluos al escribir HTML Muchas veces esto requiere iteración y refactorización, pero produce menos HTML. Tome el sgte ejemplo:

```html
<!-- Not so great -->
<span class="avatar">
  <img src="...">
</span>

<!-- Better -->
<img class="avatar" src="...">
```

## Codigo HTML generado por JS

Escribir codigo HTML desde JS hace que el contenido sea más dificil de encontrar, editar y menos eficaz. Evitelo siempre que sea posible.

# Más buenas practicas para escribir HTML

(https://browserdiet.com/es/)

1. Especificar
    * Tipo de documento HTML5 `<!doctype html>` en minúsculas
    * Atributo de idioma `lang=es`
    * Juego de caracteres `<meta charset="utf-8">`
    * Acerca de la visualización *viewport*
2. Definir
    * `title` Único (máx 65 caracteres)
    * `description` Único (máx 156 caracteres)
    * Estilos antes de `</head>`
    * Scripts antes de `</body>` (recomendable pero no obligatorio)

Ejemplo:
```html
<! DOCTYPE html>
<html lang="es">
<head>
  <meta name="viewport" content="width=device-width", initial-scale=1.0>
  <meta http-equiv="X-UA-Compatible" content="IE=edge, chrome=1">
  <meta charset="UTF-8">
  <title>Titulo de documento, este deberá ser único max 65 caracteres</title>
  <meta name="description" content="Breve descripción de lo que los
usuarios encontraran en este documento, debe ser única más 156 caracteres">
  <!-- Codigos CSS -->
  <link rel="stylesheet" href="estilos.css">
</head>
<body>
  <h1>Estructura de documento HTML5</h1>

  <!-- Codigos JavaScript -->
  <script src="codigos.js"></script>
</body>
</html>
```