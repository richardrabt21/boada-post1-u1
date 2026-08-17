# Análisis 3: Petición POST — Postman (JSONPlaceholder)

## Configuración de la petición
- URL: https://jsonplaceholder.typicode.com/posts
- Método: POST
- Header enviado: Content-Type: application/json
- Cuerpo (raw JSON):
```json
{
  "title": "Laboratorio Programacion Web",
  "body": "Analisis de peticiones HTTP con Postman.",
  "userId": 1
}
```

## Respuesta recibida
- Código de estado: 201 Created
- Tiempo de respuesta: 532 ms
- Tamaño: 1.32 KB

```json
{
  "title": "Laboratorio Programacion Web",
  "body": "Analisis de peticiones HTTP con Postman.",
  "userId": 1,
  "id": 101
}
```

## Headers relevantes de la respuesta
| Header | Valor | Significado |
|--------|-------|--------------|
| Location | https://jsonplaceholder.typicode.com/posts/101 | URL del nuevo recurso creado |
| Content-Type | application/json; charset=utf-8 | El cuerpo de la respuesta es JSON |
| Content-Length | 127 | Tamaño en bytes del cuerpo de la respuesta |
| Cache-Control | no-cache | El recurso creado no debe almacenarse en caché |

## Resultado de los tests
| Test | Resultado |
|------|-----------|
| Status 201 Created | ✅ PASSED |
| Respuesta incluye id asignado | ✅ PASSED |

## Diferencias entre GET y POST
| Aspecto | GET | POST |
|---------|-----|------|
| Propósito | Solicitar/leer un recurso existente | Crear un nuevo recurso en el servidor |
| Cuerpo (body) | No lleva cuerpo | Lleva un cuerpo con los datos a enviar |
| Código de éxito típico | 200 OK | 201 Created |
| Idempotencia | Sí (repetir la misma petición no cambia el estado del servidor) | No (repetir la petición puede crear múltiples recursos) |
| Visibilidad de datos | Los parámetros suelen ir en la URL | Los datos van en el cuerpo, no en la URL |

## Conclusión
La petición POST a /posts retornó un código 201 Created, confirmando que el servidor "creó" el recurso exitosamente (JSONPlaceholder simula la creación sin persistir realmente los datos). El servidor asignó automáticamente un campo id (101) al objeto enviado, y devolvió el header Location apuntando a la URL del nuevo recurso, siguiendo las buenas prácticas de una API RESTful. A diferencia de las peticiones GET analizadas anteriormente, esta petición requirió especificar un método diferente, un header Content-Type y un cuerpo en formato JSON. Los dos tests automatizados en Postman (verificación del código de estado y de la presencia del campo id) pasaron exitosamente, validando que la respuesta cumple con el comportamiento esperado de una API REST al crear un recurso.