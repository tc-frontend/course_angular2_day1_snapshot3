Angular 2: Getting Started - SnapShot 3
===================
En esta parte veremos estos contenidos del curso de Pluralshight:

 - Data Binding & Pipes


----------


### 1 - Data Binding


----------


En esta sección vamos a ver uno por uno cata tipo de binding que podemos aplicar en Angular2. Todos los tipos están ejemplificados en la siguiente imagen:


![enter image description here](https://i.imgur.com/aAYMGm0.png)


Gracias al motor de Angular cualquier modificación en ejecución de las propiedades del componente lanza el refresco de los bindings generados en la vista. 


.

 
#### Interpolation 


[Binding One-Way]


Con la interpolación lo que se consigue es poder renderizar en el HTML el valor de una propiedad o el valor de retorno de una función expuesta a través del componente.

En el momento en el que a la propiedad se le modifique el valor la vista se refrescará automáticamente.


.


#### Property Binding 


[Binding One-Way]


Con el property binding será posible enlazar una propiedad a la vista pudiendo a su vez aplicar expresiones condicionales o Pipes como más adelante se verá. Sigue siendo un Binding OneWay


 - NOTA: Se puede incluso enlazar estilos: **[style.width.px]='imageWitdh'**


![enter image description here](https://i.imgur.com/tes1f2h.jpg)


.


#### Event Binding


[Binding One-Way]


Con event binding podemos enlazar un evento del DOM al componente TypeScript. 


Es posible generar un binding Two-way si se combina el Property Binding con el Event Binding. Podemos reaccionar a un evento del DOM y en el componente actualizar alguna propiedad que esté enlazada a la vista.


 - $event: Con este binding tabién es posible enviar el payload del evento. Algo propio de javascript. Ejemplo: **(click)='metodo($event)'**


![enter image description here](https://i.imgur.com/YWzI30S.jpg)


.


#### Two-Way Binding


¿Cómo funciona el Two-Way binding? 


 - **ngModel**: es una propiedad pública de cualquier componente Angular


 - Angular por debajo crea una instancia de **FormControl**. 


 - La clase FormControl se enlazará a la propiedad **Value** del control **Input** y a su vez se enlazará a la propiedad **listFilter** del componente Angular. De esta forma FormControl no deja de ser un intermediario entre el control Input y la propiedad del componente y se encarga de propagar los cambios en ambos sentidos. [FormControl Class](https://angular.io/docs/ts/latest/api/forms/index/FormControl-class.html) 
 

- **NOTA**: Es más. Cuando se define un formulario completo en Angular con **ngForm** que se verá más adelante en este curso, en realidad lo que ocurre por debajo es que Angular está generando un **FormArray** de instancias de **FormControl** para todos los controles HTML del formulario.


- **Es necesario incluir el Módulo de Forms de Angular en el app.module.ts**: 


    import { FormsModule } from '@angular/forms'
    
    @ngModule ({
         imports : [
            BrowseModule,
            FormsModule
         ],
    ....



![enter image description here](https://i.imgur.com/4gvl9Rp.jpg)


.


----------


### 2 - Pipes


----------


Las Pipes son mecanismos para formatear valores antes de ser mostrados en la vista. Permite definir una transformación de datos asociada al Binding de una propiedad.

Hay varias pipes predefinidas en Angular para formatear strings, números, moneda, fechas, etc. Incluso se pueden crear Pipes customizadas por nosotros.



![enter image description here](https://i.imgur.com/LSYnF6E.jpg)


.


----------


### Práctica


----------


Para ello clonamos el **SnapShot 3** desde el primer commit:

    git clone https://github.com/tc-frontend/course_angular2_day1_snapshot3
    cd course_angular2_day1_snapshot3
    git checkout tags/init
    npm install
    code .
 
----------
#### 1 - Añadir imagen del producto y enlazar las propiedades

    <img [src]='product.imageUrl'
        [title]='product.productName'
        [style.width.px]='imageWith'
        [style.margin.px]='imageMargin'>

https://goo.gl/k6EnGk


----------
#### 2 - Añadir evento click al botón

Implementar la lógica necesaria para mostrar u ocultar la imagen. También se pide condicionar el texto a mostrar en el botón dependiendo Show/Hide

https://goo.gl/CM8VF3


----------
#### 3 - Usar Two-way binding

Utilizar two-way binding para enlazar el textbox del filtro a propiedad filter de la clase.
Es necesario importar en el módulo principal FormsModule.

https://goo.gl/tY9Tdf



----------
#### 4 - Utilizar pipes para formatear el precio y para poner en minúsculas el código producto


https://goo.gl/bV8hf8

----------

Seguimos los pasos detallados en el historial de commits:

https://goo.gl/nx0eWb  
  
Si queremos ver la App en nuestro browser

    npm start

Si queremos ver la solución final de este SnapShot:

    git checkout master
    npm install
    npm start


