### Conclusiones.md

```markdown
# Conclusiones e Indagacion Autonoma

## Tarea 8: Idempotencia en HTTP

un metodo HTTP es estable si ejecutarlo multiples veces seguidas produce el mismo efecto en el servidor que ejecutarlo una sola vez.

- metodos estables: GET, PUT, DELETE.
- metodos NO estables: POST, PATCH.

prueba en Postman:
- Al ejecutar PUT /posts/1 varias veces, el resultado en el servidor siempre mantiene el objeto en el mismo estado actualizado.
- En una API, ejecutar POST /posts multiples veces creara multiples recursos nuevos en la base de datos cada vez.

---

## Tarea 9: Cabeceras de Respuesta (Headers)

1. content-type (application/json; charset=utf-8): indica que tipo de informacion esta enviando el servidor. en este caso, muestra que los datos estan en formato json y permite saber como debe leerlos el programa que los recibe.

2. cache-control: indica como se debe guardar la informacion recibida para poder usarla nuevamente sin tener que pedirla al servidor cada vez. por ejemplo, puede indicar cuanto tiempo se puede guardar.

3. server: muestra que sistema o servicio esta utilizando el servidor para funcionar. por ejemplo, puede indicar que utiliza cloudflare.


---

## Dos Preguntas Finales (Sustentacion)

### 1. que le falta a la tabla de la fase 2 para ser un plan de pruebas formal?

le faltan algunos datos importantes para que sea un plan de pruebas completo, como: un numero para identificar cada prueba, el nombre o descripcion de la prueba, los requisitos necesarios antes de realizarla, los datos que se van a utilizar, el lugar donde se realizara la prueba, la importancia de cada prueba y el resultado final, es decir, si la prueba fue correcta o fallo.

### 2. por que un 404 puede ser una buena noticia y un 200 un defecto?

un 404 puede ser algo bueno cuando se busca algo que no existe, porque significa que el sistema se dio cuenta de que ese recurso no esta disponible y respondio correctamente. en cambio, un 200 seria un problema si se busca algo que no existe, porque el sistema estaria diciendo que todo esta bien y que encontro la informacion, cuando realmente no es asi.
