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























































