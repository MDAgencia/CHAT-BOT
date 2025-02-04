# chat-BOT 👋🤖🤙

## Versión npm y Descargas
Interfaz de usuario de chatbot sencilla para la Web con secuencias de comandos JSON.

### Características
- Configuración e implementación rápida.
- Funciona con o sin clasificadores de lenguaje natural.
- Ligero: solo 1KB GZipped.
- Sin dependencias.
- Escrito en ES5 (compatible con IE11+).


## Instalación

### Usando Yarn/NPM
```sh
yarn add chat-bubble
o
npm install chat-bubble
```

## Inicio rápido
Este método supone que tiene un entorno de desarrollo que puede transpilar JavaScript de ES6. Consulte esta [guía](#) para configurarlo.

Si no tiene un entorno de desarrollo de ES6, consulte la sección **"¡No tengo un entorno de desarrollo de ES6!"**.

### Implementación en ES6
```javascript
import { Bubbles, prepHTML } from "../node_modules/chat-bubble/component/Bubbles.js";

// Configurar el contenedor de chat
prepHTML({ relative_path: "../node_modules/chat-bubble/" });

// Inicializar la ventana de chat
const chatWindow = new Bubbles(
  document.getElementById("chat"),
  "chatWindow"
);

// Definir la conversación
chatWindow.talk({
  ice: {
    says: ["¡Hola!", "¿Me das un plátano?"],
    reply: [
      {
        question: "🍌",
        answer: "banana"
      }
    ]
  },
  banana: {
    says: ["¡Gracias!", "¿Me das otro plátano?"],
    reply: [
      {
        question: "🍌🍌",
        answer: "banana"
      }
    ]
  }
});
```

## ¡No tengo un entorno de desarrollo de ES6!
Si no desea configurar un servidor de desarrollo, simplemente descomprima el paquete y cree dentro del directorio. Luego, agregue el siguiente código en `index.html`:

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <title>Mi Proyecto chat-bot</title>
    <link rel="stylesheet" media="all" href="../styles/setup.css" />
    <link rel="stylesheet" media="all" href="../styles/says.css" />
    <link rel="stylesheet" media="all" href="../styles/reply.css" />
    <link rel="stylesheet" media="all" href="../styles/typing.css" />
    <link rel="stylesheet" media="all" href="../styles/input.css" />
</head>
<body>
    <div id="chat"></div>
    <script src="./component/Bubbles.js"></script>
    <script>
      // Agregar código de implementación aquí
    </script>
</body>
</html>
```

Ahora abra este archivo en su navegador. ¡Listo!

## Demostraciones y ejemplos
- **Ejemplo básico**: Cómo se ve el código en el navegador.
- **Punto de inicio personalizado**: Reanudar la conversación desde otro punto que no sea `ice`.
- **Entrada de teclado**: Implementación personalizada para reconocimiento de texto.
- **Ejecución de scripts**: Permite que el bot ejecute acciones mediante JavaScript.

💡 **Soporte para clasificadores de lenguaje natural**: Se puede integrar con RASA u otros modelos interceptando mensajes de respuesta y entradas del teclado.

📂 Revisa la carpeta `/examples` para más ejemplos y código fuente.

## Preguntas frecuentes

### ¿Puedo agregar imágenes y código HTML a mi bot?
¡Sí! Puedes agregar gráficos personalizados, videos de YouTube y más.


## Compatibilidad con navegadores
Es posible que necesites agregar polyfills para `Object.assign()` y `String.includes()` en navegadores antiguos.

