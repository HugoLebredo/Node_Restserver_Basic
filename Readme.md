# Plantilla de Webserver Node.js

Una plantilla de un webserver utilizando Express y cors. A partir de este este esqueleto 馃拃 鈿掞笍 podemos dearrollar todo lo necesario para desplegar una aplicaci贸n de NodeJS.

Las rutas y la l贸gica se encuentran separadas.

En la versi贸n actual se a帽aden un par de Schemas para que sirvan de referencia en futuras aplicaciones

## Dependencias

1. [Express](https://github.com/expressjs/express, "express") Nos permite manejar las rutas de nuestro servidor. 
2. [cors](https://github.com/expressjs/cors, "cors") Es un middleware que nos permite solicitar recursos a una p谩gina web que se encuentre en otro dominio. Si no tenemos el [cors](https://es.wikipedia.org/wiki/Intercambio_de_recursos_de_origen_cruzado, "corsWiki") configurado.
3. [dotenv](https://www.npmjs.com/package/dotenv, "dotenv") Este m贸dulo carga como variables globales lo que introduzcamos en el archivo `.env`. En esta aplicaci贸n se utiliza para indicar en n煤mero de puerto.
4. [Mongoose](https://mongoosejs.com/, "mongoose")
5. [BcryptJS](https://www.npmjs.com/package/bcryptjs, "bcrypt") Utilizamos este paquete para encriptar las contrase帽as de los usuarios.
6. [Express-validator](https://express-validator.github.io/docs/, "express-validator") Paquete utilizado para validar el email
7. [jsonwebtoken](https://www.npmjs.com/package/jsonwebtoken, "jsonwebtoken") Utilizamos este paquete para la creaci贸n de los tokens necesarios en el proceso de autentificaci贸n con la base de datos. En esta web [JWT](https://jwt.io/, "JWT") podemos simular tokens.
8. [google-auth-library](https://www.npmjs.com/package/google-auth-library) Gracias a esta librer铆a integraremos cierta informaci贸n de nuestra cuenta de Google y la utilizaremos para crear usuarios en nuestra aplicaci贸n. Tenemos que hacer un poco de refactorizaci贸n de c贸digo de la [doc de Google](https://developers.google.com/identity/sign-in/web/backend-auth).
9. [express-fileupload](https://github.com/richardgirges/express-fileupload) Este paquete nos ayudar谩 a gestionar la subida de archivos.
10. [uuid](https://www.npmjs.com/package/uuid) Esta dependencia ser谩 la utilizada para generar los ids de las imagenes.
11. [Cloudinary](https://www.npmjs.com/package/cloudinary) Este paquete nos servir谩 para almacenar nuestras imagenes en nuestro repositorio de [Cloudinary](https://cloudinary.com/).

## Algunos tips 馃搶

 - Es habitual encontrar toda la l贸gica en el app.js. Aqui se ha creado la clase server para que quede todo m谩s pulcro. Son formas de trabajar, yo prefiero dejar el inicio de mi aplicaci贸n lo m谩s limpio posible.

 - La funcion `usersGet` espera 3 par谩metros `{id, limit, name}` Se les da un valor por defecto en caso de que la petici贸n lo los contenga para ayudar a evitar errores de ejecuci贸n.

 - En `router.put` paso la variable `id`. Ser谩 en el controlador correspondiente se gestionar谩. En este ejemplo tan solo lo muestro.

 - Normalmente no es una buena pr谩ctica pasar el archivo `.env` pero en este caso hago una excepci贸n ya que ser谩 donde definamos el puerto por el que funcionar谩 el servidor. Aunque lo correcto ser铆a subir un archivo `.example_env`.

 - En `models/server.js` est谩 dividida la l贸gica necesaria para levantar el server en las   
 
    - La funci贸n `middleware()` donde incluiremos los middlewares que necesite el serviodr.
    - La funci贸n `routes()` donde incluimos la ruta del html p煤blico (normalmente el directorio public).
    - El proceso `listen()` necesita el puerto que va a utilizar el servidor

馃憟 [Venimos de](https://es.wikipedia.org/wiki/Intercambio_de_recursos_de_origen_cruzado)

