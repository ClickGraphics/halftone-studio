# HALFTONE STUDIO — MVP 0.1

Aplicación estática para crear efectos halftone en el navegador. No requiere backend: la imagen se procesa localmente y no se sube a un servidor.

## Incluye
- Carga por selector o arrastrar y soltar.
- Patrones: puntos, líneas y difusión de error.
- Tamaño/frecuencia, ángulo, contraste, gamma y umbral.
- Fondo transparente e inversión para prendas oscuras.
- Exportación PNG con metadatos de resolución (DPI).
- Límite de procesamiento: 4500 × 5400 px, conservando proporción.

## Probar localmente
Abre `index.html` en un navegador moderno. Para evitar restricciones del navegador, también puedes iniciar un servidor local:
`python -m http.server 8000`
y visitar `http://localhost:8000`.

## Publicar gratis
1. Sube el contenido de esta carpeta a un repositorio GitHub.
2. En Cloudflare Pages, crea un proyecto conectado a ese repositorio.
3. Framework preset: None.
4. Build command: dejar vacío.
5. Build output directory: `/` (raíz del repositorio).
6. Publica. No se requiere servidor ni variables de entorno.

## Privacidad / acceso
El procesamiento ocurre en el navegador del visitante. La publicación en Pages es pública por defecto. Para la fase privada, protege el sitio con Cloudflare Access antes de compartirlo; no confíes en una contraseña añadida únicamente al JavaScript del frontend.

## Limitaciones conocidas del MVP
- Los modos de puntos y líneas son una primera implementación visual; todavía no equivalen a una validación píxel a píxel del Space original.
- El modo difusión utiliza Floyd–Steinberg sobre una cuadrícula reducida.
- El control de transparencia convierte la intensidad de tinta en alfa; revisa el resultado sobre el color real de la prenda antes de producción.
- No incluye todavía separación CMYK, perfiles ICC, previsualización física de trama ni pruebas de impresión.

## Próximas etapas
1. Comparación técnica con el original y ajuste de algoritmos.
2. Mejoras de rendimiento con Web Workers / OffscreenCanvas.
3. Presets para DTF, DTF UV y serigrafía.
4. Perfiles de exportación y dimensiones físicas en cm.
5. Acceso privado con Cloudflare Access y posterior apertura pública.