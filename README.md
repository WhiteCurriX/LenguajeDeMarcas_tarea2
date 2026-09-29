# Tarea: Reconocimiento de Elementos en el Desarrollo de un Programa Informático

Trabajo práctico para la asignatura de **Entornos de Desarrollo** (1º DAM).

---

## 1. Documentación inicial

* **Nombre de la app:** AutoCare Hub
* **De qué va:** Es básicamente una página web/app pensada para talleres mecánicos de barrio. La idea es que sirva para llevar la cuenta de los coches que van entrando, avisar al cliente cuando su coche esté arreglado y controlar las piezas que quedan en la nave.
* **Qué problema resuelve:** Quitar los papeles y carpetas por el taller que siempre se traspapelan, y evitar que el cliente tenga que estar llamando a recepción a cada rato para saber si su coche está listo.
* **Quién la va a usar:**
  * *Mecánico:* Abre la ficha de la avería, cambia el estado del coche (por ejemplo de "en proceso" a "listo") y pide piezas al almacén.
  * *Recepcionista:* Apunta las citas que van llegando, cobra las facturas y mira las piezas que van quedando.
  * *Cliente:* Entra desde el móvil para ir viendo cómo va su coche y acepta si hay que cambiarle alguna pieza extra.
* **Dónde se va a usar:**
  * En ordenador para la persona que esté en recepción.
  * En tablet/móvil tanto para el mecánico que está manchándose en el taller como para el cliente desde su casa.
* **Modelo de desarrollo:** Vamos a usar un **modelo ágil (scrum)**. En clase hemos visto que viene genial para este tipo de proyectos porque en un taller van saliendo cosas sobre la marcha. En lugar de hacer todo el programa entero de golpe, hacemos entregas cada dos semanas (sprints) y así el mecánico nos va diciendo si le gusta cómo queda la pantalla o si hay que cambiar los botones.

---

## 2. Por qué elegimos esta aplicación

Hemos tirado por la idea de un taller mecánico relacionándolo con dos puntos clave del temario:

1. **Modelos de desarrollo (ágil vs cascada):** Si usáramos un modelo en cascada y diseñáramos todo el programa de principio a fin sin probarlo, corremos el riesgo de que al mecánico le resulte incómodo usar la tablet mientras trabaja. Con el modelo ágil vamos sacando versiones pequeñas y corregimos sobre la marcha.
2. **Clasificación de requisitos:** Nos venía muy bien este ejemplo para diferenciar los requisitos funcionales (las opciones del programa, como mandar un SMS) de los no funcionales (la velocidad, que la base de datos sea segura, etc.).

---

## 3. Lista de características principales

Aquí van 10 funciones que tendría la app mezclando funcionales y no funcionales:

1. Registrar un coche cuando llega al taller con la matrícula, fotos de si tiene algún bollo y lo que le pasa. *(Funcional)*
2. Enviar un SMS o un correo automático al cliente cuando su coche cambie de estado. *(Funcional)*
3. Sacar el presupuesto en pdf para mandarlo por correo o imprimirlo. *(Funcional)*
4. Una pantalla para que el cliente confirme desde el móvil si acepta un arreglo que ha salido a última hora. *(Funcional)*
5. Avisar cuando queden pocas unidades de un recambio en el almacén. *(Funcional)*
6. Guardar las contraseñas **e** información de los clientes de forma segura para que no las roben. *(No funcional)*
7. Que al buscar un coche la lista cargue en menos de 2 segundos. *(No funcional)*
8. Botones grandes en la pantalla de la tablet para **habrir** el menú rápido aunque lleves guantes. *(No funcional)*
9. Que la app no se caiga ni se quede pillada durante la jornada de trabajo. *(No funcional)*
10. Que funcione bien desde cualquier navegador (Chrome, Firefox, Edge...). *(No funcional)*

---

## 4. Análisis de Requisitos

### Requisitos funcionales (RF)

* **RF-01: Ficha del coche**
  * *Qué hace:* Permite abrir una ficha a un coche con su matrícula, asignarle un mecánico y apuntar los filtros o piezas que se hayan usado.
  * *Por qué es importante:* Es la función principal. Si esto no tira, el programa no sirve para nada porque es el objetivo básico del proyecto.
* **RF-02: Seguimiento para el cliente**
  * *Qué hace:* El cliente entra desde un enlace que le llega al móvil y ve una barra de progreso de su reparación.
  * *Por qué es importante:* Le ahorra tiempo al recepcionista para que no tenga que estar cogiendo el teléfono a cada rato para dar la misma información.
* **RF-03: Descontar piezas del almacén**
  * *Qué hace:* Cada vez que se usa una pieza en un coche, el sistema quita 1 unidad del inventario solo.
  * *Por qué es importante:* Para llevar la lógica del negocio bien y evitar que el taller se quede sin piezas a mitad de un trabajo sin darse cuenta.
* **RF-04: Confirmación del presupuesto**
  * *Qué hace:* El cliente le da a un botón en la pantalla del móvil para dar el visto bueno al precio final.
  * *Por qué es importante:* Para que quede constancia de que el cliente dio el ok antes de ponerse a cambiar piezas raras.
* **RF-05: Informe del mes**
  * *Qué hace:* Un botón para sacar un resumen del dinero que ha entrado y cuántos coches se han arreglado al mes.
  * *Por qué es importante:* Ayuda al dueño a ver **como** va la cosa sin tener que echar cuentas con la calculadora.

### Requisitos no funcionales (RNF)

* **RNF-01: Usabilidad**
  * *Qué hace:* La interfaz de la tablet tiene que verse clara y los botones ser amplios.
  * *Por qué es importante:* El mecánico no es un experto informático, así que si le ponemos una pantalla complicada directamente no la va a usar.
* **RNF-02: Seguridad**
  * *Qué hace:* Los datos personales (DNI, teléfono, cuenta) van encriptados y con usuario/contraseña para entrar.
  * *Por qué es importante:* Hay que cumplir las leyes de protección de datos obligatoriamente para evitar multas.
* **RNF-03: Velocidad**
  * *Qué hace:* Buscar una matrícula o abrir la base de datos no puede tardar más de 2 segundos.
  * *Por qué es importante:* Si la app va lenta se forman colas en la entrada del taller y la gente se impacienta.
* **RNF-04: Disponibilidad**
  * *Qué hace:* El servidor tiene que estar funcionando el 99% del tiempo y hacer copias de seguridad a diario.
  * *Por qué es importante:* Si el programa se cae en medio de la mañana, el taller no puede cobrar ni trabajar.
* **RNF-05: Portabilidad**
  * *Qué hace:* Entras directamente desde la web sin necesidad de **instalasion** de programas raros.
  * *Por qué es importante:* Facilita poner la app en marcha sin tener que gastar dinero en ordenadores nuevos.

---

## 5. Trabajo en grupo y reflexión

### Reparto de tareas
* **Integrante 1:** Se encargó de la parte inicial, la explicación del modelo ágil y redactó los Requisitos Funcionales (del 1 al 5).
* **Integrante 2:** Pensó la idea del taller, los tipos de usuario y escribió los Requisitos No Funcionales (del 1 al 5).
* **Integrante 3:** Organizó las 10 características, dio formato al texto y repasó la entrega final.

### Conclusión sobre lo visto en clase
Lo que más quebraderos de cabeza nos ha dado ha sido la **fase de análisis**, sobre todo al principio para no liar lo que es un requisito funcional de uno no funcional. 

Repasando los modelos de desarrollo, si hubiéramos planteado esto con el **modelo en cascada** tendríamos bastante miedo de meter la pata al principio, porque si te equivocas en el análisis no te enteras hasta el final del proyecto y hay que tirar semanas de trabajo. Con el **modelo ágil** vas haciendo entregas cortas, pruebas lo que tienes con el usuario e vas corrigiendo los fallos sobre la marcha sin tanto agobio.