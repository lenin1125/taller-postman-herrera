# Hallazgos de las Pruebas con Postman

## tabla de peticiones y resultados (Fase 2)

| # | Peticion | Codigo esperado | Codigo obtenido | Coincide? |
| :-: | :--- | :-: | :-: | :-: |
| 1 | GET /posts/1 | 200 OK | 200 OK | Si |
| 2 | GET /posts | 200 OK | 200 OK | Si |
| 3 | GET /posts/9999 | 404 Not Found | 404 Not Found | Si |
| 4 | POST /posts | 201 Created | 201 Created | Si |
| 5 | PUT /posts/1 | 200 OK | 200 OK | Si |
| 6 | PATCH /posts/1 | 200 OK | 200 OK | Si |
| 7 | DELETE /posts/1 | 200 OK | 200 OK | Si |

---

## Analisis de Resultados

### Tarea 4: recurso individual vs coleccion

GET /posts/1: devuelve un solo objeto JSON con 4 datos: userId, id, title y body.

GET /posts: devuelve una lista con 100 objetos.

diferencia en las pruebas: cuando se revisa un solo recurso, se comprueba que exista y que sus datos tengan el formato correcto. cuando se revisa una lista, se comprueba que entregue varios elementos, que tenga la cantidad esperada y que todos tengan una estructura similar.

### Tarea 5: error 404 provocado

paso o fallo el caso de prueba? el caso PASO. se esperaba recibir un 404 Not Found al buscar un recurso que no existe y se obtuvo exactamente ese resultado. un caso de prueba falla cuando el resultado obtenido no es el que se esperaba.

que pasaria si devuelve 200 con cuerpo vacio? seria un DEFECTO importante, porque el codigo 200 le estaria diciendo al usuario o al programa que la consulta fue correcta, aunque el recurso realmente no exista.

### Tarea 6: creacion con POST

observacion: al realizar la peticion POST 5 veces seguidas, siempre devuelve id: 101.

explicacion: esto sucede porque JSONPlaceholder es una API de prueba que no guarda informacion real. solamente imita lo que haria una API real y por eso siempre entrega el mismo ID.

verificacion en una API real: en una API real, cada vez que se crea un nuevo registro se generaria un ID diferente, por ejemplo 101, 102, 103 y asi sucesivamente. esto se podria comprobar haciendo un GET al nuevo ID creado.

### Tarea 7: diferencia entre PUT y PATCH

al enviar solamente {"title": "Nuevo Titulo"}:

PUT /posts/1: reemplaza la informacion del recurso y puede eliminar los datos que no fueron enviados, como body y userId, dejando el nuevo title y el id.

PATCH /posts/1: cambia solamente el dato title y mantiene los demas datos sin modificarlos.

conclusion: usaria PATCH para corregir un error de escritura, porque permite cambiar solamente ese dato sin afectar la informacion restante.

---

## Indagacion (Tareas 10 y 11)

### Tarea 10: pruebas de limite

ID mas alto con 200 OK: /posts/100

primer ID con 404 Not Found: /posts/101

nombre de la tecnica: pruebas de valores limite o frontera.

por que los errores se concentran ahi? porque al programar es comun equivocarse al establecer hasta donde debe llegar un proceso o una lista. por ejemplo, se puede indicar que termine antes o despues del punto correcto.

### Tarea 11: exploracion de otros recursos

recursos explorados: /users y /comments.

ruta probada: GET /posts/1/comments.

resultado: devuelve la lista de comentarios relacionados solamente con la publicacion que tiene el id 1. esta forma de organizar las rutas permite relacionar una publicacion con los comentarios que pertenecen a ella.

---

## Pruebas automaticas escritas (Tarea 13)

1. verificar tiempo de respuesta:

```javascript
pm.test("Tiempo de respuesta menor a 1000ms", function () {

    pm.expect(pm.response.responseTime).to.be.below(1000);

});
```
