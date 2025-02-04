chat-BOT 👋🤖🤙
Versión npm Descargas

Interfaz de usuario de chatbot sencilla para la Web con secuencias de 👋🤖🤙 comandos JSON

Captura de pantalla

Rápida configuración e implementación.
Funciona con o sin clasificadores de lenguaje natural.
1KB GZipped. Sin dependencias. Escrito con ES5 (compatible con IE11+).
Demostración | Video tutorial

Instalación
Hilado/NPM
yarn add chat-bubble o npm install chat-bubble

Descargar
Obtenga el archivo .ZIP aquí.

Inicio rápido
Este método supone que tiene un entorno de desarrollo en ejecución que es capaz de transpilar JavaScript de ES6. Hay una breve guía sobre cómo hacer que uno funcione aquí. De lo contrario, consulte "No tengo ningún entorno de desarrollo de ES6". Esta guía te mostrará cómo construir esto.

/************************************************************************/
/******* CONVENIENCE METHODS AVAILABLE FOR ES6 BUILD ENVIRONMENTS *******/
/************************************************************************/

// the URL of where you've installed the component; you may need to change this:
import {
  Bubbles,
  prepHTML
} from "../node_modules/chat-bubble/component/Bubbles.js";

// this is a convenience script that builds all necessary HTML,
// imports all scripts and stylesheets; your container DIV will
// have a default `id="chat"`;
// you can specify a different ID with:
// `container: "my_chatbox_id"` option
prepHTML({ relative_path: "../node_modules/chat-bubble/" });

/************************************************************************/
/************************ SAMPLE IMPLEMENTATION *************************/
/************************************************************************/

// initialize by constructing a named function...
const chatWindow = new Bubbles(
  document.getElementById("chat"), // ...passing HTML container element...
  "chatWindow" // ...and name of the function as a parameter
);

// `.talk()` will get your bot to begin the conversation
chatWindow.talk(
  // pass your JSON/JavaScript object to `.talk()` function where
  // you define how the conversation between the bot and user will go
  {
    // "ice" (as in "breaking the ice") is a required conversation object
    // that maps the first thing the bot will say to the user
    ice: {
      // "says" defines an array of sequential bubbles
      // that the bot will produce
      says: ["Hey!", "Can I have a banana?"],

      // "reply" is an array of possible options the user can pick from
      // as a reply
      reply: [
        {
          question: "🍌", // label for the reply option
          answer: "banana" // key for the next conversation object
        }
      ]
    }, // end required "ice" conversation object

    // another conversation object that can be queued from within
    // any other conversation object, including itself
    banana: {
      says: ["Thank you!", "Can I have another banana?"],
      reply: [
        {
          question: "🍌🍌",
          answer: "banana"
        }
      ]
    } // end conversation object
  } // end conversation object
);
"¡No tengo ningún entorno de desarrollo de ES6!"
Si no quieres molestarte en configurar un servidor de desarrollo y un transpilador para el código ES6, lo entiendo. Simplemente descomprima el paquete y cree dentro de ese directorio. A continuación, agregue todo el JavaScript que vea debajo del comentario en el ejemplo de código anterior. Reemplace por .index.html/*SAMPLE IMPLEMENTATION*/constvar

<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>My chat-bubble Project</title>

    <!-- stylesheets are conveniently separated into components -->
    <link rel="stylesheet" media="all" href="../styles/setup.css" />
    <link rel="stylesheet" media="all" href="../styles/says.css" />
    <link rel="stylesheet" media="all" href="../styles/reply.css" />
    <link rel="stylesheet" media="all" href="../styles/typing.css" />
    <link rel="stylesheet" media="all" href="../styles/input.css" />
  </head>
  <body>
    <!-- container element for chat window -->
    <div id="chat"></div>

    <!-- import the JavaScript file -->
    <script src="./component/Bubbles.js"></script>
    <script>
      /************************************************************************/
      /**************** add "SAMPLE IMPLEMENTATION" code here *****************/
      /************************************************************************/
    </script>
  </body>
</html>
Ahora abra este archivo en su navegador. ¡Hecho!

Demostraciones y más ejemplos de uso:
Ejemplo básico: vea cómo se ve el código de arriba en el navegador.
Punto de inicio personalizado: ¿qué pasaría si quisiera reanudar la conversación desde otro lugar que no sea el punto de inicio requerido? Así es como lo harías.ice:{}
Entrada de teclado: una estructura básica similar a un complemento que le permite implementar su propia entrada de teclado y reconocimiento de texto (aunque no procesa el lenguaje natural).
Ejecutar scripts: las respuestas de tu bot pueden hacer cosas. No solo podría decir algo, sino que podría dirigir al usuario hacia una acción o realizarla mediante la ejecución de JavaScript.
La implementación del clasificador de lenguaje natural es posible con un esfuerzo adicional al interceptar el mensaje de respuesta y la entrada del teclado. Un ejemplo de uso de RASA (documentación) se puede encontrar aquí.
Echa un vistazo a la carpeta para ver el código fuente y más ideas./examples

Preguntas más frecuentes:
¿Puedo agregar imágenes y código HTML a mi bot?
¡Sí! gráficos personalizados, videos de YouTube, ¡lo que quieras!
¿Cómo puedo contribuir?
Consulte la guía de contribuciones aquí.
Cómprame un café: usa el botón "Patrocinador" de GH o hazlo a través de https://ko-fi.com/dmitrizzle
Compatibilidad con navegadores
Es posible que debas agregar polyfills para Object.assign() y String.includes()
