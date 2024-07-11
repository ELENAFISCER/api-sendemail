# API de Envío de Correos

Esta API permite al usuario mandar emails a través de una solicitud HTTP usando el método POST. Está diseñada para recibir datos JSON y enviar email al webmaster.


## Cómo se realiza una solicitud

### Formato de la Solicitud
La solicitud debe ser POST y el contenido debe estar en JSON.

### Cuerpo de la Solicitud
```json

POST http://dominio/api/v1/endpoint-webservice/
Content-Type: "application/json"

{
  "name": "Nombre del remitente",
  "email": "Correo electrónico del remitente",
  "message": "Mensaje enviado"
}
````
## Posibles respuestas recibidas

### Respuesta con éxito
Cuando todos los datos están completos y correctos la respuesta es exitosa y aparece de la siguiente forma:
````json
{
  "status": "success",
  "message": "Correo enviado correctamente."
}
````

### Respuesta inválida
Cuando falta algún dato o no son correctos nos dará esta respuesta: 
````json
{
  "status": "error",
  "message": "Datos inválidos."
}
````

### Respuesta errónea
Cuando hay un error en la conexión con el servidor la respuesta nos aparecerá es la siguiente:
````json
{
  "status": "error",
  "message": "Error al enviar el correo."
}
````