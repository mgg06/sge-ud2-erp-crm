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
* Proyecto GNU (FSF), definición de software libre en gnu.org/philosophy - 28/09/2026
* Open Source Initiative, The Open Source Definition en opensource.org - 28/09/2026
* Choose a License, explicación de las implicaciones de las licencias AGPL y LGPL en choosealicense.com - 28/09/2026
* Presentación de clase sobre sistemas ERP-CRM libres y propietarios - 28/09/2026

## 3. Fichas técnicas

Para esta sección me he metido en la documentación oficial de los cuatro sistemas. La idea es saber los detalles de cada programa para saberlos exactamente al montarlo para gestionar a los repartidores y pedidos de Rapidísimo. 

### ERP libre: Odoo Community

*   **Licencia exacta:** GNU LGPLv3. Es una licencia copyleft más relajada que nos deja enlazar módulos propios sin obligarnos a hacer público nuestro código, algo que viene muy bien para integraciones a medida.
*Fuente: [Acuerdos Legales de Odoo](https://www.odoo.com/es_ES/page/legal) - 28/09/2026*

*   **Versión vigente:** Odoo 19.
*Fuente: [Descargas y versiones actuales](https://www.odoo.com/es_ES/page/download) - 28/09/2026*

*   **Lenguaje del servidor:** Todo el backend y la lógica de negocio del servidor están programados en Python.
*Fuente: [Documentación técnica para desarrolladores](https://www.odoo.com/documentation/master/es/developer.html) - 28/09/2026*

*   **SGBD compatibles:** PostgreSQL. Son súper estrictos con esto, es el único motor de base de datos que soportan de manera oficial, olvidándonos de MySQL u Oracle.
*Fuente: [Guía de instalación de base de datos](https://www.odoo.com/documentation/master/es/administration/install.html) - 28/09/2026*

*   **Modalidad:** Instalación local (On-Premise). Implica que nosotros mismos descargamos el código, lo alojamos en un servidor propio y nos encargamos de todo el mantenimiento.
*Fuente: [Ediciones y alojamiento Odoo](https://www.odoo.com/es_ES/page/editions) - 28/09/2026*

*   **Módulos principales:** Ventas, CRM, Facturación, Inventario y Punto de Venta (POS). Para Rapidísimo, tirar del módulo de Inventario y Ventas sería clave para organizar las rutas.
*Fuente: [Catálogo oficial de Apps](https://www.odoo.com/es_ES/app/apps) - 28/09/2026*

*   **Requisitos:** Piden una máquina con Linux (recomiendan Ubuntu), tener instalado Python 3.10 o superior, PostgreSQL como motor de base de datos y librerías adicionales como wkhtmltopdf para generar los informes.
*Fuente: [Requisitos de instalación en sistema](https://www.odoo.com/documentation/master/es/administration/install.html) - 28/09/2026*


### ERP propietario: SAP S/4HANA

*   **Licencia exacta:** Comercial propietaria. Es un modelo totalmente cerrado donde se paga por el uso y las licencias de usuario.
*Fuente: [Centro de Confianza SAP - Acuerdos](https://www.sap.com/spain/about/trust-center/agreements.html) - 28/09/2026*

*   **Versión vigente:** SAP S/4HANA 2025 (suelen nombrar las versiones potentes con el año en curso).
*Fuente: [Información de producto S/4HANA](https://www.sap.com/spain/products/erp/s4hana.html) - 28/09/2026*

*   **Lenguaje del servidor:** ABAP. Es un lenguaje de programación altísimamente específico que fue creado por la propia SAP para desarrollar dentro de sus entornos.
*Fuente: [Entorno de desarrollo SAP ABAP](https://help.sap.com/docs/abap) - 28/09/2026*

*   **SGBD compatibles:** Exclusivamente SAP HANA. Es su propia base de datos "in-memory", diseñada para procesar toda la información en la memoria RAM en vez de en el disco duro para que las consultas vuelen.
*Fuente: [Características de la base de datos SAP HANA](https://www.sap.com/spain/products/technology-platform/hana/features.html) - 28/09/2026*

*   **Modalidad:** Híbrida. Dan la libertad de instalarlo en tus propios servidores físicos (On-Premise) o usar su infraestructura en la nube (Cloud).
*Fuente: [Opciones de despliegue de S/4HANA](https://www.sap.com/spain/products/erp/s4hana/features.html) - 28/09/2026*

*   **Módulos principales:** Finanzas (FI), Controlling (CO), Ventas y Distribución (SD) y Gestión de Materiales (MM).
*Fuente: [Capacidades del ERP SAP](https://www.sap.com/spain/products/erp/s4hana/features.html) - 28/09/2026*

*   **Requisitos:** Es bastante duro de mover. Exige hardware certificado oficialmente por SAP, usar su motor HANA y un sistema operativo Linux de nivel empresarial, limitándose normalmente a SUSE o Red Hat.
*Fuente: [Portal de ayuda SAP On-Premise](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE?locale=es-ES) - 28/09/2026*


### CRM libre: SuiteCRM

*   **Licencia exacta:** AGPLv3. Justo lo que comentaba en el bloque anterior, mucho cuidado con usarlo en red para integrar pedidos web sin querer liberar nuestras modificaciones.
*Fuente: [Licencia del proyecto SuiteCRM](https://suitecrm.com/about/) - 28/09/2026*

*   **Versión vigente:** SuiteCRM 8.7.
*Fuente: [Notas de la última versión (Releases)](https://docs.suitecrm.com/8.x/admin/releases/) - 28/09/2026*

*   **Lenguaje del servidor:** PHP. Todo el núcleo está programado con este lenguaje, apoyándose fuertemente en el framework Symfony para estructurar el backend.
*Fuente: [Matriz de compatibilidad y arquitectura](https://docs.suitecrm.com/8.x/admin/installation-guide/compatibility-matrix/) - 28/09/2026*

*   **SGBD compatibles:** MySQL y MariaDB.
*Fuente: [Bases de datos soportadas](https://docs.suitecrm.com/8.x/admin/installation-guide/compatibility-matrix/) - 28/09/2026*

*   **Modalidad:** Instalación local (On-Premise) para desplegarlo íntegramente en nuestra propia infraestructura.
*Fuente: [Descargas oficiales SuiteCRM](https://suitecrm.com/download/) - 28/09/2026*

*   **Módulos principales:** Cuentas (para fichar a los comercios locales), Contactos, Oportunidades de venta y el módulo de Casos, que serviría para llevar el control de incidencias o quejas con los repartos.
*Fuente: [Características y módulos de SuiteCRM](https://suitecrm.com/features/) - 28/09/2026*

*   **Requisitos:** Hay que montar una arquitectura web, un servidor HTTP como Apache o Nginx, tener instalado PHP 8.2 o superior, la base de datos MySQL/MariaDB y algunas extensiones de PHP activas como cURL o GD.
*Fuente: [Requisitos previos de instalación](https://docs.suitecrm.com/8.x/admin/installation-guide/downloading-installing/) - 28/09/2026*


### CRM propietario: Salesforce

*   **Licencia exacta:** Comercial propietaria cerrada. Funcionan con un modelo puramente SaaS (Software as a Service) donde se paga una cuota mensual por cada usuario que entre al sistema.
*Fuente: [Documentación legal Salesforce](https://www.salesforce.com/es/company/legal/) - 28/09/2026*

*   **Versión vigente:** Winter '27. No se complican con números normales, lanzan actualizaciones estacionales de forma global para todos sus clientes a la vez.
*Fuente: [Lanzamientos y versiones estacionales](https://www.salesforce.com/es/releases/) - 28/09/2026*

*   **Lenguaje del servidor:** Apex. Es un lenguaje propio orientado a objetos que crearon ellos, y la verdad es que la sintaxis es igual a Java.
*Fuente: [Guía para desarrolladores sobre Apex](https://developer.salesforce.com/docs/) - 28/09/2026*

*   **SGBD compatibles:** Trabajan con una arquitectura "multitenant" soportada por bases de datos Oracle, pero el cliente final ni lo ve ni lo gestiona, todo es transparente.
*Fuente: [Arquitectura de plataforma Salesforce](https://architect.salesforce.com/fundamentals/architecture-landscape) - 28/09/2026*

*   **Modalidad:** 100% Nube (Cloud). Todo se aloja y procesa en sus servidores, no existe un instalador para montarlo en tus máquinas.
*Fuente: [Definición y entorno Salesforce](https://www.salesforce.com/es/learning-centre/crm/what-is-salesforce/) - 28/09/2026*

*   **Módulos principales:** Sales Cloud (fuerza de ventas), Service Cloud (atención al cliente y soporte) y Marketing Cloud (gestión de campañas).
*Fuente: [Catálogo de productos Salesforce](https://www.salesforce.com/es/products/) - 28/09/2026*

*   **Requisitos:** Al ser una plataforma totalmente en la nube, el sistema informático de la empresa da un poco igual. Solo se requiere una conexión a internet estable y entrar desde un navegador moderno (Chrome, Edge, Safari o Firefox).
*Fuente: [Navegadores compatibles](https://help.salesforce.com/s/articleView?id=sf.getstart_browsers_sfx.htm&type=5&language=es) - 28/09/2026*


## 4. Fe de erratas del tema 2

La actividad nos pide localizar dos, pero yo he encontrado 3: 

**Bases de datos compatibles con SuiteCRM**
En la diapositiva de soluciones CRM, el temario dice que SuiteCRM es compatible con MySQL, MariaDB y SQL Server. El problema es que esto ya no es verdad. En las versiones antiguas (la rama 7.x) sí que lo soportaba, pero desde el salto a la versión 8 cambiaron toda la arquitectura y quitaron el soporte oficial para la base de datos de Microsoft. Si miramos su matriz de compatibilidad técnica actual, dejan clarísimo que solo admiten MySQL y MariaDB. Instalarlo sobre SQL Server hoy en día para Rapidísimo directamente nos daría error.
* Fuente consultada (28/09/2026): Matriz de compatibilidad en la documentación oficial de SuiteCRM (https://docs.suitecrm.com/8.x/admin/installation-guide/compatibility-matrix/).

**El desarrollador real de SuiteCRM**
En esa misma diapositiva, dice que SuiteCRM está desarrollado por la comunidad SugarCRM. Esto es un error histórico, ya que SuiteCRM nació justo por lo contrario, la empresa SugarCRM decidió cerrar su código para hacerlo de pago. Cuando pasó esto, la empresa SalesAgility cogió la última versión libre que quedaba y montó una bifurcación para crear SuiteCRM a partir de ella y mantenerla libre. Así que son competencia directa y el desarrollo lo lleva SalesAgility junto a su propia comunidad, no la de SugarCRM.
* Fuente consultada (28/09/2026): Historia del proyecto en la página oficial (https://suitecrm.com/about/).

**La popularidad de Fat Free CRM en GitHub**
También he visto que se dice que Fat Free CRM es como el CRM más valorado en GitHub por su comunidad activa. Ese dato se ha quedado bastante anticuado, Si nos metemos hoy a GitHub, Fat Free CRM tiene unas 3.000 estrellas. No está mal para un proyecto pequeño, pero si lo comparamos con otros gigantes del software libre, Odoo pasa de las 35.000 estrellas y ERPNext tiene más de 16.000. Actualmente está lejísimos de ser el sistema más valorado por los desarrolladores.
* Fuente consultada (28/09/2026): Repositorios oficiales de GitHub de Odoo (https://github.com/odoo/odoo) y Fat Free CRM (https://github.com/fatfreecrm/fat_free_crm).


## 5. Matriz de decisión y recomendación

Para tomar la mejor decisión, he hecho una matriz comparando tres opciones que son muy diferentes: un ERP libre (Odoo Community), un CRM propietario que es líder en el mercado (Salesforce) y un CRM libre (SuiteCRM). 

Los criterios y los pesos los he ajustado a la realidad que tendría Rapidísimo, ya que son una empresa local con un presupuesto limitado, cuentan con 25 mensajeros que necesitan trabajar desde el móvil en la calle, y su principal canal para recibir pedidos de los comercios es WhatsApp.

### Justificación de las puntuaciones (1 al 5)

**1. Coste de licencias e infraestructura (Peso: 20%)**
*   **Odoo Community (5):** Al ser de código abierto, evitamos el pago por licencia de usuario. Solo tendríamos que asumir el coste del servidor mensual, y eso es bastante asumible para la empresa.
*   **Salesforce (1):** Puntuación mínima. Asumir el pago mensual de licencias para 25 mensajeros y el personal de oficina reduciría drásticamente los márgenes de beneficio de una empresa local.
*   **SuiteCRM (5):** Al igual que Odoo, el coste de la licencia es cero y los requisitos para el servidor web son bastante económicos.

**2. Usabilidad móvil para los mensajeros (Peso: 25%)**
*   **Odoo Community (4):** Su diseño web es "responsive" y se adapta muy bien a las pantallas de los móviles. Los repartidores podrían ir marcando sus entregas con fácilmente.
*   **Salesforce (5):** Tienen con una aplicación móvil nativa que está muy pulida y es rápida, diseñada específicamente para trabajar fuera de la oficina con mucha fluidez.
*   **SuiteCRM (2):** En este aspecto se queda atrás. La interfaz desde el móvil es más antigua y menos intuitiva, lo que resultaría poco ágil para los mensajeros durante su ruta.

**3. Integración de pedidos vía WhatsApp (Peso: 20%)**
*   **Odoo Community (3):** Por defecto no incluye una integración nativa. Nos tocaría desarrollar un módulo a medida o utilizar herramientas de terceros para conectar la API de WhatsApp Business.
*   **Salesforce (5):** Destaca por su omnicanalidad. Tiene integración directa con WhatsApp, lo que permite que los mensajes entren directamente al sistema para ser gestionados.
*   **SuiteCRM (2):** Requiere bastante trabajo técnico. Al ser un sistema más tradicional, conectar canales modernos exige programar integraciones complejas que no siempre son estables.

**4. Logística y control de paquetes (Peso: 15%)**
*   **Odoo Community (5):** Al ser un ERP completo, su módulo de Inventario es muy potente. Nos permite tratar cada paquete como si fuera stock en movimiento y gestionar las rutas de reparto.
*   **Salesforce (2):** Es una herramienta enfocada a ventas. Podríamos adaptar el sistema creando objetos personalizados para simular paquetes, pero no está diseñada para la logística.
*   **SuiteCRM (1):** Resultaría muy complejo y poco eficiente intentar gestionar rutas y paquetes en un sistema pensado principalmente para el seguimiento comercial.

**5. Independencia del proveedor "Vendor Lock-in" (Peso: 10%)**
*   **Odoo Community (4):** Al tener el código fuente y la base de datos alojados en nuestro propio servidor, mantenemos una gran independencia, aunque seguimos sujetos a la arquitectura de Odoo.
*   **Salesforce (1):** Dependencia total. Si cambian las tarifas o se interrumpe el servicio, la empresa queda paralizada sin acceso a su propia base de datos de forma directa.
*   **SuiteCRM (5):** Independencia absoluta. Al ser software libre bajo licencia AGPLv3, la empresa es dueña total de sus datos y de las modificaciones que haga en el código.

**6. Soporte técnico y comunidad (Peso: 10%)**
*   **Odoo Community (4):** No cuenta con soporte oficial directo en esta versión, pero tiene una comunidad de desarrolladores enorme, lo que facilita encontrar soluciones en foros y documentación.
*   **Salesforce (5):** Al pagar las licencias, se incluye un soporte técnico corporativo directo con acuerdos de nivel de servicio bastante estrictos.
*   **SuiteCRM (3):** Tiene una comunidad activa, pero al ser más reducida, los tiempos para encontrar soluciones a problemas técnicos pueden ser mayores.

### Resultados totales ponderados

Aplicando los porcentajes a cada puntuación, estos son los resultados sobre un máximo de 5 puntos:

*   **Odoo Community:** (5×0.20) + (4×0.25) + (3×0.20) + (5×0.15) + (4×0.10) + (4×0.10) = **4.15 puntos**
*   **Salesforce:** (1×0.20) + (5×0.25) + (5×0.20) + (2×0.15) + (1×0.10) + (5×0.10) = **3.35 puntos**
*   **SuiteCRM:** (5×0.20) + (2×0.25) + (2×0.20) + (1×0.15) + (5×0.10) + (3×0.10) = **2.85 puntos**

### Recomendación y plan de riesgos

Tras analizar los resultados de la matriz, la recomendación final que daría para Rapidísimo es implantar Odoo Community. Es la opción que mejor resuelve la parte logística gracias a su módulo de inventario, permitiendo al mismo tiempo mantener unos costes asumibles al no requerir el pago de 25 licencias mensuales. Además, ofrece una interfaz móvil suficientemente buena para los mensajeros.

Pero, antes de implantarlo, es necesario tener en cuenta los siguientes riesgos:

*   **Coste total de propiedad (TCO):** Aunque el software es libre, debemos hacer un presupuesto de el mantenimiento del servidor y, de manera crucial, el coste del desarrollo a medida para integrar la API de WhatsApp con Odoo.
*   **Dependencia del proveedor (Servicios):** Al necesitar desarrollos personalizados, corremos el riesgo de depender del programador o de la consultora externa que realice esa integración. Si la relación termina, el mantenimiento del código recaerá en nosotros.
*   **Soporte técnico:** Al no disponer de la versión Enterprise, no contamos con soporte oficial ante caídas del sistema. Si ocurre un fallo grave durante el horario de reparto, dependeremos exclusivamente de nuestro propio equipo técnico.
*   **Migración futura:** La base de datos de Odoo (PostgreSQL) tiene una estructura muy específica. Si en el futuro la empresa crece a nivel nacional y necesita migrar a otro sistema más grande, la extracción y transformación de todo el histórico de envíos será un proceso técnico complejo.