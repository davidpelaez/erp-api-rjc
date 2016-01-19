RJC ERP API v1
==============

Este repositorio define la versión uno del API del ERP para el Bizhub de RJC.

Se contemplan los siguientes aspectos:

  * Soporte para múltiples países
  * Soporte para bodegas por país
  * Endpoints de información de semi-constantes del ERP como tipo de cliente, zonas, segmentos, etc.
  * Soporte para apuntar a una referencia específica de una línea con información expandida.
  * Soporte para paginado, ordenamiento y filrado de colecciones (e.j. productos, sedes).
  * Especificación dinámica de filtrado de colecciones usando selectores (filtros discretos) o rangos.
  * Manejo de autenticación basado en un token pasado en los headers de todas las solicitudes.
  * Estructura unificada para mensajes de error.
  * Mapeo de columnas de las DB del ERP a nombres en inglés para normalización de la interfaz con buenas prácticas REST.
  * Descripción de código de respuesta en cada endpoint.
  * Especificación de estructuras de datos formales utilizados en los endpoints.

Pendientes:

  * Las columnas cuyo significado no es claro se han nombrado con el patrón x_nombre_de_columna. Es necesario renombrar estas columnas a su equivalente en inglés.

Consideraciones importantes:

  * Esta es una definición formal y objectiva del API. Los tipos de dato se definieron según los ejemplos previos de Apiary y por lo tanto cualquier otra columna que sea necesaria debe ser agregada.
  * Todos los campos nuevos deben llamarse en inglés.
  * Si los filtros y clasificaciones de productos varian o no por bodega es indifrente para el API. Se implementan todos los endpoints como recursos anidado dentro de la URL de las bodegas con el fin de adaptar el diseño al patrón de consumo.
  * Hay comentarios en todo el código para hacer más simple la lectura.
  * El API estblace un patrón de acceso pero n o neecsariamente refleja uno a uno la estructura de la base de datos y esa asimetría debe ser manejada por el implementador.
