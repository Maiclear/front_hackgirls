#Mi primer landing page

Genial ahora pondremos en práctica lo que aprendimos de HTML y CSS pero agregaremos un componente nuevo y es bootstrap. imagino que estas pensando que es bootstrap, bueno Boostrap es un framework mobile first desarrollado por la gente de Twitter y liberado a la comunidad; nos permite desarrollar sitios web responsive e interfaces de forma rápida combinando CSS, HTML5 y Jquery, y es eso lo que vamos a realizar ahora.

Como desafío vamos enseñar a construir el siguiente landing page

// pega foto

Ya verás que con bootstrap no es complejo y podremos poner nuestros conocimientos en práctica, asi que manos a la obra.

## Iniciando el proyecto
Lo primero que debemos hacer es instalar bootstrap, para esto existen diferentes mecanismos de instalación, pero solo utilizaremos una de ellas, comencemos!

Primero debemos descargar los archivos fuentes de bootstrap. Para ello hacemos click en el siguiente [enlace](https://github.com/twbs/bootstrap/releases/download/v3.3.7/bootstrap-3.3.7-dist.zip) 

El archivo lo deben guardar en alguna carpeta de tu computador. Para esta guía la nombraremos bootstrap_landing. Dentro de la carpeta debemos dejar el fichero comprimido que descargamos, luego lo debemos descomprimir quedando la siguiente estructura de directorios.

```
bootstrap_demo/
├── css/
│   ├── bootstrap.css
│   ├── bootstrap.css.map
│   ├── bootstrap.min.css
│   ├── bootstrap.min.css.map
│   ├── bootstrap-theme.css
│   ├── bootstrap-theme.css.map
│   ├── bootstrap-theme.min.css
│   └── bootstrap-theme.min.css.map
├── js/
│   ├── bootstrap.js
│   └── bootstrap.min.js
└── fonts/
    ├── glyphicons-halflings-regular.eot
    ├── glyphicons-halflings-regular.svg
    ├── glyphicons-halflings-regular.ttf
    ├── glyphicons-halflings-regular.woff
    └── glyphicons-halflings-regular.woff2
``` 

## Configuración template básico
Ahora debemos crear un archivo nuevo que lo nombraremos __index.html__ (puede ser cualquier nombre). 

Debemos abrir el archivo nuevo con nuestro editor de texto sublime text. En el contenido del archivo __index.html__ debemos copiar y pegar el siguiente contenido.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <!-- The above 3 meta tags *must* come first in the head; any other head content must come *after* these tags -->
    <title>Landing Page</title>

    <!-- Bootstrap -->
    <link href="css/bootstrap.min.css" rel="stylesheet">

    <!-- HTML5 shim and Respond.js for IE8 support of HTML5 elements and media queries -->
    <!-- WARNING: Respond.js doesn't work if you view the page via file:// -->
    <!--[if lt IE 9]>
      <script src="https://oss.maxcdn.com/html5shiv/3.7.3/html5shiv.min.js"></script>
      <script src="https://oss.maxcdn.com/respond/1.4.2/respond.min.js"></script>
    <![endif]-->
  </head>
  <body>
    <h1>Hello, world!</h1>

    <!-- jQuery (necessary for Bootstrap's JavaScript plugins) -->
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/1.12.4/jquery.min.js"></script>
    <!-- Include all compiled plugins (below), or include individual files as needed -->
    <script src="js/bootstrap.min.js"></script>
  </body>
</html>
```

Este contenido representa **Basic template** de bootstrap y será nuestro punto de partida.

___¿Cómo podemos saber si bootstrap se instaló de forma correcta?___

Entre la etiquetas <body>  y </body> agregar <input type="button" value="Funciono!!" class="btn btn-primary">

Si nos aparece lo siguiente

![Bootstrap work!](images/bootstrap_work.png)

Todo está funcionando. 

## Definiendo las secciones de nuestro landing
Para construir nuestro landing lo primero que debemos es mirar nuestro diseño y segmentarlo en los diferentes bloques que estan propuestos, para definir cada bloque utilizaremos de forma correcta las etiquetas de HTML5 como header, footer, aside y section. Si quieres saber más de esto revisa el siguiente [link](#).

// pega foto con landing y segmentación en bloques

Lo que se presenta en la foto anterio lo debemos llevar código, para ello escribiremos los siguientes bloques dentro de la etiqueta body. (recuerda que todo lo que ve el visitante de tu sitio va dentro de body)

El esqueleto de nuestro landing lo definiremos de la siguiente forma

```
  <header>

  </header>

  <section class="block">
    
  </section>

  <section class="block alt">
    
  </section>

  <section class="block info">
    
  </section>

  <footer>
    
  </footer>

```

Si te fijas etiquete las secciones con algunas clases, esto lo veremos más adelante pero será de mucha utilidad para aplicar nuestras reglas de css.

Dentro de cada bloque colocaremos lo siguiente
```
<div class="container">
    <div class="row">
      
    </div>
  </div>
```

Este bloque define un contenedor de un ancho que bootstrap proporciona y cambia en función del tamaño de nuestro viewport*. Con el bloque row nos permitirá colocar columnas de forma segura sin que se desarme nuestro diseño. Si quieres saber más detalles como funciona la clase .row visita el siguiente [link](#) que se explica en detalle el concepto de clearfix & row.

Ahora podemos ir definiendo las diferentes columnas en función de layout que estamos intentando construir.

Comencemos con el header. Si revisas la imagen te daras cuenta que el header contiene una imagen de fondo, una frase principal (nuestro h1), dos botones, una frase de bajada (un p) y un menú. Para este último utilizaremos [navbar de bootstrap](http://getbootstrap.com/components/#navbar). Ahora todos estos elementos en el header deberían quedar de la siguiente forma

```

  <header class="main">

      <div class="container">
          <div class="row">
              <div class="col-md-12">
                  <nav class="navbar navbar-default navbar-latam">
                    <div class="container-fluid">
                      <!-- Brand and toggle get grouped for better mobile display -->
                      <div class="navbar-header">
                        <button type="button" class="navbar-toggle collapsed" data-toggle="collapse" data-target="#menu" aria-expanded="false">
                          <span class="sr-only">Toggle navigation</span>
                          <span class="icon-bar"></span>
                          <span class="icon-bar"></span>
                          <span class="icon-bar"></span>
                          
                        </button>
                        <a class="navbar-brand" href="#">
                            <img src="images/latam_logo.png" alt="Logo latam" class="logo">
                        </a>
                      </div>

                      <!-- Collect the nav links, forms, and other content for toggling -->
                      <div class="collapse navbar-collapse" id="menu">

       
                        <ul class="nav navbar-nav navbar-right">
                          <li><a href="#">Equipo</a></li>
                          <li><a href="#">Blog</a></li>
                          <li><a href="#">Contacto</a></li>

                        </ul>
                      </div><!-- /.navbar-collapse -->
                    </div><!-- /.container-fluid -->
                  </nav>
              </div>
          </div>
          <div class="row">
              <div class="col-md-8 col-md-offset-2">
                <h1 class="headline text-center">Comienza una nueva vida y únete al mundo tecnológico</h1>
                <p class="text-center">
                    <button class="btn btn-primary btn-lg">Comienza Acá</button>
                    <button class="btn btn-success btn-lg">Más info!</button>
                </p>   

                <p class="text-center headline-caption">Hay una escasez gigante de desarrolladores en el mundo y más aún en Latinoamérica, se necesitan más desarrolladores y Tú puedes ser uno!</p>
              </div>
          </div>
      </div>
  </header>

```

Al colocar este código ya podrías ver en tu navegador como va quedando el landing. si te fijas lo que vemos es solo estructural, asi que tranquila ya le pondremos color :D.

El elemento más complejo de este bloque es el menú. Bootstrap nos provee un menú ya construido y solo debemos copiar y pegar (si como lo escuhas copiar y pegar pero con un poco de talento :D).

El menú por si solo está definido en el siguiente bloque:


```
<nav class="navbar navbar-default navbar-latam">
                    <div class="container-fluid">
                      <!-- Brand and toggle get grouped for better mobile display -->
                      <div class="navbar-header">
                        <button type="button" class="navbar-toggle collapsed" data-toggle="collapse" data-target="#menu" aria-expanded="false">
                          <span class="sr-only">Toggle navigation</span>
                          <span class="icon-bar"></span>
                          <span class="icon-bar"></span>
                          <span class="icon-bar"></span>
                          
                        </button>
                        <a class="navbar-brand" href="#">
                            <img src="images/latam_logo.png" alt="Logo latam" class="logo">
                        </a>
                      </div>

                      <!-- Collect the nav links, forms, and other content for toggling -->
                      <div class="collapse navbar-collapse" id="menu">

       
                        <ul class="nav navbar-nav navbar-right">
                          <li><a href="#">Equipo</a></li>
                          <li><a href="#">Blog</a></li>
                          <li><a href="#">Contacto</a></li>

                        </ul>
                      </div><!-- /.navbar-collapse -->
                    </div><!-- /.container-fluid -->
                  </nav>
```

si todo funciona correctamente, ya deberíamos tener nuestra página con un menú que funciona en pantallas pequeñas. 

__¿y el logo donde lo colocamos?__

Navbar provee un pequeño bloque para colocar nuestro bloque. Acá colocaremos el logotipo de nuestro diseño. este bloque debería quedar así

```
<a class="navbar-brand" href="#">
    <img src="images/latam_logo.png" alt="Logo latam" class="logo">
</a>
```

¿Funciona la imagen? la respuesta en no :/. esto se debe a que debemos cargar la imagen en nuestro proyecto. Para ello crearemos una carpeta al mismo nivel que css, y le colocaremos el nombre de __images__ dentro de ella copiamos la imagen del logo (la puedes descargar desde [acá](#))

Si te fijas y vuelves a abrir la página ya verás el logo (no se verá del todo bien pero ya lo mejoraremos :D)

Sigamos con las siguientes secciones. Ahora enfoquemonos en la siguiente sección. La siguiente sección tenemos menos elementos y es más simple. Acá tenemos un título de menor jerarquia (lo definiremos como h3), un texto y una imagen. 

```

  <section class="block">
    <div class="container">
      <div class="row">
        <div class="col-md-12">
          <h3 class="text-center">Lorem ipsum dolor sit amet, consectetur adipisicing elit</h3>
          <p class="text-center">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Nesciunt, qui, necessitatibus. Perferendis pariatur quae, vero, voluptate saepe soluta itaque rerum earum sit alias harum repudiandae eos molestias magnam iusto, voluptatibus.</p>

          <p class="text-center">
            <img src="images/people.png" alt="" class="people">
          </p>
        
        </div>

      </div>
    </div>
  </section>

```

Si te fijas bien estoy definiendo columnas de 12, si bien no es necesario, lo definiremos para ser consistentes con el uso de columnas.

Probemos lo que llevamos ahora. Recuerda que solo estamos definiendo elementos estructurales (para eso es HTML)

Sigamos con la siguiente sección

// analogo a lo anterior

Uff! ya estamos casi. nos queda la última sección. A diferencia de las anteriores esta la dividiremos en dos columnas. la primera será de 4 columnas y la segunda 8 para completar las 12 columnas que necesitamos. Por lo que nos quedaría de la siguiente forma:

```
  <section class="block info">
    <div class="container">
      <div class="row">
        <div class="col-md-4">
          
        </div>
        <div class="col-md-8">
    
        </div>
      </div>
    </div>
  </section>
```

En la columna de 4 colocaremos nuestra dirección de la siguiente forma
```
<h3>Contacto</h3>
  <address>
    <strong>Twitter, Inc.</strong><br>
    1355 Market Street, Suite 900<br>
    San Francisco, CA 94103<br>
    <abbr title="Phone">P:</abbr> (123) 456-7890
  </address>
```

Estamos usando la etiqueta address que nos permite indicarle a los motores que ese bloque corresponde a una dirección.

Ahora en la columna de 8, colocaremos el formulario

```
 <h3>Suscribete</h3>
          <form class="form-inline">
         
            <div class="form-group">
              
              <input type="email" class="form-control" id="exampleInputEmail2" placeholder="jane.doe@example.com">
            </div>
            <button type="submit" class="btn btn-default">Send invitation</button>
          </form>
```
Para el formulario estamos usando los elementos de bootstrap que hace que nuestros form queden cool! si quieres saber más revisa la documentación de [boostrap referente a los formularios](http://getbootstrap.com/css/#forms)

El bloque completo quedaría de la siguiente forma
```
 <section class="block info">
    <div class="container">
      <div class="row">
        <div class="col-md-4">
          <h3>Contacto</h3>
          <address>
            <strong>Twitter, Inc.</strong><br>
            1355 Market Street, Suite 900<br>
            San Francisco, CA 94103<br>
            <abbr title="Phone">P:</abbr> (123) 456-7890
          </address>
        </div>
        <div class="col-md-8">
          <h3>Suscribete</h3>
          <form class="form-inline">
         
            <div class="form-group">
              
              <input type="email" class="form-control" id="exampleInputEmail2" placeholder="jane.doe@example.com">
            </div>
            <button type="submit" class="btn btn-default">Send invitation</button>
          </form>
        </div>
      </div>
    </div>
  </section>
```

Finalmente nos queda definir el pie de la página. Esto será simple y se reduce a lo siguiente

```
  <footer>
    <div class="container">
      <div class="row">
        <div class="col-md-12">
          <p>Hackgirls 2016 / Frontend Day.</p>
        </div>
      </div>
    </div>
  </footer>
```

Con esto ya tenemos nuestro código base para comenzar a pintar. Te perdiste? no te preocupes [acá](#) puedes revisar el código completo. 

## Colocando un poco de color (CSS)
... pendiente
