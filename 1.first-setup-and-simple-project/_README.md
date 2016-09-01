# Instalar Node.js
  Instalar la última versión estable 4.X de Node.js. En este momento, la versión estable actual es la v4.5.0 LTS.
  La descarga se puede realizar mediante el siguiente [Enlace](https://nodejs.org/en/)

# Instalar Polymer-cli
  Desde el terminal, introducir la siguiente sentencia:
  ```sh
  $ npm install -g polymer-cli
  ```
  Desde este momento, ya tendremos disponible en nuestra consola el comando polymer para poder trabajar con él.

# Crear un proyecto nuevo a partir de un template

  ```sh
  $ mkdir app-ejemplo
  $ cd app-ejemplo
  $ polymer init starter-kit
  ```

# Servir el proyecto
  Por último, para servir nuestro proyecto en localhost y ser lanzado en el navegador, escribimos en consola:
  ```sh
  $ polymer serve --open
  ```
  Llegados a este punto, tendremos en el navegador un proyecto base de Polymer, en el que podemos observar un menú lateral con tres enlaces, y cada uno de ellos nos cambia de página. A continuación, continuaremos trabajando sobre este proyecto de ejemplo para ir conociendo más cosas sobre Polymer.

 # Incluir una nueva página
En este apartado, incluiremos una nueva página a nuestro proyecto. Los pasos serán los siguientes:
##### Crear el elemento para nuestra nueva página
Crear un fichero nuevo en la carpeta src/ llamado *my-new-view.html* e incluir el siguiente código:

```html
<link rel="import" href="../bower_components/polymer/polymer.html">

<dom-module id="new-view">
  <!-- Defines the element's style and local DOM -->
  <template>
    <style>
      :host {
        display: block;

        padding: 16px;
      }
    </style>

    <h1>New view</h1>
  </template>
  <!-- Creates the element's prototype and registers it -->
  <script>
    Polymer({
      is: 'new-view'
    });
  </script>
</dom-module>
```
Analizando nuestra nueva página, vemos cómo en ella se distribuye la declaración de la misma bajo el tag dom-module, estilos y HTML que contiene bajo el tag template y la creación del elemento propiamente en el tag script. Por ahora, nuestro template únicamente contiene una etiqueta h1, pero avancemos poco a poco.

##### Inluir nuestro elemento al proyecto
Ya tenemos nuestra nueva página creada, ahora tenemos que añadirla a nuestra página principal. Para ello, haremos lo mismo que con las otras páginas:

  - En el fichero src/my-app.html, nos situamos en la siguiente parte del código:
      ```html
      <iron-pages
        selected="[[page]]"
        attr-for-selected="name"
        fallback-selection="view404"
        role="main">
      <my-view1 name="view1"></my-view1>
      <my-view2 name="view2"></my-view2>
      <my-view3 name="view3"></my-view3>
      <my-view404 name="view404"></my-view404>
    </iron-pages>
      ```
  - Incluimos la nueva página en el contenedor de la página principal:
    ```html
    <new-view name="new-view"></new-view>
    ```
  - Añadimos un enlace para que el usuario pueda acceder a nuestra nueva página dentro del tag <iron-selector>:
    ```html
    <a name="new-view" href="/new-view">New View</a>
    ```
Listo, ahora al recargar la página, en nuestro menú lateral aparecerá una nueva opción, la cual nos lleva a la página que hemos creado.

Por último, aunque no es necesario realmente(solo es necesario si vamos a hacer un build y posterior despliegue), incluímos en el fichero *polymer.json* nuestra nueva página en el array de *fragments*, con lo que quedaría de la siguiente manera:

```javascript
"fragments": [
    "src/my-view1.html",
    "src/my-view2.html",
    "src/my-view3.html",
    "src/my-new-view.html",
    "src/my-view404.html"
 ]
```
