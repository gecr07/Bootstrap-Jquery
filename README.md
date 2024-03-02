# Jquery

Permite agregar comportamiento dinamico a los sitios se pueden usar muchos metodos que son los de java script. Como analogia javascript son legos puedes construir una ciudad pero tardas mucho poque es desde cero Jquery son edificios carreteras pre diseñados eso quiere decir que hace lo mismo que si lo hicieramos con JS pero ahorra tiempo y podrias construir laa ciudad mas rapido.

```javascript


jQuery gives us access to tons of different methods to add dynamic behavior to our sites, some methods you’ll see and use often including effects, events, and DOM manipulation:

effect methods:
.animate()
.delay()
.fadeIn()/.fadeOut()
.hide()/.show()
.toggle()
event methods:
.change()
.click()
.focus()
.hover()
.keydown()/.keyup()/.keypress()
.mouseenter()/.mouseleave()
.on()
.ready()
DOM manipulation methods:
.addClass()/.toggleClass()
.after()/.before()
.append()/.prepend()
.remove()
.val()
…again, there are many more methods to research and test. Check out the jQuery documentation for more methods that may be applicable to your site!

```

##  jQuery .ready() method

Este metodo espera a que toda la pagina se cargue debes de poner todo el codigo dentro de esta funcion.

> The jQuery .ready() method waits until the HTML page’s DOM is ready to manipulate. You should wrap all JavaScript behavior inside of the .ready() method. This will make sure the web page is rendered in the browser before any jQuery code executes.

```javascript
$(document).ready(() => {

});
```


## jQuery objects

Para crear objetos usamos $() para hacer referencias por tag id o clase. Por ejemplo para apuntar a todos los elementos que pertenescan a la clase ".product-photo" . Hacer esto hace un jquery object.

### Target by class

```
$(document).ready(() => {
$('.product-photo').show()

});
```

### Target by id

```
$(document).ready(() => {
  $('#nav-dropdown').hide();
});
```
Las variables para que se puedan diferenciar se le pone $ enfrente

```
const $jQueryObject = $('.someClass');
```

>  It is a naming convention that reminds you and lets others know that a given variable is a jQuery object.

## Event Handlers

El metodo de Jquery de on() es el encargado de añadir events handler recibe dos pararametros el nombre del evento por ejemplo el clic y el otro la call back function cuando para cuando el evento se desencadene.

```
$('#login').on('click', () => {
  $loginForm.show();
})

```

Como ejemplo define los objetos jquery y define un event handler para que cuando se hace clic muestre el menu.

```javascript
$(document).ready(() => {
  const $menuButton = $('.menu-button');
  const $navDropdown = $('#nav-dropdown');

$menuButton.on('click', () => {
 $navDropdown.show()
})

})

```


Ahora para mostrar y quitar cuanod el mouse se mueva


```
$(document).ready(() => {
  const $menuButton = $('.menu-button');
  const $navDropdown = $('#nav-dropdown');

  $menuButton.on('click', () => {
    $navDropdown.show();
  })
  
  $navDropdown.on('mouseleave', () => {
    $navDropdown.hide();
  })
})
```

Ejemplo de un proyecto para desplegar un menu 

```
$(document).ready(() => {

$('#cart').on('click', () => {
  $('#cartMenu').show();
})

$('#account').on('click', () => {
  $('#accountMenu').show();
})

$('#help').on('click', () => {
  $('#helpMenu').show();
})

$('.dropdown-menu').on('mouseleave',() => {
  $('.dropdown-menu').hide();
})

});
```

Puedes usar targets como imagenes.

```

$(document).ready(() => {
  
$('.hide-button').on('click', () => {
$('.first-image').hide()
  })


});

```
## toggle() 

Este metodo permite hacer show y hide osea neesitas  uno solo boton para ambas acciones.

```

$(document).ready(() => {
  $('.hide-button').on('click', () => {
    $('.first-image').hide();
  });
  
  $('.show-button').on('click', () => {
    $('.first-image').show();
  });
  
  $('.toggle-button').on('click', () => {
    $('.first-image').toggle();
  });
  
});
```


Como conclucion busca los metodos tienen toggle que hacen ambas acciones como mostrar y ocultar. Aqui tienes un pequeño ejemplo.

```
$(document).ready(() =>{

$('.hint-box').on('click', () => {
  $('.hint').slideToggle(500);
})


$('.wrong-answer-one').on('click', () => {
  $('.wrong-text-one').fadeOut('slow');
  $('.frown').show();
})

$('.wrong-answer-two').on('click', () => {
  $('.wrong-text-two').fadeOut('slow');
  $('.frown').show();
})

$('.wrong-answer-three').on('click', () => {
  $('.wrong-text-three').fadeOut('slow');
  $('.frown').show();
})

$('.correct-answer').on('click', () => {
  $('.frown').hide();
  $('.smiley').show();
})
});
```

Tengo otro ejemplo que te puede servir esconder todos los elemntos div.

```

$('.hide').on('click', () => {
  $('div').hide();
});
```

## Introduction to Mouse Events

Como siempre ya sabes que los eventos que hacen referencia a elementos html clases ids etc tinen event listener and a callback function. Ahora estos eventos van a hacer cosas cuando el mouse haga algo.

```
$(document).ready(() => {
  $('.login-button').on('click', () => {
    $('.login-form').show();
  });
  
  $('.menu-button').on('mouseenter', () => {
    $('.nav-menu').show()
  })
  
  $('.nav-menu').on('mouseleave', () => {
    $('.nav-menu').hide();
  })

  $('.product-photo').on('mouseenter', () => {
   $('.product-photo').addClass('photo-active');
  }).on('mouseleave', () => {
   $('.product-photo').removeClass('photo-active');
  })
  
})
```

En el ejemplo anterior se activa cuando pasas el mouse y cuando lo quitas se desactiva el zoom esto lo controlan agregando y eliminando clases.

## currentTarget

Para que cuando tu pases el mouse no todos los elementos se agan zoom es una cosa de this.


![image](https://github.com/gecr07/Bootstrap-Jquery/assets/63270579/6841d364-c783-4b31-afc7-4eb2d3d0fe8a)


```
$(document).ready(() => {
  $('.login-button').on('click', () => {
    $('.login-form').show();
  });
  
  $('.menu-button').on('mouseenter', () => {
    $('.nav-menu').show()
  })
  
  $('.nav-menu').on('mouseleave', () => {
    $('.nav-menu').hide();
  })
  
  $('.product-photo').on('mouseenter', event => {
    $(event.currentTarget).addClass('photo-active')
  }).on('mouseleave', event => {
    $(event.currentTarget).removeClass('photo-active')
  })
  
}); 

```

## Manejar texto ( importante para cosas de buscar etc)

Cuando cargas la pagina tienes que dar clic en donde quieres escribir bueno con esta linea al cargar la pagina solita se pone el cursor.

```
$('.postText').focus();
```

![image](https://github.com/gecr07/Bootstrap-Jquery/assets/63270579/279aded9-175b-4ffb-abba-1e6c578a545c)

Para este ejercicio se tiene que se usa el focul tambien los caracteres cuando escribes se va actualizando la varibale.

![image](https://github.com/gecr07/Bootstrap-Jquery/assets/63270579/e3f0c617-233b-4413-91ae-62078be69865)

```

$(document).ready(() => {

$('.menu').on('mouseenter', () => {

$('.nav-menu').show();

  })

$('.menu').on('mouseleave', () => {

$('.nav-menu').hide();

  })
  

  $('.btn').on('mouseenter', event => {
    $(event.currentTarget).addClass('btn-hover')
  }).on('mouseleave', event => {
    $(event.currentTarget).removeClass('btn-hover')
  })


$('.postText').on('keyup', event => {
let post = $(event.currentTarget).val();
let remaining = 140 - post.length;

if (remaining <=0) {

$('.wordcount').addClass('red')

}
else
{
$('.wordcount').removeClass('red')
}


$('.characters').html(remaining);




  })

$('.postText').focus();

});

```


![image](https://github.com/gecr07/Bootstrap-Jquery/assets/63270579/2745c01c-9363-47b5-a34a-fc0ba7ccc819)


## CSS & jQuery

Para este apartado jquery puede modificar las propiedades de css.

> To modify CSS properties of an element, jQuery provides a method called .css().

![image](https://github.com/gecr07/Bootstrap-Jquery/assets/63270579/15c2c85d-4b56-4e42-9b4c-5df9bc4d544b)



```
$(document).ready(() => {
 
  $('.login-button').on('click', () => {
    $('.login-form').toggle();
  });
  
  $('.menu-button').on('mouseenter', () => {
    $('.nav-menu').show();
     $('.menu-button').css('color', '#C3FF00');
  })
  
  $('.nav-menu').on('mouseleave', () => {
    $('.nav-menu').hide();
    $('.menu-button').css('color', '#EFEFEF');
  })
  
}); 

```

Incluso se puede pasar en formato clave valor para pasar muchas propiedades para modificar.


```
$(document).ready(() => {
 
  $('.login-button').on('click', () => {
    $('.login-form').toggle();
  });
  
  $('.menu-button').on('mouseenter', () => {
    $('.nav-menu').show();
     $('.menu-button').css({color: '#C3FF00',
  backgroundColor: '#535353'});
  })
  
  $('.nav-menu').on('mouseleave', () => {
    $('.nav-menu').hide();
    $('.menu-button').css({color: '#EFEFEF',
  backgroundColor: '#303030'});
  })
  
}); 

```


Tenemos aqui un ejemplo de como funciona ya todo:

![image](https://github.com/gecr07/Bootstrap-Jquery/assets/63270579/7be90ee0-1988-4064-8327-528785712332)


```
$(document).ready(() => {
  
  $('#text').on('keyup', event => {
  $('.preview').html($(event.currentTarget).val());
  
})

$('#font').on('change', event => {
  $('.preview').css({fontFamily: $(event.currentTarget).val()});
  
})

$('#weight').on('change', event => {
  $('.preview').css({fontWeight: $(event.currentTarget).val()
  });
  
})

$('#size').on('keyup', event => {
  let fontSize= $(event.currentTarget).val() + 'px';
  $('.preview').css({ fontSize: fontSize
  });
  
})

})
```

## Bootstrap

Bootstrap is a framework of readily available code that integrates with HTML to create stylized websites that adapt the layout to users’ screen sizes. Para incorporar Bootstrap a un proyecto, tenemos que incluir dos etiquetas <meta> y la biblioteca CSS Bootstrap. Para usar este framework se necesita poner dos tags meta y una link de la sigueinte manera.

```
<head>
    <!-- Required meta tags -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">

    <!-- Bootstrap CSS for styling and layout-->
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.1.3/css/bootstrap.min.css" integrity="sha384-MCw98/SFnGE8fJT3GXwEOngsV7Zt27NXFoaoApmYm81iuXoPkFOJwJ8ERdknLPMO" crossorigin="anonymous">
</head>

```

En este ejemplo bootstrap se obtiene desde una CDN. Existen algunas otras librerias que se puden agregar para agregar cosas interactivas y estas se agregan despues del <body>. Aqui tienes el link a la documentacion oficial.


``` htlm
<!doctype html>
<html lang="en">

<head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
    <!-- Add link to Bootstrap CDN below: -->
    
<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.1.3/css/bootstrap.min.css" integrity="sha384-MCw98/SFnGE8fJT3GXwEOngsV7Zt27NXFoaoApmYm81iuXoPkFOJwJ8ERdknLPMO" crossorigin="anonymous">

    <title>News Website</title>
</head>

<body>
    <div class="container">
        <header class="sticky-top">
            <div class="row flex-nowrap justify-content-between align-items-center bg-dark">
                <div class="col-4 pt-1">
                    <button type="button" class="btn btn-sm btn-outline-primary">Subscribe</button>
                </div>
                <div class="col-4 text-center">
                    <h1 class="text-white" href="#">News</h1>
                </div>
                <div class="col-4 d-flex justify-content-end align-items-center">
                    <a class="btn btn-sm btn-outline-light" href="#">Log In</a>
                </div>
            </div>
            <nav class="navbar navbar-expand-lg navbar-light bg-light">
                <a class="navbar-brand mx-auto" href="#">Categories:</a>
                <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
                    <span class="navbar-toggler-icon"></span>
                </button>
                
                <div class="collapse navbar-collapse" id="navbarSupportedContent">
                    <div class="navbar-nav mx-auto">
                        <a class="p-2 text-muted" href="#">US</a>
                        <a class="p-2 text-muted" href="#">Foreign</a>
                        <a class="p-2 text-muted" href="#">Technology</a>
                        <a class="p-2 text-muted" href="#">Business</a>
                        <a class="p-2 text-muted" href="#">Culture</a>
                        <a class="p-2 text-muted" href="#">ics</a>
                        <a class="p-2 text-muted" href="#">Opinion</a>
                        <a class="p-2 text-muted" href="#">Health</a>
                        <a class="p-2 text-muted" href="#">Economics</a>
                    </div>
                </div>
            </nav>
        </header>

        <div class="row">
            <div class="col-12">
                <div class="jumbotron p-3 p-md-5 rounded" style="background-image: url('https://content.codecademy.com/courses/learn-bootstrap-4/student-reading.jpg'); background-size: cover;">
                    <div class="col-12" style="background-color: rgba(0,0,0, 0.4);">
                        <h1 class="display-4 text-white">Kids Love to Read!</h1>
                        <p class="lead text-light my-3">Teachers say it starts at home! You should begin reading to
                            your children consistently at a young age.</p>
                        <p class="lead mb-0"><a href="#" class="text-white font-weight-bold">Continue reading...</a></p>
                    </div>
                </div>
            </div>
        </div>

        <div class="row mb-2">
            <div class="col-12 col-md-6">
                <div class="card mb-4 box-shadow">
                    <img class="card-img-top img-fluid" src="https://content.codecademy.com/courses/learn-bootstrap-4/recycle.jpg" alt="Card image cap">
                    <div class="card-body d-flex flex-column align-items-start">
                            <p class="d-inline-block mb-2 text-info font-weight-bold">Foreign</p>
                        <h3 class="mb-0">
                            <a class="text-dark" href="#">Filling the Gaps</a>
                        </h3>
                        <div class="mb-1 text-muted">Nov 12</div>
                        <p class="card-text">Developed countries have reduced their plastic usage and
                            adopted sustainable living practices. This change has slowed down the effects of
                            climate change for developing nations.</p>
                        <a href="#">Read More</a>
                    </div>
                </div>
            </div>
            
            <div class="col-12 col-md-6">
                <div class="card mb-4 box-shadow">
                    <img class="card-img-top img-fluid" src="https://content.codecademy.com/courses/learn-bootstrap-4/polling-station.jpg" alt="Card image cap">
                    <div class="card-body d-flex flex-column align-items-start">
                        <p class="d-inline-block mb-2 text-warning font-weight-bold">Politics</p>
                        <h3 class="mb-0">
                            <a class="text-dark" href="#">Record High for Young US Voters</a>
                        </h3>
                        <div class="mb-1 text-muted">Nov 11</div>
                        <p class="card-text">American voters under 30 years old came out in droves for
                            the last election. This trend is inspiring the youths of other democratic nations.</p>
                        <a href="#">Read More</a>
                    </div>
                </div>
            </div>
        </div>
            
        
        <div class="row">
            <div class="col-12">
                <div class="p-3 mb-3 bg-light rounded">
                    <h4>About</h4>
                    <p class="mb-0"><span class="font-italic">Your news fast and accurate!</span> At News, we take the news very
                        seriously. We guarantee real news from certified, experience journalists.</p>
                </div>
            </div>
        </div>
        
        <div class="row">    
            <div class="col-6">
                <h4 class="font-italic">Archives</h4>
                <ol class="list-unstyled">
                    <li><a href="#">October 2018</a></li>
                    <li><a href="#">September 2018</a></li>
                    <li><a href="#">August 2018</a></li>
                    <li><a href="#">July 2018</a></li>
                </ol>
            </div>
            <div class="col-6">
                <h4 class="font-italic">Social</h4>
                <ol class="list-unstyled">
                    <li><a href="#">YouTube</a></li>
                    <li><a href="#">Twitter</a></li>
                    <li><a href="#">Facebook</a></li>
                </ol>
            </div>
        </div>
    </div>

    <!-- jQuery first, then Popper.js, then Bootstrap JS -->
    <script src="https://code.jquery.com/jquery-3.3.1.slim.min.js" integrity="sha384-q8i/X+965DzO0rT7abK41JStQIAqVgRVzpbzo5smXKp4YfRvH+8abtTE1Pi6jizo" crossorigin="anonymous"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.3/umd/popper.min.js" integrity="sha384-ZMP7rVo3mIykV+2+9J3UJ46jBk0WLaUAdn689aCwoqbBJiSnjAK/l8WvCWPIPm49" crossorigin="anonymous"></script>
    <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.1.3/js/bootstrap.min.js" integrity="sha384-ChfqqxuZUCnJSK3+MXmPNIyE6ZbWh2IMqE241rYiqJxyMiZ6OW/JmZQ5stwEULTy" crossorigin="anonymous"></script>
</body>

</html>
```

### Intro to the Grid

Los contenedores son la base de la cuadrícula de Bootstrap. Dentro de los contenedores, anidamos filas como hijos inmediatos. Luego, las filas interiores anidadas son columnas.

![image](https://github.com/gecr07/Bootstrap-Jquery/assets/63270579/d3ed0a03-9de2-48a7-8af7-aad03dfdac0a)

El codigo para representar esto seria:

```
<div class="container">
  <div class="row">
    <div class="col">
      <!-- A column inside a row inside a container! -->
    </div>
  </div>
</div>
```
Y ya si quiere suna vista mas general.

![image](https://github.com/gecr07/Bootstrap-Jquery/assets/63270579/5185837d-7f96-4d1f-aa0e-32b9865f3de4)


Bootstrap como ya se vio funciona como el CSS Flex(entiendo que es por bloques)

```
<div class="container">
  <div class="row">
  </div>
</div>

```

![image](https://github.com/gecr07/Bootstrap-Jquery/assets/63270579/5e8d0d60-2c8d-4293-84e3-79d0ef850d0a)


Nos ponen ejemplos:

```
    <div class="container">
      <!--First row-->
			<div class="row">
        <div class="col">
          <h3>One Column in a row</h3>
        </div>
      </div>

      <!--Second row-->
      <div class="row">
				<div class="col">
          <p>Two columns in a row</p>
        </div>
				<div class="col">
          <p>Two columns in a row</p>
        </div>
      </div>
      
      <!--Third row-->
			<div class="row">
				<div class="col">
          <p>Three columns in a row</p>
        </div>
				<div class="col">
          <p>Three columns in a row</p>
        </div>
				<div class="col">
          <p>Three columns in a row</p>
        </div>
      </div>
    </div>
```

![image](https://github.com/gecr07/Bootstrap-Jquery/assets/63270579/83396ee3-bcf7-422b-bc2a-3d55e409a363)

Column Widths

Podemos manejar el tamaño de largo de las columans el Widths

```

    <div class="container">
			<div class="row">
        <div class="col-9">
					<p>Differently</p>
        </div>
        <div class="col-3">
          <p>Sized</p>
        </div>
      </div>

```

![image](https://github.com/gecr07/Bootstrap-Jquery/assets/63270579/3f9375d1-7858-432f-90ac-d2cc488599c4)

Se puede ajustar dependiendo por ejemplo del texto

```
<div class="col-auto">
  <p>This content determines the width of the parent column</p>
</div>

```

## Bootstrap Breakpoints

Este punto tiene que ver con que bootstrap es responsive.

![image](https://github.com/gecr07/Bootstrap-Jquery/assets/63270579/3008708f-f2c7-4bb5-b3c3-b337b5befc72)

![image](https://github.com/gecr07/Bootstrap-Jquery/assets/63270579/c2c8dc0c-4080-484c-9d7f-b0bee6d8d2f5)

![image](https://github.com/gecr07/Bootstrap-Jquery/assets/63270579/5e896d9f-9518-48cc-bd62-c2da2f4498ba)


## Clases

Se pueden poner mas de una clase a los tags para tener mas control.

```
<div class="col-12 col-md-8">
</div>
```

###  BOOTSTRAP 4: UTILITIES AND COMPONENTS

Puedes cambiar el estilo basicamente de todo.


```
  <p class="text-warning">
    Change the text color in this paragraph to yellow.
  </p>

```

Tambien puedes usar botones y componentes ya hechos has de cuenta que ya traen todo nada mas copias y pegas el codigo. Checa esta definicion: 

> The first component we’ll investigate is the navigation (nav) component which offers our users a collection of links. The nav component is slightly different from a navbar component. The nav component is often specific to one or a few webpages, whereas a navbar often appears on all the pages of a website.

```
<ul class="nav">
  <li class="nav-item">
    <a class="nav-link" href="#">First Link</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" href="#">Second Link</a>
  </li>
</ul>

```











