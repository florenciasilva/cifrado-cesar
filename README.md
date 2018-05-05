# Cifrado César

## Preámbulo

Está próxima la fecha del cumpleaños de tu flacx (novix) y estás organizando una
fiesta sorpresa. Para organizar la fiesta has creado un grupo de Whatsapp junto
con amigos y familiares.

Un gran problema es que pones tu alarma para levantarte temprano, sin embargo
(como supondrás) eso nunca sucede y tu flacx es quien termina apagando la alarma
y "de casualidad" revisando tus mensajes. Debido a que es algo sorpresa, decides
crear una aplicación que te permita enviar mensajes cifrados y que las demás
personas (partícipes de la fiesta) puedan tener una interfaz para
descifrarlo. Así que ahora te toca aplicar tus superpoderes 😎

## Introducción

El [cifrado César](https://en.wikipedia.org/wiki/Caesar_cipher) es uno de los
primeros métodos de cifrado conocidos históricamente. Es un tipo de cifrado por
sustitución en el que una letra en el texto original es reemplazada por otra
letra que se encuentra un número fijo de posiciones más adelante en el alfabeto.

El emperador Julio César lo usaba para enviar órdenes a sus generales en los
campos de batalla, es una de las técnicas más simples y más usadas para cifrar
un mensaje.

Por ejemplo si usáramos un desplazamiento de 3:

* Alfabeto sin cifrar: A B C D E F G H I J K L M N Ñ O P Q R S T U V W X Y Z
* Alfabeto cifrado: D E F G H I J K L M N Ñ O P Q R S T U V W X Y Z A B C

Actualmente todos los cifrados de sustitución alfabética simple, se descifran
con facilidad y en la práctica no ofrece mucha seguridad en la comunicación,
pero el cifrado César muchas veces puede formar parte de sistemas más complejos
de codificación, como el cifrado Vigenère, e incluso tiene aplicación en el
sistema ROT13.

## Objetivos

El objetivo principal de aprendizaje de este reto es tener tu primera
experiencia construyendo una aplicación web usando tus conocimientos de **User
Experience Design** y de **JavaScript**. Esto incluye diseñar un producto
pensando en los usuarios, construir una interfaz, escuchar eventos básicos del
DOM, escribir lógica para llevar a cabo el cifado/descifrado, tests unitarios
básicos para comprobar (y documentar) dicha lógica, y finalmente manipulación
del DOM para mostrar (escribir) los resultados.

Para completar el reto tendrás que familiarizarte con conceptos como _valores_,
_tipos_, _variables_, _estructuras de datos_, _control de flujo_, _funciones_ y
_tests unitarios_.

Esperamos que en este reto puedas pensar en el usuario, entendiendo quién es y
su necesidad. La idea es que logres entender qué necesita el usuario para el que
crearás el producto y le ayudes a resolver esa necesidad de la mejor manera
posible.

Además, que puedas organizarte teniendo en cuenta el tiempo y los recursos
disponibles. Es la primera vez que evaluaremos tus soft skills, pero debes
considerar que son habilidades que probablemente ya has utilizado en distintas
experiencias de tu vida. Lo importante es que realices el reto de manera
integral.

## Consideraciones generales

La lógica del reto debe estar implementada completamente en JavaScript (ES6).
En este reto NO está permitido usar librerías o frameworks, sólo
[vanilla JavaScript](https://medium.com/laboratoria-how-to/vanillajs-vs-jquery-31e623bbd46e).

No se debe utilizar la _pseudo-variable_ `this`.

Los tests unitarios deben cubrir un mínimo del 70% de _statements_, _functions_
y _lines_, y un mínimo del 50% de _branches_. El _boilerplate_ ya contiene el
setup y configuración necesaria para ejecutar los tests (pruebas) usando el
comando `npm test` (o `yarn test` si estás usando `yarn` como
_package manager_).

Para comenzar este reto tendrás que hacer un _fork_ y _clonar_ este repositorio
que contiene el _boilerplate_.

El _boilerplate_ contiene una estructura de archivos como punto de partida así
como toda la configuración de dependencias y tests de ejemplo:

```
./
├── .editorconfig
├── .eslintrc
├── .gitignore
├── README.md
├── package.json
├── src
│   ├── cipher.js
│   ├── index.html
│   ├── index.js
│   └── style.css
└── test
    ├── cipher.spec.js
    ├── headless.js
    └── index.html
```

## Parte obligatoria

### Definición del producto

En el `README.md` cuéntanos cómo pensaste en los usuarios al desarrollar tu
producto y cuál fue tu proceso para definir el producto final a nivel de
experiencia y de interfaz.

* quiénes son los principales usarios de producto
* cuáles son los objetivos de estos usarios en relación con el producto
* cómo crees que el producto que estás creando les está resolviendo sus
  problemas

### UI

La interfaz debe permitir al usuario:

* elegir un `offset` indicando cuántas posiciones queremos que el cifrado
  desplace cada caracter
* insertar un mensaje (texto) que queremos cifrar
* ver el resultado del mensaje cifrado
* insertar un mensaje (texto) a descifrar
* ver el resultado del mensaje descifrado

### Scripts / Archivos

* `README.md`: debe explicar cómo descargar, instalar y ejecutar la aplicación
  así como una introducción a la aplicación, su funcionalidad y decisiones de
  diseño que tomaron.
* `src/index.html`: este es el punto de entrada a tu aplicación. Este archivo
  debe contener to _markup_ (HTML) e incluir el CSS y JavaScript necesario.
* `src/cipher.js`: acá debes implementar el objeto cipher, el cual debe estar
  _exportado_ en el objeto global (`window`). Este objeto (`cipher`) debe
  contener dos métodos:
    - `cipher.encode(offset, string)`: `offset` es el número de posiciones que
       queremos mover a la derecha en el alfabeto y `string` el mensaje (texto)
       que queremos cifrar.
    - `cipher.decode(offset, string)`: `offset` es el número de posiciones que
      queremos mover a la izquierda en el alfabeto y `string` el mensaje
      (texto) que queremos decifrar.
* `src/index.js`: acá debes escuchar eventos del DOM, invocar `cipher.encode()`
  o `cipher.decode()` según sea necesario y actualizar el resultado en la UI.
* `test/cipher.spec.js`: este archivo contiene algunos tests de ejemplo y acá
  tendrás que implementar los tests para `cipher.encode()` y `cipher.decode()`.

### Tests

El _boilerplate_ incluye tests (pruebas) de ejemplo y todo el setup necesario
para implementar y ejecutar los tests, así como _code coverage_ para ver el
nivel de cobertura de los tests (ver consideraciones generales).

## Hacker edition

No estás limitada a implementar solo la parte obligatoria. Te sugerimos crear
también una función `cipher.createCipherWithOffset()` que reciba un `offset` y
devuelva un nuevo objeto con dos métodos (`encode` y `decode`) que solo reciban
el string y usen el `offset` que se pasó a `createCipherWithOffset` a la hora
de crear el objeto.

Lo anterior, nos ayuda a observar tu capacidad de autoaprendizaje, pudiendo
agregar a tu trabajo un elemento que lo lleva al siguiente nivel.

Lo mismo en Soft Skills, puedes realizar una planificación experta teniendo en
consideración la utilización de herramientas de planificación, como un
calendario, trello, papelógrafo u otras, creando un plan paso a paso de cómo
quiere abarcar el reto o problema. Realizando una estimación realista del
tiempo.

## Entrega

El proyecto será _entregado_ subiendo tu código a GitHub (`commit`/`push`) y la
interfaz será desplegada usando GitHub pages.

## Evaluación

### Tech

[tbd]

### UX

[tbd]

### Soft Skills

Para este reto queremos que intentes llegar al nivel 2 por lo menos en 5 de tus
soft skills, teniendo sólo 3 en el nivel 1. Te aconsejamos revisar la rúbrica.

* **Planificación y manejo del tiempo**: logras organizar el proyecto de manera
  general, estimando el tiempo de trabajo que debes invertir en éste.
* **Autoaprendizaje**: demuestras interés en adquirir conocimientos de forma
  autónoma, realizas preguntas sobre la materia, aclarando conceptos y
  resolviendo dudas, lo que te ayudar a realizar un mejor proyecto.
* **Solución de problemas**: buscas soluciones alternativas a las dificultades
  que se presentan durante el proyecto.
* **Dar y recibir feedback**: buscas instancias de feedback para tu proyecto,
  escuchando los comentarios y críticas de los demás de manera respetuosa.
  Además, entregas tu opinión de forma constructiva.
* **Adaptabilidad**: ante cambios o nuevos desafíos los recibes con una actitud
  positiva, a pesar de que esto implique una nueva organización.
* **Trabajo en equipo**: trabajas de manera coordinada con tu squad, apoyándote
  en él cuando sea necesario.
* **Comunicación eficaz**: logras comunicar tus ideas a los demás cuando es
  necesario.
* **Presentaciones**: cualquier persona puede acceder a tu demo desde cualquier
  equipo. Haces contacto visual con la audiencia y hablas en un volumen
  adecuado.

***

## Primeros pasos

1. Haz un _fork_ de este repositorio en tu cuenta de GitHub.
2. Clona el repo en tu computadora.
3. Instala las dependencias del proyecto con el comando `npm install` (o
   `yarn install` dependiendo de que _package manager_ estés usando).
4. Puedes ejecutar los tests con el comando `npm test` dentro de la carpeta del
   reto (o `yarn test`)

***

## Tips / Pistas

A continuación un video de Michelle que te lleva a través de la fórmula
matemática del Cifrado César y un par de cosas más que debes saber para
resolver este reto. ¡Escúchala con detenimiento y sigue sus consejos! :)

[![tips caesar cipher](https://img.youtube.com/vi/zd8eVrXhs7Y/0.jpg)](https://www.youtube.com/watch?v=zd8eVrXhs7Y)

También te compartimos más información de lo que Michelle te ha explicado en el
video anterior:

* [Aprende más sobre `charCodeAt()`](https://developer.mozilla.org/es/docs/Web/JavaScript/Referencia/Objetos_globales/String/charCodeAt)
* [Aprende más sobre `String.fromCharCode()`](https://developer.mozilla.org/es/docs/Web/JavaScript/Referencia/Objetos_globales/String/fromCharCode)
* [Aprende más sobre `ASCII`](http://conceptodefinicion.de/ascii/)
* [Documentación de NPM](https://docs.npmjs.com/)
* [Documentación de yarn](https://yarnpkg.com/en/)

Estos son algunos tips que te pueden ayudar en la organización y realización de
tu proyecto, teniendo en cuenta el desarrollo de tus _Soft Skills_ (habilidades
blandas):

* Para comenzar realiza una organización de tu proyecto, ve con qué recursos
  cuentas y el tiempo que tienes para completarlo.
* Si hay algo que no sepas pregunta e intenta resolverlo; puedes comenzar con
  una búsqueda en google, luego consultando a tu squad y por último a tus
  mentores. Si hay algo que yo no sé, otro me puede ayudar. El aprendizaje es un
  proceso colaborativo.
* Una vez que empieces a avanzar pide feedback, tus compañeras pueden tener
  excelentes ideas o formas de resolver el reto que te pueden ayudar.
* Cuando te topes con un problema, busca alternativas, y para eso consulta
  diferentes fuentes.
* Si ya te ves invirtiendo mucho tiempo en detalles debes saber priorizar y
  seguir con lo más importante, los proyectos tienen tiempo limitado y debes
  saber administrarlo.
* Trabaja en equipo, pregunta e intenta completar el reto sin rendirte.
* Prepara tu presentación, si no logro comunicar mis ideas a los demás no se
  podrá apreciar todo el esfuerzo y trabajo que invertiste.
