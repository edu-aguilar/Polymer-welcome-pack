![alt tag](https://www.polymer-project.org/images/logos/p-logo.png)

# Polymer-welcome-pack

  Conjunto de ejemplos y definiciones para comenzar a trabajar con la librería basada en WebComponents conocida como Polymer.


# ¿Qué es Polymer?

  Polymer es una librería javascript desarrollada por Google que funciona en base a los estándares de WebComponents.

Los WebComponents son un estándar del W3C que nos permiten dividir el desarrollo de aplicaciones web en pequeños contenedores, que conoceremos como componentes, que contienen código HTML, CSS y JavaScript.
Esto conlleva una gran posibilidad: poder reutilizar dichos componentes en diferentes partes de nuestras aplicaciones y, a su vez, poder reutilizarlos en otros proyectos.

Para aquellos conocedores del framework AngularJS, y que se interesan por Polymer, como forma introductoria podríamos hacer un símil para entender los componentes con las ya conocidas directivas de Angular. Elementos con marcado HTML, controlador(lógica) y estilos propios.


# Elementos de un WebComponent

  Los WebComponents se componen de cuatro elementos complementarios, pero independientes entre sí:

- ##### Custom elements
  Consiste en la creación de etiquetas de marcado HTML para identificar de forma sencilla y semántica a un componente.

- ##### Templates
  Son las plantillas HTML que representan los datos de nuestro componente, y son nativos del navegador.

- ##### Shadow DOM
  Es el DOM que encapsula nuestro componente, aquello que incluyamos en nuestro WebComponent puede ser completamente ajeno al resto del documento web. De esta forma, evitaremos solapamiento de CSS, y tendremos un ámbito propio de ejecución de código JavaScript. Pensemos en ello como un DOM anidado al DOM primario de nuestro documento web.

- ##### HTML Imports
  Gracias a los HTML Imports tenemos la posibilidad de importar ficheros HTML que contengan WebComponents a nuestro proyecto.
