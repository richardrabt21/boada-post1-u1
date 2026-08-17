# Análisis 2: Petición GET — API REST (JSONPlaceholder)

## Información general — Petición exitosa
- URL: https://jsonplaceholder.typicode.com/posts/1
- Método: GET
- Código de estado: 200 OK

## Headers de Response (petición exitosa)
| Header | Valor | Significado |
|--------|-------|--------------|
| Content-Type | application/json; charset=utf-8 | Indica que el cuerpo es JSON, no HTML |
| Cache-Control | max-age=43200 | El navegador puede reutilizar la respuesta hasta por 12 horas |
| Etag | W/"124-viKdLzqO5qBrJFrcdJ8Y..." | Identificador único de esta versión del recurso, usado para validar caché |
| Age | 21494 | Segundos que el recurso lleva en la caché de la CDN |
| Cf-Cache-Status | HIT | La respuesta fue servida desde la caché de Cloudflare, no desde el origen |

## Cuerpo de la respuesta (JSON)
```json
{
  "userId": 1,
  "id": 1,
  "title": "sunt aut facere repellat provident occaecati excepturi optio reprehenderit",
  "body": "quia et suscipit\nsuscipit recusandae..."
}
```

## Información general — Petición fallida
- URL: https://jsonplaceholder.typicode.com/posts/999
- Método: GET
- Código de estado: 404 Not Found
- Cuerpo de la respuesta: `{}` (objeto vacío)

## Comparación HTTP (HTML) vs API REST (JSON)
| Aspecto | Página HTML (example.com) | API REST (JSONPlaceholder) |
|---------|---------------------------|------------------------------|
| Content-Type | text/html | application/json |
| Formato de respuesta | Documento HTML completo | Objeto/array JSON estructurado |
| Uso típico | Renderizar contenido visual en el navegador | Intercambio de datos entre sistemas (frontend-backend, apps) |
| Manejo de recurso inexistente | Redirección o página de error HTML | Código 404 con cuerpo JSON vacío o con mensaje de error |

## Conclusión
La API REST responde con Content-Type: application/json, a diferencia de la página HTML analizada en el paso anterior que respondía con text/html — esta diferencia es fundamental porque le indica al cliente (navegador, app, u otro programa) cómo debe interpretar el cuerpo de la