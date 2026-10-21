# Bitacora del proyecto

**Proyecto:** Parcial 1 - Programacion  
**Materia:** Programacion Web IV  
**Estudiante:** Gibrham Jossell Cedeño de Alba  
**Fecha:** 21 de octubre de 2026

## Inicio del proyecto

Para comenzar con el parcial, se revisaron las herramientas necesarias para trabajar con Node.js, Express y MySQL. Se utilizo Visual Studio Code para revisar los archivos del proyecto y XAMPP para administrar la base de datos desde phpMyAdmin.

Tambien se comprobo que Git y npm estuvieran funcionando correctamente para poder trabajar con las dependencias y guardar los cambios en GitHub.

## Configuracion de la base de datos

Durante la configuracion de MySQL se presentaron algunos inconvenientes. Al principio, las tablas estaban ubicadas en una base de datos diferente, por lo que fue necesario copiarlas a `parcial1_gibrham`.

Despues se presento un error de conexion porque el usuario configurado en el archivo `.env` no tenia acceso a MySQL. Para solucionarlo, se creo el usuario correspondiente y se le asignaron los permisos necesarios.

Finalmente, se logro establecer la conexion y consultar los diez productos registrados.

## Funcionamiento de la API

Una vez solucionada la conexion, se iniciaron las pruebas del servidor con Node.js y Express. Primero se comprobo que los productos aparecieran correctamente y que fuera posible consultar uno mediante su identificador.

Posteriormente se trabajaron los pedidos. Se creo un pedido de prueba, se consulto su informacion y se cambio su estado de pendiente a pagado.

Tambien se verifico que los cambios quedaran guardados en MySQL.

## Pruebas realizadas

Para comprobar el funcionamiento de la API se utilizo Thunder Client. Se realizaron consultas de productos y pedidos, ademas de pruebas con datos incorrectos para verificar las respuestas del servidor.

Entre las pruebas realizadas estuvieron los pedidos sin cliente, las cantidades negativas, los productos inexistentes y los pedidos con stock insuficiente.

Una de las comprobaciones mas importantes fue verificar que, cuando un pedido se rechaza por falta de stock, las cantidades de los productos no cambian. Esto permitio confirmar el funcionamiento de las transacciones.

## Documentacion y GitHub

Se reviso el archivo `README.md` para organizar los endpoints y los resultados de las pruebas. Tambien se utilizo Swagger para visualizar la documentacion y ejecutar una consulta de productos desde el navegador.

Por otra parte, se configuro Git y se vinculo el proyecto con el repositorio correspondiente en GitHub. Se revisaron los archivos de configuracion para mantener las credenciales de la base de datos fuera del repositorio.

## Resultado del trabajo

Al finalizar las comprobaciones, la API permitio consultar productos, registrar pedidos, cambiar sus estados y responder correctamente cuando se enviaban datos incorrectos.

Los principales inconvenientes estuvieron relacionados con la configuracion de MySQL y algunos metodos utilizados durante las pruebas. Estos problemas se fueron solucionando hasta conseguir que el proyecto funcionara correctamente.