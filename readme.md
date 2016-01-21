RJC ERP API v1
==============

Este repositorio define la versión uno del API del ERP para el Bizhub de RJC.

Se contemplan los siguientes aspectos:
================

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

Pendientes a cargo del implementador:
================

  * Las columnas cuyo significado no es claro se han nombrado con el patrón x_nombre_de_columna. Es necesario renombrar estas columnas a su equivalente en inglés.
  * Se debe documentar cómo se calculan los precios de un pedido según el cliente para conocer como se debe estructurar un pedido para crearlo y como calcular el precio final que tendrá.

Consideraciones importantes:
================

  * Esta es una definición formal y objectiva del API. Los tipos de dato se definieron según los ejemplos previos de Apiary y por lo tanto cualquier otra columna que sea necesaria debe ser agregada.
  * Todos los campos nuevos deben llamarse en inglés.
  * Si los filtros y clasificaciones de productos varian o no por bodega es indifrente para el API. Se implementan todos los endpoints como recursos anidado dentro de la URL de las bodegas con el fin de adaptar el diseño al patrón de consumo.
  * Hay comentarios en todo el código para hacer más simple la lectura.
  * El API estblace un patrón de acceso pero n o neecsariamente refleja uno a uno la estructura de la base de datos y esa asimetría debe ser manejada por el implementador.
  * El endpoint de pedidos acepta la creación de todo el pedido incluidos sus renglones en su sólo endpoint.
  * Cuando se actualicé un pedido los cambios en sus renglones deben ser manejados por el PATCH de los pedidos.
  * El cliente del API debe asumir que toda solicitud exitosa cumple las reglas de negocios del ERP.

Recomendaciones:
================

  * Utilizar vistas de la db para manejar el mapeo a inglés de los nombres de columna
  * Calcular diariamente en batch las popularidades por artículo

Links:
================

  * Para desargar en ZIP este repositorio: https://github.com/davidpelaez/erp-api-rjc/archive/master.zip
  * Especificación de RAML 1.0: http://docs.raml.org/specs/1.0
