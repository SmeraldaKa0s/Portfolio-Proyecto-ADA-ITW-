# Observaciones

Alex, felicitaciones por tu trabajo. Me encanta como se ve tu portfolio y la cantidad de detalles que agregaste. Los efectos en el hover, la barra de navegación, el responsive tan cuidado, todo habla de un altisimo nivel de detalle que se nota y hace que tu web sea muy agradable de recorrer. 

Como dije en clase, este trabajo no se hace para que constates conocimientos, sino para que aprendas: en ese sentido, mi intencion es que estos comentarios te sirvan para aprender, mejorar tu codigo a futuro e ir apreciando mejor qué se espera de nosotras como desarrolladoras front end.

## Estructura correcta de documento HTML

Cumplido en general. 

Algo que me llama la atención es tu `header`, dado que allí repetís innecesariamente muchísimos links.

```html
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
<!-- ... -->
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
<!-- ... -->
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
<!-- ... -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
```

Cada uno de esos links hace exactamente lo mismo - traerse el css de google fonts para poder usar los fonts en tu sitio. Quizá estés bajo la impresión de que por cada uno de los fonts de tu web es necesario traerse nuevamente estos css, pero no, no es necesario agregarlo más de una vez. Agregar muchos de estos links innecesarios impacta negativamente en la velocidad de carga de tu web, ya que por cada uno de ellos se hace un llamado a un css externo y se lo carga. Esto para cada uno de los distintos css que te importas. Deberia haber solo uno de cada uno. La excepcion, claro, son las distintas tipografias, que tienen cada una su css. 

Tenés cierta tendencia a tener divs de más. Algunas estructuras de tu web se podrían resolver con menos divs. Dicho esto, yo prefiero que los divs sobren antes de que falten: un div de más se soluciona muy fácil, un div menos puede ser un gran dolor de cabeza cuando estamos recién arrancando. Este sería un comentario que quizá me reservaría para futuros trabajos, pero veo tan bien tu código que me siento confiada en recomendarte que empieces a ver estas cosas desde ya. 

Si tenés ganas, con tiempo, te diría que valdría la pena recorrer tu html y notar que estructuras como esta se pueden hacer más breves. Tambien prestale atención al tabulado:

```html
      <section class="contenedor-cita">

            <div class="conocimientos-seccion">

                <i class="fas fa-quote-right quote-icon"></i>

                <blockquote>
                    <p class="descripcion-parrafo">El ser humano debe ser capaz de cambiar pañales, planear una
                        invasión, sacrificar un cerdo, gobernar un barco, diseñar un edificio, escribir un soneto,
                        reducir una fractura, consolar a los moribundos, recibir órdenes, dar órdenes, resolver
                        ecuaciones, abonar la tierra, programar una computadora, cocinar una comida
                        sabrosa, combatir con eficacia, morir con gallardía. La especialización es para los insectos.
                    </p>
                </blockquote>

                <h2 class="autorx">Robert Heinlein</h2>

            </div>
        </section>
```

Todos los estilos del div `conocimientos-seccion` se podrían llevar al `section` sin problema, y el `blockquote` no cumple ninguna función así que se podría sacar también. Notá también que el nombre conocimientos-seccion aquí no tiene ningún sentido. 

Te lo comento aquí como un ejemplo, pero esto es algo que se repite a lo largo de tu código. 

## Respeta la consigna

- El portfolio cuenta con las secciones solicitadas
- Al clickear en los links de navegación, debe llevar a la sección correspondiente
- Al clickear en los links de contacto, debe llevar a la página externa
  correspondiente
- El portfolio debe tener un diseño responsivo y verse correctamente en distintos dispositivos
- El portfolio debe estar deployado y ser accesible desde una URL
- El repositorio en GitHub debe tener un readme adecuado

Todos estos puntos están cumplidos. Menciono especialmente tu responsive: es increíble lo bien que solucionaste las distintas resoluciones, siguiendo casi a la perfección el modelo y preocupandote para que todo se vea hermoso, veamos tu web desde cualquier dispositivo. Ahora bien, para lograrlo adoptaste dos estrategias que no son ideales:

- Tenes muchas mas media queries que las necesarias. Comenté en clase que la guia de bootstrap para las media queries me parece la mejor, te la dejo acá. Si notas que necesitas una media para 500, una para 560, una para 600... es una buena pauta de que quizá haya algo que no está bien resuelto a nivel HTML y CSS. Con flex bien aprovechado no debería ser necesario tener tantas media queries. 


```css
/* Celulares */
@media (max-width: 576px) { ... }

/* Celulares en modo horizontal y tablets pequeñas */
@media (max-width: 768px) { ... }

/* Tablets  */
@media (max-width: 992px) { ... }

/* Monitores pequeños */
@media (max-width: 1200px) { ... }

/* Monitores grandes */
@media (max-width: 1400px) { ... }
```

Nuevamente, este es un punto bastante complejo y que normalmente no señalaría en esta etapa, pero viendo la alta calidad de tu trabajo me siento confiada sugiriendotelo. 

### Respeta el diseño dado

Cumplido a la perfección. Noto algún apego a varias estructuras del HTML y CSS del modelo de Ada, especialmente en la seccion de "Mis proyectos". Por supuesto, el codigo de esa web es público y sabemos y comprendemos que ocasionalmente vas a mirarlo para despejar algunas dudas, pero algunos problemas parecen obvios de solucionar cuando ves como lo hace el modelo: esa no es la única manera. La mejor, por supuesto, es la que se te ocurra a vos.

### Buena estructura de proyecto

Usás muchas imágenes en tu proyecto, y viéndolo a primera vista en github no es tan fácil ver cuáles son los archivos principales. Siempre que uses imágenes locales, como en este caso, agregalas a una carpeta que se llame por ejemplo "imgs", "imagenes" o "assets". De esta manera solo los archivos principales - html, readme y css - son los que están en la carpeta principal. La excepción a esta regla es el favicon, que siempre debería ir en la carpeta principal y llamarse "favicon.ico"

### Código bien indentado

Tabulas en general muy bien, lo cual parece un detalle extra cuando una recien comienza pero ayuda un monton a su legibilidad, y que lo hayas logrado en esta etapa es un gran mérito. Tenés muchísimos saltos de linea innecesarios que dificultan seguir el HTML. 

### Comentarios que permiten mejorar la legibilidad del código

Impecables en HTML. Aunsentes en css, donde mas se necesitan, y tenes algo de codigo comentado. Esto no es buena práctica, es el equivalente de tachar algo en un texto impreso para la facu. Mejor borrarlo. No debería haber código comentado en una entrega a menos que sea un mensaje para otros desarrolladores o una indicación de secciones. 

### Uso correcto de etiquetas semánticas

En general usas bien las etiquetas semánticas. Me llama la atención que hayas usado `div` o `a` para las tarjetas de Mis Conocimientos y Mis Proyectos: yo diría que deberían ser `article`. Pero es el único detalle a comentar aquí (y hay quien podría discutirme que deberían ser divs)

### Buenos nombres de clases

En general está cumplido. 

Ocasionalmente veo que reutilizaste código CSS, lo cual está perfecto, pero mantuviste el nombre de clase anterior: no tiene sentido que la seccion de la cita se llame "conocimientos-seccion". Si tienen el mismo estilo que otro, debes encontrar un nombre que se aplique a ambos. 

Noto algunas clases que tienen identidades confusas y problemas con lo que consideramos "descriptivo". Cuando decimos que un nombre de clase debe ser descriptivo, lo decimos en un sentido funcional: qué rol cumple este elemento en el código. Los colores de los elementos, su forma, su estilo, su posición, todas esas cosas pueden cambiar y efectivamente cambian todo el tiempo en las webs que hacemos. El botón que hoy es violeta mañana será azul; la sección que estaba a la derecha mañana estará arriba. Por lo tanto esos factores sos no son buenos descriptores, y no deberían ser parte de nuestros nombres de clases. Cosas como sección "secciondos" deberían cambiarse para representar qué son en tu página: la sección que tiene una cita, el formulario de contacto.

Ocasionalmente tenés clases que no usas en tu css. Para que está "proyectos", por ejemplo?

### Código CSS bien estructurado

Cumplido a nivel formal. Noto algunos estilos innecesarios o confusos, que te voy indicando en tu archivo de css.

### Reutilización de estilos

Cumplido en general

### Cumple con criterios básicos de accesibilidad

- Los colores tienen un contraste adecuado

Cumplido para los elementos principales, pero lo perdés en los detalles, especialmente en los hover y en la seccion de la cita. 

- Las imágenes tiene el atributo `alt` que corresponde

Se nota la intención de cumplirlo, pero comentamos en clase que el lector de pantalla ignora los iconos a menos que tengan "role=img", asi que no esta cumplido para ellos. 

- Los íconos y elementos que no presentan texto agregan la información correspondiente por otros medios (etiquetas aria, texto oculto)

No cumplido.

- Los íconos y elementos que no necesitan ser anunciados por un lector de pantalla tienen la etiqueta aria correspondiente

No cumplido. 

- Commits con mensajes adecuados

Cumplido, noto muchos y buenos commits en tu proyecto, lo que siempre se agradece.

- Cuenta con un favicon

Cumplido, aunque debería ser un archivo llamado favicon.ico y estar en la carpeta principal

### Nota: 9
