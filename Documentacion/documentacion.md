Isx1535386Franlin Colque S. 2018
================================

DOCUMENTACIÓN
=============

Implantación de una aplicación web estática en Github Pages con jekyll.
=======================================================================

Pasos a seguir para la creación de esta web estática :

1\. Crear las distintas páginas html en el entorno de desarrollo.

2\. Podemos añadir alguna funcionalidad añadiendo código javascript, que
se ejecutará en el cliente. (esta no la tocaremos ya que no es necesario
para nuestra web estatica)

3\. El entorno de producción necesita sólo un servidor web. 

4\. El despliegue podemos hacer usando un servidor ftp para subir los
ficheros al servidor.

Ventajas de las páginas estáticas:

-   Portabilidad, funcionan en cualquier servidor.
-   Tiempos de acceso óptimos, tardan muy poco en cargarse.
-   Facilitan el posicionamiento.
-   Costos de alojamiento menores.
-   Mínimos requerimientos técnicos para su operación.

Desventajas de las páginas estáticas:

-   Funcionalidad muy limitada
-   No se pueden realizar búsquedas en la página.
-   El visitante no tiene ninguna posibilidad de seleccionar, ordenar o
    modificar los contenidos o el diseño de la página a su gusto. (ya
    que solo nosotros seremos capaces de modificar a nuestro gusto)
-   El administrador web debe acceder al servidor donde está alojada la
    página para cambiar los contenidos de la página ya sea de nuestro
    repositorio github en local o directamente en la pagina de github.
-   El proceso de actualización es lento, tedioso y
    esencialmente manual.
-   No se accede a bases de datos (esto puede ser también una ventaja)

Github Pages
------------

Es un servicio que te ofrece Github para publicar de una manera muy
sencilla páginas web. Disponemos de la opción de generar de forma
automática las páginas utilizando una herramienta gráfica, o la creación
y modificación de páginas web usando la línea de comandos con el comando
git.

### Cómo podemos construir nuestras páginas web

La forma más sencilla de construir nuestro sitio es subir a nuestro
repositorio todos los ficheros necesarios: ficheros html, markdown ,
hojas de estilos (css), javascript, imágenes, etc. Si sólo tuviéramos
esta opción de edición de páginas no tendríamos grandes ventajas para
decidirnos a escoger este servicio de hosting.

Lo que realmente hace esta herramienta una opción muy potente es que
Github Pages soporta jekyll, herramienta escrita en Ruby que nos permite
generar, de una forma muy sencilla, ficheros HTML estáticos. Aunque esta
herramienta esta pensada para generar blogs,voy a utilizar algunas de
sus funcionalidades para crear un portfolio sobre mi mismo.

### Usando Jekyll para crear páginas web

La principal característica de Jekylls es la generación de html estático
a partir de dos recursos muy simples:

-   Plantillas (templates): Ficheros que contienen el esqueleto de las
    página html que se van a generar. Yo partire de un template básico
    para a si poder modelarlo a mi gusto.
-   Ficheros de contenido: Normalmente escritos en sintaxis Markdown y
    que contienen el contenido de la página que se va a generar.

Por lo tanto una vez que tengo definidas mis plantillas, y los ficheros
necesarios que tocare serán en html general y la hoja de estilo css.

Guía rapido de github antes de crear la plantilla minima de jekyll:

-Crearemos un nuevo fichero en donde trabajeroms con nuestro projecto:

\[isx1535386@i02 \~\]\$ mkdir PROJECTE

-Para cada cambio de algun fichero haremos las siguiente orden para
subir los cambios a la web github:

\[isx1535386@i02 PROJECTE\]\$ git add .

\[isx1535386@i02 PROJECTE\]\$ git status

\[isx1535386@i02 PROJECTE\]\$ git commit -am "segon commmit"

-→para subir al repositorio principal

\[isx1535386@i02 PROJECTE\]\$ git push -u origin master

-→Para bajarte los cambios de la web github

\[isx1535386@i02 PROJECTE\]\$ git pull origin master

--&gt; Ver el historial de commits que se han generado

\[isx1535386@i02 PROJECTE\]\$ git log

--&gt; Para que no te pida el passwd , primero tendrás que conectarte
con una clave ssh\_keygen, y vincularlo con tu cuenta. Y luego hacer la
siguiente orden.

\[isx1535386@i02 PROJECTE\]\$git push SSH-franlin master

Haremos la ultima orden al final de cada cambio de nuestra web estatica.

Ahora si Pasos para crear la plantilla mínima que luego modificaremos
evidentemente:

Primero Instalamos los paquetes siguientes de jekyll para configurar
nuestro sistema:

\[isx1535386@i02 PROJECTE\]\$ sudo dnf install rubygems rubygems-devel
ruby-devel gcc-c++

\[isx1535386@i02 PROJECTE\]\$ sudo dnf install redhat-rpm-config

\[isx1535386@i02 PROJECTE\]\$ sudo gem install jekyll

\[isx1535386@i02 PROJECTE\]\$ gem install bundler

\[isx1535386@i02 PROJECTE\]\$ gem install minima

\[isx1535386@i02 PROJECTE\]\$cp -r \~/.gem/ruby/gems/minima-\*/\* .

\[isx1535386@i02 PROJECTE\]\$ sed -i 's/\^theme:/\#&/' \_config.yml

Para no estar haciendo un git push cada vez que modificamos el fichero
hacemos la siguiente orden

y despues en firefox ponemos
“[*http://localhost:4000*](http://localhost:4000/)” para visualizar los
cambios

\[isx1535386@i02 PROJECTE\]\$ jekyll serve –watch

Documentacion de los .html utilizados y sus respectivos .css

Ruta donde se encuentra mi html principal:
**Francs9.github.io/\_site/index.html**

Ruta donde se encuentra el CSS principal:**Francs9.github.io/\_site
/assets**/**css**/**main.css**

###1\. Creacion de titulo y encabezado de mi pagina:

En esta parte hacemos un header para la creacion del el titulo “h1” y su
subtitulo “&lt;p&gt;” y tambien hacemos los diferentes titulos en el
borde extremo derecho parar ir pasando a la parte indicada en los
diferentes puntos:

&lt;header id="home"&gt;

&lt;div class="content-wrap"&gt;

&lt;nav&gt;&lt;a href="\#about-me"&gt;Sobre mi&lt;/a&gt;

&lt;a href="\#Experenice"&gt;Experiencias&lt;/a&gt;

&lt;a href="\#Blog"&gt;Blog&lt;/a&gt;

&lt;a href="\#Details"&gt;Contactame&lt;/a&gt;

&lt;/nav&gt;

&lt;h1&gt;

&lt;span&gt;Franlin colque&lt;/span&gt;

&lt;/h1&gt;

&lt;p class="kicker"&gt;Estudiante de ASIR // Estudiante de Ingles
&lt;/p&gt;

&lt;/div&gt;

&lt;/header&gt;

###2.Creacion de un breve resumen sobre mi:

Para este apartado hacemos un breve resumen sobre mi persona , con su
respectivo “h2” y su descripción.”&lt;p&gt;”

&lt;section&gt;&lt;h2 id="about-me"&gt;Breve descripcion sobre
mi:&lt;/h2&gt;

&lt;div class="blurb"&gt;

&lt;p&gt;hola me llamo franlin colque , vivo en Barcelona (Hospitalet de
llobregat)

actualmente estoy estudiando el curso de administración de sistemas
informatico en red.

Tambien estoy en una academia de ingles en
Barcelona&lt;/p&gt;&lt;/div&gt;&lt;div class="skill-lock"&gt;

&lt;/div&gt;

&lt;/section&gt;

**3.Descripcion sobre mis experiencias:**

3.1 Aqui hago una breve experiencia academica separados por años

&lt;div class="history"&gt;

&lt;div class="cd-timeline-header"&gt;

&lt;h2 id="Experenice"&gt;Experiencias&lt;/h2&gt;

&lt;hr class="bar"/&gt;

&lt;/div&gt;

&lt;section id="cd-timeline" class="cd-container"&gt;

\*Aqui hago unos blocks para separar cada experiencia de mi:

Primer bloque para explicar sobre los estudios de secundaria

&lt;div class="cd-timeline-block"&gt;

&lt;div class="cd-timeline-content"&gt;

&lt;h2 class="story-heading"&gt;Estudiante de la secundaria&lt;/h2&gt;

&lt;P&gt;Estudie y termine el instituto en este año en mi Pais de
procedencia Bolivia&lt;/P&gt;

&lt;span class="cd-date"&gt;2010-2013&lt;/span&gt;

&lt;/div&gt;

&lt;!-- cd-timeline-content--&gt;&lt;!-- cd-timeline-block--&gt;

&lt;/div&gt;

Segundo bloque para explicar sobre los estudios post obligatorios.

&lt;div class="cd-timeline-block"&gt;

&lt;div class="cd-timeline-content"&gt;

&lt;h2&gt;Estudios Postobligatorios&lt;/h2&gt;

&lt;p&gt;Estudie el bachillerato cientifico en Cataluña.

Habia llegado recientemente de mis pais y tuve una dificial

adapctación pero al final si que pude.&lt;/p&gt;

&lt;span class="cd-date"&gt;sept 2013&lt;/span&gt;

&lt;/div&gt;

Tercer bloque para explicar sobre los estudios de grado Superios que
estoy cursando:

&lt;div class="cd-timeline-block"&gt;

&lt;div class="cd-timeline-content"&gt;

&lt;h2&gt;Estudiante de cfgs&lt;/h2&gt;

&lt;p&gt;Al acabar bachillerato decidi Estudiar un ciclo superior

de informatica porque es lo más me aposionaba y es lo que continuo

estudiando.&lt;/p&gt;

&lt;span class="cd-date"&gt; Sept 2016&lt;/span&gt;

&lt;/div&gt;

Quinto bloque con su respectivo h2 (header) y su texto plano (p)

&lt;div class="cd-timeline-block"&gt;

&lt;div class="cd-timeline-content"&gt;

&lt;h2&gt;Academia de Ingles&lt;/h2&gt;

&lt;p&gt;Empeza la academia de ingles porque me era imprescindible

para formarme en la familia de informática&lt;/p&gt;

&lt;span class="cd-date"&gt;Sept 2017 - now&lt;/span&gt;

&lt;/div&gt;

&lt;!-- cd-timeline-content--&gt;&lt;!-- cd-timeline-block--&gt;

&lt;/div&gt;

Ultimo bloque para explicar sobre mis aficiones y poco mas

&lt;div class="cd-timeline-block"&gt;

&lt;div class="cd-timeline-content"&gt;

&lt;h2&gt;Mis aficiones&lt;/h2&gt;

&lt;p&gt;El futbol y el basket son mis principales aficiones.&lt;/p&gt;

&lt;span class="cd-date"&gt;Aficiones&lt;/span&gt;

&lt;/div&gt;

&lt;!-- cd-timeline-content--&gt;&lt;!-- cd-timeline-block--&gt;

&lt;/div&gt;

###4\. Detalles sobre como he realizado el contacto y el logotipo de
facebook, github y youtube:

\*Dividimos el contacto hacia mi en dos secciones el de información
sobre mi y poder contactarme con un mensaje directamente a mi.

4.1 información sobre mi:

Hacemos un “href ” que apunte a cada icono de github facebook i youtube.
Y despues hacemos un link que apunte a gmail , con mi gmail especificado
debajo de ello.

&lt;section class="section-contact"&gt;

&lt;h2 id="Details"&gt;Detalles de contacto&lt;/h2&gt;

&lt;hr class="bar"/&gt;

&lt;div class="social-links"&gt;

&lt;a href="https://www.facebook.com/"&gt;

&lt;div class="glyph-icon flaticon-facebook3"&gt;

&lt;/div&gt;

&lt;/a&gt;

&lt;a href="https://github.com/Francs9"&gt;

&lt;div class="glyph-icon flaticon-github"&gt;

&lt;/div&gt;

&lt;/a&gt;

&lt;a href="https://www.youtube.com"&gt;

&lt;div class="glyph-icon flaticon-youtube31"&gt;

&lt;/div&gt;

&lt;/a&gt;

&lt;/div&gt;

&lt;hr class="bar"/&gt;

&lt;a href="https://www.gmail.com"
class="biglink"&gt;&lt;b&gt;franlincol999@gmail.com&lt;/b&gt;&lt;/a&gt;

&lt;/section&gt;

4.2 Mensaje para contactarme :

Lo hacemos en otra sección para dejarme un mensaje y un boton para
enviar(que reenviara a gmail).

&lt;section&gt;

&lt;h2 id="Contact"&gt;Contactame&lt;/h2&gt;

&lt;hr class="bar"/&gt;

&lt;form method="post" action="//formspree.io/example@gmail.com"&gt;

&lt;div class="contact-info-group"&gt;

&lt;label&gt;

&lt;span&gt;Nombre&lt;/span&gt;

&lt;input type="text" name="name"/&gt;

&lt;/label&gt;

&lt;label&gt;

&lt;span&gt;Email&lt;/span&gt;

&lt;input type="email" name="\_replyto"/&gt;

&lt;/label&gt;

&lt;/div&gt;

&lt;label&gt;

&lt;span&gt;Mensaje&lt;/span&gt;

&lt;textarea name="Message"&gt;&lt;/textarea&gt;

&lt;div class="submit-wrap"&gt;

&lt;input type="submit" value="Enviar"/&gt;

&lt;/div&gt;

&lt;/label&gt;

&lt;/form&gt;

&lt;/section&gt;

###5\. Por último añado un footer pequeño al final para volver a poner
subtitulos que apunten a cada sección creada con anterioridad

&lt;footer&gt;&lt;div class="lockup"&gt;

&lt;div class="content-wrap"&gt;&lt;nav&gt;

&lt;a href="\#about-me"&gt;Sobre mi&lt;/a&gt;

&lt;a href="\#Experenice"&gt;Experiencias&lt;/a&gt;

&lt;a href="\#Blog"&gt;skills&lt;/a&gt;

&lt;a href="\#Details"&gt;Contactame&lt;/a&gt;

&lt;/nav&gt;&lt;p class="copyright"&gt;Franlin colque 2018&lt;/p&gt;

&lt;/div&gt;

&lt;/div&gt;

&lt;/footer&gt;

 &lt;/body&gt;

&lt;/html&gt;

##CSS:

Para el css estilo de la página usamos una plantilla muy básica ,que
luego modificamos de la siguiente manera.

###1\. Para el cuerpo de la pegina

Ponemos un fondo de color celeste en hexadecimal

Y tambien el color de las letras de contacto a negro(black)

body {

/\*cambiomos el color de fondo a celeste\*/

 background: \#67e8ec;

 font-size: 14px;

 line-height: 1.6;

 font-family: 'Open Sans' sans-serif;

/\*cambiomos el color de la letras de contacto\*/

 color: black;

 -webkit-font-smoothing: antialiased;

 -webkit-text-size-adjust: 100%; }

###2.La descripcion sobre mi

Centramos la descripcion al medio y el color de las letras lo ponemos ha
azul.

Usamos un padding para determinar el espacio de relleno del texto.

h2 {

 color: blue;

 text-align: center;

 padding: 50px 0 30px; }

###3.Determinamos el tipo de fuente y color de las secciones.

Lo aplicamos a todos los estilos de letras de la descripoción.

h2, header nav a, header .kicker, footer .lockup a, \#h\_small
\#nav\_small a, \#h\_small .kicker {

 font-size: 14px;

 font-weight: 700;

 text-transform: uppercase;

 color:black;

 }

###4.Ponemos un fondo

Ponemos una imagen de fondo en el titulo principal indicando la url con
la ruta absoluta de la imagen y luego la centramos .

header {

 background: url(../img/kk2.jpg) center center;

 background-size: cover; }

###5.Secciones

Cambiamos de color a la elección de secciones a silver con un margen
correspondiente.

 header nav a {

 margin-left: 20px;

/\*cambiomos color de contacto \*/

 color: silver; }

Tambien lo haccemos con el header o la cabezera principal.

 header h1 {

 text-align: center;

/\*cambiomos color de titulo\*/

 color: silver;

 text-transform: uppercase;

 letter-spacing: 0.05cm;

 margin-bottom: 20px;

 clear: both; }

###6\. La cabezara del final.

Hacemos el mismo fondo que la parte de arriba:

footer {

 background: url(../img/kk2.jpg) center center;

 background-size: cover; }

El color de mi nombre en rojo:

 color:red;}

 footer .lockup a {

Y el de contacto lo ponemos a silver como el header principal el (sobre
mi,experiencias,blog contactame.)

 color:silver;

 display: inline-block;

 margin-right: 30px; }

 footer .lockup a:hover {

 color: black; }

###7\. Logotipos de las redes sociales

Ponemos un color de fondo a blanco y las imagenes tal cual estaban.

 .social-links .glyph-icon:before {

 display: block;

 font-size: 60px;

 line-height: 70px;

/\*cambiamo color de logos de contactos youtube,facebook y twiter\*/

 color: white;

 -webkit-transition: all 0.15s ease-out 0s;

 transition: all 0.15s ease-out 0s;

 margin-left

Ponemos un color de letras del portfolio en hexadecimal.

.

.cd-container {

 background: \#e5eaee;

 width: 90%;

 max-width: 1070px;

 margin: 0 auto; }

 .cd-container::after {

 content: '';

 display: table;

 clear: both; }

###8\. Contenedores de cada descripcion de la sección de experiencias :

Lo hacemos de un medida maxima de los cuadros de 960px con margen 0 y un
padin de texto al máximo.

Y hcemos lo mismo para cada contenedor.

.thumb-container {

 max-width: 960px;

 margin: 0px auto;

 padding-bottom: 100px; }

 .thumb-container::after {

 clear: both;

 content: "";

 display: table; }

 .thumb-container .thumb-unit {

 display: block;

 width: 25%;

 float: left;

 position: relative;

 padding: 10px;

 padding-top: 20%;

 overflow: hidden;

 background-image: url(../img/project.png);

 background-position: center center;

 background-repeat: no-repeat;

 background-size: cover; }

 .thumb-container .thumb-unit .thumb-overlay {

 position: absolute;

 top: 100%;

 right: 0px;

 left: 0px;

 height: 100%;

 background: rgba(201, 144, 101, 0.9);

 -webkit-transition: all 0.15s ease-out 0s;

 transition: all 0.15s ease-out 0s; }

 .thumb-container .thumb-unit:hover .thumb-overlay {

 position: absolute;

 top: 0%;

 right: 0px;

 left: 0px; }
