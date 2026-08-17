# Análisis 1: Petición GET — example.com

## Información general
- URL: https://example.com/
- Método: GET
- Código de estado: 200 OK

## Headers de Request
| Header | Valor |
|--------|-------|
| Host (:authority) | example.com |
| User-Agent | Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/151.0.0.0 Safari/537.36 |
| Accept | text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7 |

## Headers de Response
| Header | Valor | Significado |
|--------|-------|--------------|
| Content-Type | text/html | Indica que el cuerpo de la respuesta es HTML |
| Cache-Control | (no presente explícitamente) | El servidor no envió esta directiva en esta respuesta |
| Content-Encoding | br | El contenido fue comprimido con Brotli antes de enviarse |
| Server | cloudflare | El servidor está detrás de una CDN de Cloudflare |
| Age | 1983 | Segundos que el recurso lleva almacenado en la caché de la CDN |
| Date | Mon, 17 Aug 2026 20:40:47 GMT | Fecha y hora en que se generó la respuesta |

## Tiempos de carga
| Fase | Tiempo (ms) |
|------|------------|
| Queueing | 1.79 |
| Stalled | 2.27 |
| Request sent | 0.47 |
| TTFB (Waiting for server response) | 121.97 |
| Content Download | 3.51 |
| **Total** | **130.01** |

## Conclusión
La petición a example.com retornó un código 200 OK con contenido HTML servido a través de una CDN de Cloudflare, evidenciado por el header Server y el Cf-Cache-Status. La mayor parte del tiempo total (121.97 ms de 130.01 ms) corresponde a la espera de la respuesta del servidor (TTFB), mientras que la descarga del contenido fue casi instantánea gracias al pequeño tamaño de la página. No se registraron fases separadas de DNS Lookup ni SSL, lo que sugiere que la conexión ya estaba parcialmente establecida o cacheada por el navegador. El uso del header Content-Encoding: br confirma que el servidor comprime el contenido con Brotli para optimizar la transferencia.