# Respuestas del video

Completa aqui las respuestas a las ocho preguntas de la guía despues de ver los tramos indicados.

1. ¿Que comando inicia un proyecto de Node.js y que archivo crea? ¿Para que sirve ese archivo?

El comando npm init permite iniciar un proyecto de Node.js y crear el archivo package.json. Este archivo contiene la informacion del proyecto, las dependencias y los comandos necesarios para ejecutarlo.

2. ¿Que hace nodemon y por que conviene durante el desarrollo pero no en produccion?

Nodemon reinicia automaticamente el servidor cuando detecta cambios en el codigo. Es util durante el desarrollo porque evita tener que reiniciar manualmente la aplicación. En produccion se recomienda utilizar Node.js con un administrador de procesos adecuado.

3. Describan las carpetas de la aplicación. ¿Cuales equivalen a routes, controllers y models?

La carpeta routes contiene las rutas que reciben las peticiones HTTP. La carpeta controllers se encarga de procesar las solicitudes y preparar las respuestas. La carpeta models contiene las funciones relacionadas con la base de datos. Esta separación permite mantener el proyecto organizado y facilita su mantenimiento.

4. En una ruta como /productos/, ¿como obtiene el codigo el valor de id? ¿Que ventaja tiene separar la ruta del controlador?

El valor del identificador se obtiene mediante req.params.id. Separar las rutas de los controladores permite organizar mejor el codigo, reutilizar funciones y facilitar la correccion de errores.

5. ¿Donde se escriben los datos de conexion? ¿Que diferencia existe con el archivo .env?

Los datos de conexion incluyen el servidor, usuario, contraseña y nombre de la base de datos. En nuestro proyecto se almacenan en el archivo .env, que permite mantener las credenciales separadas del código principal. Es más seguro porque podemos excluirlo de GitHub mediante .gitignore.

6. ¿Que tienen en común las tablas de la base de datos y qué claves foraneas utilizan?

Las tablas permiten organizar la información y relacionar diferentes registros mediante claves primarias y foráneas. En nuestra tienda, productos se relaciona con categorias mediante categoria_id, mientras que pedido_items utiliza pedido_id y producto_id para relacionar los pedidos con sus productos.

7. ¿Que operaciones utiliza CRUD y cuáles son sus métodos HTTP y códigos de respuesta?

CRUD representa las operaciones de crear, leer, actualizar y eliminar información

En nuestro proyecto no se utiliza DELETE para los pedidos, porque estos se cancelan cambiando su estado. También se utilizan los códigos 400 para datos incorrectos, 404 para recursos inexistentes y 422 para errores relacionados con las reglas del negocio.

8. ¿Por que es importante utilizar parametros en las consultas SQL para evitar la inyeccion SQL?

Las consultas parametrizadas utilizan símbolos como ? para enviar valores de manera segura a la base de datos. Esto evita que los datos introducidos por un usuario sean interpretados como instrucciones SQL. De esta manera se reduce el riesgo de inyeccion SQL y se protege la informacion almacenada.

9. ¿Que pasaría si utilizáramos concatenación de texto en lugar de parametros SQL?

Un atacante podria introducir instrucciones SQL maliciosas en la dirección de la API para intentar modificar o consultar informacion sin autorización. Utilizar parametros como ? evita que los datos del usuario se interpreten como instrucciones SQL y ayuda a prevenir la inyección SQL.

10. ¿Por que cambiar el estado de un pedido utiliza PATCH y no PUT?

Se utiliza PATCH porque solamente necesitamos modificar una parte del pedido, en este caso su estado. PUT se utiliza generalmente para reemplazar la representacion completa de un recurso.

11. Si el cliente solicita un producto_id que no existe, ¿responderian 404 o 422?

Utilizariamos el código 422 porque el pedido contiene un producto inexistente y no puede procesarse correctamente. Aunque 404 se utiliza para recursos no encontrados, en este caso estamos validando los datos enviados para crear un pedido.

12. ¿Por que pedido_items guarda precio_unitario si el precio ya está en productos?

Se guarda el precio unitario para conservar el valor que tenia el producto cuando se realizo la compra. Si posteriormente aumenta o disminuye su precio, los pedidos anteriores mantendran el importe original, permitiendo consultar correctamente el historial de ventas.

## Autoevaluacion

**1. ¿Que paso les tomo mas tiempo y como lo resolvieron?**

El paso que mas tiempo me tomo fue la configuracion de la base de datos y su conexion con la API. Tuve problemas con los permisos del usuario de MySQL y con la ubicacion de las tablas. Lo resolvi revisando la configuracion en XAMPP y phpMyAdmin hasta lograr que el servidor se conectara correctamente.

**2. Expliquen con sus palabras que habria pasado en la prueba 8 sin la transaccion.**

Sin la transaccion, cuando un pedido tuviera un producto sin suficiente stock, el sistema podria haber descontado las cantidades de otros productos antes de detectar el problema. Esto dejaria el inventario incorrecto aunque el pedido fuera rechazado. La transaccion permite cancelar todos los cambios si ocurre un error.

**3. Cada integrante escribe dos lineas sobre el aporte del otro.**

Realice el desarrollo y las pruebas del parcial de manera individual, por lo que no tuve otro integrante al cual evaluar. Me encargue de revisar la base de datos, comprobar los endpoints, realizar las pruebas y organizar la documentacion del proyecto.

**4. ¿Que nota se pondrian segun la rubrica? Justifiquen en dos lineas.**

Me pondria una nota de 95 sobre 100, porque logre configurar la base de datos, comprobar las principales operaciones de la API y preparar la documentacion solicitada. Sin embargo, reconozco que quedaron algunas pruebas.