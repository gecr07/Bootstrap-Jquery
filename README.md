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

































