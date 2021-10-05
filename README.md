Se ha polemizado mucho el último tiempo (por el bloqueo del Banco Estado y Falabella a algunas Fintech) sobre el web scraping. Se dice que esta práctica está en un área gris. Pero hacer web scraping en sí no es ilegal, aunque la manera de hacerlo puede ser molesta en algunos casos.

Esta guía pretende dar algunos lineamientos a seguir al hacer web scraping y seas cuidadoso de la manera y el tipo de datos que estás extrayendo.

# ¿Por qué hacer una guía?
Nuestros datos son nuestros. Nuestro teléfono, correo, nombre. Como también nuestros datos bancarios, datos en el SII, TGR, datos que tienen las tiendas comerciales y reparticiones públicas. Muchos de estos datos no tienen estructura, están en diversos formatos y separados en diferentes fuentes.

Algunos bancos están bloqueando web scrapers de algunas Fintechs, es decir, a que podamos obtener nuestros propios datos a través de esta técnica. 

Lo ideal siempre será hacer uso de API's cuanto estén disponibles. Cuando no, hacer web scraping es la solución. Hay varias formas de hacerlo y, si bien en este documento no queremos tocar las tecnologías a usar, sí queremos acordar los criterios que nos parecen razonables.

# Alcance
El alcance de lo expresado en este documento va que desde que se levanta el navegador hasta que se baja el/los datos. No su procesamiento o lo que se haga posteriormente con esos datos.

# Disclaimer: 
Estos criterios no constituyen una recomiendación legal ni un pase liberado a hacer web scraping sobre cualquier sitio si se cumplen todas las recomendaciones. No impide a bancos o SII a hacer sus propias definiciones. Tampoco las Fintech se verán automáticamente bloqueadas al no cumplirlas. Las recomendaciones están basadas en la experiencia acumulada de las personas que escriben estas líneas. 

No existe un ente que valide la implementación de estas mejores prácticas.

# Definiciones 
## Web Scraping
Web scraping es una técnica computacional para extraer información de sitios web. Usualmente, estos programas simulan la navegación de un humano en la WWW para obtener y tranformar datos sin estructura (como el formato HTML) en datos estructurados que pueden ser almacenados y analizados en una base de datos central, en una hoja de cálculo o en alguna otra fuente de almacenamiento. Alguno de los usos del web scraping son la comparación de precios en tiendas, la monitorización de datos relacionados con el clima de cierta región, la detección de cambios en sitios webs y la integración de datos en sitios webs. 

Las Fintechs las usamos para:
* Validación de identidad
* Extracción de información desde cuentas bancarias (saldos, cartolas)
* Automatizar una transferencia bancaria
* Hacer análisis de riesgo

## Usuario
Es el poseedor de las claves de usuario, que se asume como el dueño de los datos.

# Prácticas
En resumen:
1. No seas una carga
2. No violar los derechos sobre los datos
3. Respetar los Términos y Condiciones de cada sitio
4. No infringir GDPR
5. Seguridad

## No seas una carga
La regla más importante para hacer web scraping es no dañar al sitio que estás accediendo. Esto significa que ni el volumen ni la frecuecia de las consultas que estás haciendo deben ser una sobrecarga o una interferencia a la operación natural del sitio web.

Esto se puede hacer de varias formas: 
* Limitar el número de requests concurrentes al mismo sitio desde la misma IP
* Respetar el delay para web scrapers que se describe en el robots.txt (crawl-delay)
* En lo posible, programar los web scrapers para horarios fuera de peak
* Si hay login, hacer logout al terminar.
* Proveer a los administradores de los sitios que estás haciendo web scraping una forma fácil de contactarte. Esto se puede hacer poniendo un formulario de contacto en tu sitio de "Reporte de web scraping abusivo". Si alguna vez llegas a recibir este reporte, debes dejar de hacerlo o limitar la intensidad en orden de rectificar el abuso reportado.

## No violar los derechos sobre los datos
Los datos son del usuario y sólo el o ella pueden definir qué hacer con ellos. No se pueden compartir, vender o publicar datos que son de los usuarios.

### Consentimiento
Debe haber un consentimiento explícito de parte de los usuarios que defina:
* Qué información se va a obtener
* El uso y tratamiento de la información
* Que será obtenida mediante web scraping

Esto significa que tu debes estar en contacto directo con la persona y que ésta debe estar de acuerdo con los términos en los que tu obtienes sus datos.

### Interés Legítimo
Debe haber un mandato específico de obtención de datos por parte del usuario y éste debe ser de explícito conocimiento para el usuario. No se debe hacer web scraping si este mandato ha sido revocado por el usuario. 

### Término o fin del servicio
Se debe tener un mecanismo para que el usuario pueda retractarse y revocar el acceso a hacer web scraping en su nombre.

## Respetar los Términos y Condiciones de cada sitio
Cuando haces login, estás explicitamente accediendo a los Términos y Condiciones de cada sitio. Esto es estar eplícitamente de acuerdo con sus reglas sobre web scraping si es que hubiera. Éstas reglas pueden ser que no te permiten hacer web scraping de la data dentro de ese sitio. 

Debes leer con cuidado los Términos y Condiciones y su política de robots.txt y honrar esos contratos.

## No infringir GDPR
El Reglamento General de Protección de Datos (RGPD o GDPR en inglés) norma el cómo se procesan datos de ciudadanos Europeos. Comenzó a aplicar en mayo de 2018 y es una normativa a nivel de la Unión Europea que su no cumplimiento puede tener multas hasta los 20 millones de euros.

# Seguridad
El alcance de este documento es sólo el web scraping, desde que se levanta el browser hasta que se obtiene el dato. Por lo que las medidas de seguridad están supeditadas a este alcance. 
* Todas las conexiones deben estar cifradas.
* Si se guardan credenciales, éstas deben guardarse cifradas. 
* Todas las personas de la empresa que tengana acceso a los datos de usuarios deben tener contrato con la Fintech.

# Fuentes
* https://es.wikipedia.org/wiki/Web_scraping
* https://www.zyte.com/learn/web-scraping-best-practices
* https://es.wikipedia.org/wiki/Reglamento_General_de_Protecci%C3%B3n_de_Datos
