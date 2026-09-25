# Taller de APIs y Postman

Estudiante: Lenin Anibal Herrera Salgado
Codigo: 1114089726
Asignatura: Ingenieria de Software II - Cotecnova

---

## Marco conceptual (Tarea 1)

una API REST es una forma de permitir que diferentes programas se comuniquen entre ellos usando internet. normalmente funciona mediante HTTP, donde un programa pide informacion y otro se la entrega, generalmente en formato JSON.

recurso: es la informacion que se quiere consultar o utilizar. por ejemplo, una publicacion.

endpoint: es la direccion que se utiliza para acceder a una informacion especifica dentro de una API.

ejemplo: cuando usamos Spotify para buscar un artista o una cancion, la aplicacion se comunica con los servidores de Spotify mediante una API REST. de esta manera puede solicitar la informacion necesaria para mostrarnos el artista, las canciones y permitirnos reproducir la musica.


Fuente consultada: https://developer.mozilla.org/es/docs/Glossary/REST

---

## Metodos HTTP y CRUD (Tarea 2)

| metodo HTTP | operacion CRUD | que hace |
| :--- | :--- | :--- |
| GET | Read |consulta y recupera informacion de un recurso sin editarlo. |
| POST | Create | envia informacion al servidor para crear un nuevo recurso. |
| PUT | Update | actualiza o reemplaza completamente un recurso existente. |
| PATCH | Partial Update | modifica relativamente un recurso existente sin sobrescribirlo todo. |
| DELETE | Delete | elimina un recurso especifico en el servidor. |

---

## Codigos de estado (Tarea 3)

1xx (Informativos): indican que la solicitud fue recibida y que el proceso continua. por ejemplo, 100 Continue.
2xx (Exito): indican que la solicitud se realizo correctamente. por ejemplo, 200 OK.
3xx (Redireccion): indican que se necesita realizar otra accion para completar la solicitud. por ejemplo, 301 Moved Permanently.
4xx (Errores del Cliente): indican que existe un problema con la solicitud realizada. por ejemplo, cuando la direccion no existe o faltan algunos datos. un ejemplo es 404 Not Found.
5xx (Errores del Servidor): indican que ocurrio un problema dentro del servidor al intentar responder a una solicitud correcta. por ejemplo, 500 Internal Server Error.

¿por que se separan los errores 4xx de los 5xx?
la diferencia principal es donde se encuentra el problema:
en los 4xx, el problema esta relacionado con la solicitud que envio el cliente. por ejemplo, cuando se escribe una direccion incorrecta, faltan datos o no se tiene permiso para acceder.
en los 5xx, el problema ocurre en el servidor. la solicitud puede estar bien hecha, pero el servidor tiene algun problema para procesarla, como un error interno o una falla en la base de datos.

---

## Archivos de este repositorio
- README.md: Marco conceptual y teoria del taller.
- hallazgos.md: Registro de peticiones, respuestas y hallazgos en Postman.
- conclusiones.md: Respuestas sobre idempotencia, cabeceras y preguntas finales.
- coleccion.json: Coleccion de pruebas exportada desde Postman.
- evidencias/: Capturas de pantalla que demuestran la ejecucion de las pruebas.