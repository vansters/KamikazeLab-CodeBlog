---
layout: post
title: "Iniciando con Octopress"
date: 2014-07-06 22:03:42 -0500
comments: true
categories: 
---
### Que es Octopress ?

Antes que cualquier cosa comencemos hablando de forma rápida que es Octopress:

> Octopress es un framework diseñado por Brandon Mathis usando Jekyll,
> este consiste en un generador de sitios estáticos, que se convierten en los post .

En lo personal nos parece que octopress es un buena solución para hacer un blog simple y rápido, sin
tener que desarrollar todas las funcionalidades que un blog necesita, pero por otro lado es una plataforma
que por su naturaleza ( buscar hacer un blog rápido y fácil ) es poco personalizable de primera instancia,
si se requiere tomarse un tiempo para generar un estilo propio y funcionalidades distintas a los por defecto.

No por nada vemos a lo largo de la red un numero considerable de blog con el mismo estilo, como este jajaja.
Pero poco a poco iremos personalizando este blog y claro escribiendo nuestro camino en ese proceso.


### Como montar tu blog con Octopress ?

Primeramente necesitamos un par de cosa muy simples:

* Saber un poco de [Git](http://git-scm.com/book/es) y tenerlo instalado.
- Tener instalado [Ruby](https://www.ruby-lang.org/en/downloads/) ya que Octopress y su base están desarrolladas en este lenguaje.
+ Tener ganas de escribir n_n.

#### Paso 1: Clonar el repositorio oficial de octopress [Link Repo](https://github.com/imathis/octopress). 

``` bash Clonando el repositorio de octopress https://github.com/imathis/octopress 
$ git clone git://github.com/imathis/octopress.git Nombre-del-Blog
```
#### Paso 2: Instalando dependencias.

**2.1** Primero que nada entramos a la carpeta creada al clonar el repositorio.

``` bash Entramos a la carpeta de Octopress
$ cd Nombre-del-Blog
```
**2.2** Ahora instalaremos [Bundler](http://bundler.io/), este es un gestor de pendencias de ruby,
tal como **npm** para [Nodejs](http://nodejs.org/) o **composer** para **php**. Bundler es una gema muy importante en el mundo de ruby, ayuda a instalar de manera amigable las dependencias de cualquier proyecto.

``` bash Instalamos Bundler http://bundler.io/
$ gem install bundler
$ bundle install
$ bundle update rake
$ rake install
```
Expliquemos lo que hicimos en las cuatro lineas anteriores. En la linea 1 instalamos la gema **bundler**, que ya comentamos arriba, en la linea 2 iniciamos el comando para instalar todas las dependencias declaradas en el archivo **Gemfile**, el manejo de dependencias es una practica que debería ser adoptada por todos los desarrolladores sin importar el lenguaje que utilicen, facilita mucho el flujo de trabajo y ademas el compartir o colaborar en proyectos comunitarios, la linea 3 y 4  primero actualizan la gema rake y después proceden a inicializarla. [Rake](https://github.com/jimweirich/rake) es un constructor de aplicaciones ruby, desarrollado de primara instancia para el framework [Ruby On Rails](http://rubyonrails.org/) pero ahora es adoptado por la comunidad ruby para automatizar muchas tareas.

Hasta este punto nuestro blog es funcional, podemos comenzar a generar nuestro primer post y verlo en funcionamiento en nuestro ambiente local.

### Creando nuestro primer post octopress

Ahora que nuestro proyecto octopress ya tiene todas sus dependencias instaladas podemos proceder 
a crear nuestro primer post, vamos a requerir ayuda nuevamente de rake para ello.

``` bash Creando un post
$ rake new_post["Titulo del post"]
```
Una ves ejecutada esta acción nuestro primer post se creara como un archivo dentro de la ruta ***/Nombre-del-Blog/source/_post/año-mes-día-titulo-del-post.markdown***, dentro de este archivo encontraremos algo parecido a la siguiente:

``` text Archivo del nuevo post - año-mes-día-titulo-del-post.markdown
---
layout: post
title: "Titulo del post ..."
date: xxxx-xx-xx xx:xx:xx -0x00
comments: true
categories: 
---
```

Si modificamos un poco el archivo de nuestro primer post como el siguiente tendremos finalizado 
nuestro primer post.

``` text Archivo del nuevo post modificado - año-mes-día-titulo-del-post.markdown
---
layout: post
title: "Titulo del post ..."
date: xxxx-xx-xx xx:xx:xx -0x00
comments: true
categories:
---
### Nuestro primer post en octopress ?

Hola Octopress
```

Ahora con la ayuda de **rake** generaremos el blog y la previsualización del mismo, para que podamos visitar en nuestro navegador.

``` bash Previsualizando el blog
$ rake generate
$ rake preview
```
Si accedes en tu navegador a [http://localhost:4000/Nombre-del-Blog/](http://localhost:4000/Nombre-del-Blog/)
tendrás algo muy parecido a esto:

<img src="{{ root_url }}/images/Basic_Blog_2014-07-06 23:53:26.png" />

Bueno pues hasta aquí dejare este post, en la siguiente entrada profundizaremos en la configuración y como poner en [GitHub Pages](https://pages.github.com/) este sistema de blogging estático. 

Gracias por leernos este post fue escrito por nuestro colaborador **Mario Andrade** [@TheVansters](https://twitter.com/TheVansters).
