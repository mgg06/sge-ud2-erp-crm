# Comparativa ERP-CRM · UD2

## 1. Datos
- propietario: mgg06
- empresa: 03 — Mensajería urbana "Rapidísimo"
- palabra_del_dia: Compañeros

## 2. Licencias y modelos

Para poder montar el sistema de mensajería de Rapidísimo y conectar los pedidos de los comercios locales sin meternos en ningún problema legal, primero tenemos que entender muy bien qué tipos de licencias de software existen.

El **software libre**, según la FSF (Free Software Foundation), se basa puramente en la libertad del usuario. Te garantiza cuatro cosas importantes: que puedas usar el programa para lo que quieras, que puedas estudiar cómo está hecho por dentro y cambiar su código fuente, que puedas repartir copias y que puedas compartir las mejoras que le hayas hecho con los demás.

Por otro lado, el **código abierto** de la OSI (Open Source Initiative) defiende algo muy similar en la práctica, porque también te deja ver y modificar el código, pero el enfoque es totalmente diferente. Ellos lo ven desde un punto de vista mucho más práctico y técnico. Su lógica es que si el código está abierto para todo el mundo, toda la comunidad de programadores lo va a revisar, van a encontrar los fallos mucho más rápido y el programa va a evolucionar mejor. No es una cuestión de ética o moral, sino de hacer un software que sea más eficiente y seguro.

Frente a estos dos está el **software propietario**. Este es el modelo de caja cerrada de toda la vida. Tú pagas a una empresa por una licencia para poder usar el programa, pero no tienes acceso al código fuente. No puedes ver cómo funciona por dentro, ni hacerle modificaciones profundas, ni distribuirlo. Dependes totalmente del fabricante original para cualquier actualización, mejora o problema que surja.

La gente confunde el software libre con que sea totalmente gratuito, y esto viene de que en inglés la palabra "free" significa las dos cosas. Que un programa sea libre significa que te da las libertades sobre el código que he mencionado antes, pero en ningún sitio dice que no se pueda cobrar por él. Por ejemplo, nadie nos va a cobrar por descargar un sistema libre de internet, pero si contratamos a una consultora, sí que le cobraría a Rapidísimo por el trabajo de instalarlo en el servidor, programar la conexión para que los 25 mensajeros se coordinen o darles soporte técnico todos los meses. Lo que cuesta dinero es el servicio y la mano de obra, no el derecho a usar el código base.

Hoy en día, la mayoría de estos sistemas utilizan un modelo de doble licencia, y aquí es donde hay que tener mucho cuidado al elegir. Suelen ofrecer una edición Community y una edición Enterprise.

La **edición Community** es la versión libre y gratuita, pero suele venir con licencias que tienen una regla llamada copyleft. Para explicarlo de forma sencilla y que se entienda bien, el copyleft es una cláusula que te dice que si tú coges ese programa libre, lo modificas y lo distribuyes a terceros, estás obligado a que tu nueva versión siga siendo libre y tienes que hacer público tu código fuente. 

Dentro de estas licencias copyleft, hay una muy concreta llamada AGPL que está pensada específicamente para el uso por red. Normalmente, si tú modificas un programa libre para usarlo solo de manera interna en tu empresa, no tienes que publicar nada. Pero la AGPL dice que si ofreces ese programa modificado como un servicio a través de internet, eso también cuenta como distribución. Si lo llevo a mi empresa en concreto, si cogemos un sistema con AGPL, le modificamos el código para crear un portal web donde las tiendas locales de Rapidísimo metan sus pedidos, estaríamos obligados legalmente a hacer público todo ese código que hemos programado a medida.

Como las empresas no quieren que su competencia vea y copie los desarrollos internos en los que han invertido dinero, lo que hacen es pasarse a la **edición Enterprise**. Esta es la versión propietaria y de pago del mismo programa. Al pagar esta licencia comercial, la empresa se libra de las restricciones del copyleft y de la trampa de la AGPL. Esto les permite hacer todas las modificaciones a medida que necesiten manteniendo su código totalmente en secreto, y además se aseguran de tener un soporte técnico directo de los creadores del programa.

Aunque las características detalladas van en el apartado siguiente, para dejar analizadas las licencias como pide esta parte de la actividad, estas son las licencias exactas de los cuatro productos que voy a elegir:

* **Odoo Community**: es un ERP libre. Usa la licencia LGPLv3, que tiene un copyleft un poco más suave y sí permite enlazar el programa base con partes de código cerrado sin obligarte a liberar todo tu trabajo.
* **SAP S/4HANA**: es un ERP propietario, así que usa una licencia comercial totalmente cerrada.
* **SuiteCRM**: es un CRM libre y usa la licencia AGPLv3, por lo que nos aplicaría todo el problema de uso por red que acabo de explicar si montamos un servicio web para los clientes.
* **Salesforce**: es un CRM propietario con licencia comercial cerrada que se ofrece como un servicio directamente en la nube.

**Fuentes consultadas:**
* Proyecto GNU (FSF), definición de software libre en gnu.org/philosophy
* Open Source Initiative, The Open Source Definition en opensource.org
* Choose a License, explicación de las implicaciones de las licencias AGPL y LGPL en choosealicense.com 
* Presentación de clase sobre sistemas ERP-CRM libres y propietarios 

## 3. Fichas técnicas
### ERP libre:
### ERP propietario:
### CRM libre:
### CRM propietario:

## 4. Fe de erratas del tema 2

## 5. Matriz de decisión y recomendación