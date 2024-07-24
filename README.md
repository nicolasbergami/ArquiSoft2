# ArquiSoft2
Desarrollaremos un sistema de publicación de clasificados inmobiliarios. Este sistema permitirá que las empresas inmobiliarias carguen sus bases de datos mediante la publicación de archivos JSON con información sobre los inmuebles. Los usuarios del sitio podrán buscar estos clasificados desde la página principal, utilizando una oración que devolverá resultados priorizados, permitiéndoles ver los detalles de cada publicación.

Para ello, se desarrollarán tres microservicios:

Búsqueda
Publicaciones
Frontend

Microservicios Detallados

Servicio de Búsqueda

Utilizará un motor de búsqueda que permita la indexación y búsqueda de ítems por características (título, descripción, atributos, ciudad, estado, etc.).
Se alimentará mediante notificaciones del servicio de ítems, permitiendo así la actualización y consulta de información de dicho servicio.

Servicio de Publicaciones

Mantendrá un caché centralizado con los datos de los ítems.
Si la información de un usuario no está en caché, se solicitará al servicio correspondiente y se almacenará para que las próximas solicitudes se sirvan del caché.
Los datos de los ítems se almacenarán de forma persistente en una base de datos no relacional.
Las imágenes de los ítems se servirán localmente, por lo que es necesario prever una descarga concurrente y asíncrona de las imágenes proporcionadas en la carga inicial del catálogo.
La carga de la información de los ítems la realizará el administrador del sistema mediante la publicación de un archivo JSON con un arreglo de ítems. Una vez recibido el archivo, se finalizará la solicitud y el procesamiento se realizará de forma asíncrona.

Servicio de Frontend

Proveerá una interfaz de usuario que incluya:
Un campo de búsqueda en la página de inicio.
Un listado de publicaciones.
Una vista detallada de cada publicación.

Requerimientos No Funcionales

Proveer uno o varios balanceadores de carga para soportar múltiples instancias de los servicios.
Utilizar GitHub (o similar) para el versionado del código fuente.
Escribir la documentación en el archivo README del repositorio.
