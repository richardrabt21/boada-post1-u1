# Post-contenido — Unidad 1: Fundamentos de la Web

## Descripción
Repositorio del laboratorio de la Unidad 1 de Programación Web.
Contiene dos partes: configuración del entorno de desarrollo
(parte-1-entorno/) y análisis de peticiones HTTP con Chrome DevTools
y Postman (parte-2-analisis-http/).

## Parte 1 — Entorno de desarrollo
Página HTML básica inspeccionada con Chrome DevTools. Configuración
de VS Code (con extensiones ESLint, Prettier, GitLens y Live Server),
Git y GitHub. Ver parte-1-entorno/.

### Instrucciones de instalación/ejecución
1. Clonar este repositorio.
2. Abrir la carpeta parte-1-entorno/ en VS Code.
3. Instalar la extensión Live Server (si no está instalada).
4. Clic derecho sobre index.html → "Open with Live Server".

## Parte 2 — Análisis de peticiones HTTP

| # | Tipo | URL | Código |
|---|------|-----|--------|
| 1 | GET HTML | https://example.com | 200 OK |
| 2 | GET JSON (exitoso) | /posts/1 | 200 OK |
| 3 | GET JSON (fallido) | /posts/999 | 404 Not Found |
| 4 | POST JSON | /posts | 201 Created |

Ver parte-2-analisis-http/analisis/ para el detalle completo de cada análisis.

## Herramientas utilizadas
- VS Code, Git, GitHub
- Google Chrome + DevTools (panel Network)
- Postman (petición POST con tests)

## Conclusiones
Este laboratorio permitió configurar un entorno de desarrollo web
completo desde cero y comprender en profundidad el funcionamiento
del protocolo HTTP a través de la inspección de peticiones reales.
Se evidenciaron las diferencias clave entre servir contenido HTML
y consumir una API REST en formato JSON, así como el significado
práctico de los códigos de estado (200, 404, 201) en distintos
escenarios. El uso combinado de Chrome DevTools y Postman demostró
ser fundamental para depurar comunicaciones cliente-servidor: DevTools
para observar peticiones ya realizadas por el navegador, y Postman
para construir y probar peticiones personalizadas, incluyendo
validaciones automatizadas mediante tests.