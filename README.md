# USER-POC

El proyecto es una prueba de concepto para la creación de usuarios.

Todos los endpoints deben aceptar y retornar solamente JSON, inclusive al para los mensajes de error.

Todos los mensajes deben seguir el formato:
```json
{"mensaje": "mensaje de error"}
```

## Registro

* Ese endpoint deberá recibir un usuario con los campos "nombre", "correo", "contraseña", más un listado de objetos
"teléfono", respetando el siguiente formato:
    ```json
    {
        "name": "Juan Rodriguez",
        "email": "juan@rodriguez.org",
        "password": "hunter2",
        "phones": [
            {
                "number": "1234567",
                "citycode": "1",
                "countrycode": "57"
            }
        ]
    }
    ```

* Responder el código de status HTTP adecuado.

* En caso de éxito, retorne el usuario y los siguientes campos:
  - __id__: id del usuario (puede ser lo que se genera por el banco de datos, pero sería más deseable un UUID).
  - __created__: fecha de creación del usuario.
  - __modified__: fecha de la última actualización de usuario.
  - __last_login__: del último ingreso (en caso de nuevo usuario, va a coincidir con la fecha de creación)
  - __token__: token de acceso de la API (puede ser UUID o JWT).
  - __is_active__: Indica si el usuario sigue habilitado dentro del sistema.

* Si caso el correo conste en la base de datos, deberá retornar un error "El correo ya registrado".

* El correo debe seguir una expresión regular para validar que formato sea el correcto (aaaaaaa@dominio.cl).

* La clave debe seguir una expresión regular para validar que formato sea el correcto. (Una Mayuscula, letras
minúsculas, y dos numeros).

* El token deberá ser persistido junto con el usuario.

## Requisitos
* Plazo: 2 días.
* Banco de datos en memoria, como HSQLDB o H2.
* Proceso de build via Gradle.
* Persistencia con Hibernate.
* Framework Spring.
* Servidor Tomcat o Jetty Embedded.
* Java 8+.
* Entrega en un repositorio público (github o bitbucket) con el código fuente y script de creación de BD.
* Entrega diagrama de la solución.
* Pruebas de unidad.

## Requisitos deseables
* JWT cómo token
