# Dashboard de Piezometría — Área de Estudio

Dashboard interactivo (HTML autocontenido) con:

- **Niveles piezométricos**: series de tiempo por pozo, mapa satelital, estadísticas.
- **Caudales de extracción**: superpuestos en la serie de tiempo de cada pozo (diario y mensual).
- **Geoquímica**: diagramas de Piper, Schoeller y Stiff por sector y por muestra, con opción de ver "Todos los datos" o "Solo la media" del sector.
- **Isótopos**: gráfico δ18O vs δ2H con líneas meteóricas (GMWL/LMWL/LEL) por sector.

## Cómo verlo

### Opción 1: GitHub Pages (recomendado — un solo link, sin descargar nada)

1. Sube esta carpeta a un repositorio de GitHub (ver más abajo).
2. En el repo: **Settings → Pages → Source**, selecciona la rama (`main`) y la carpeta raíz (`/`).
3. GitHub publicará el sitio en `https://<tu-usuario>.github.io/<nombre-repo>/` (tarda 1-2 minutos).
4. Comparte esa URL con tus colegas — se abre directo en el navegador, con internet no hace falta nada más.

### Opción 2: Descargar y abrir localmente

1. Descarga (o clona) el repositorio completo — **`index.html` y la carpeta `geochem_images/` deben quedar en la misma ubicación relativa** (no compartas solo el `.html` suelto, las imágenes de geoquímica no cargarán).
2. Abre `index.html` con doble clic. Se necesita conexión a internet: el dashboard carga las librerías de gráficos (Plotly) y mapas (Leaflet) desde internet, no están incluidas en el archivo.

## Contenido de esta carpeta

- `index.html` — el dashboard completo (datos embebidos en el HTML).
- `geochem_images/` — 646 imágenes PNG (Piper, Schoeller, Stiff) referenciadas por `index.html`.

## Subir esta carpeta a GitHub (primera vez)

Requiere tener [Git](https://git-scm.com/downloads) instalado y una cuenta de GitHub.

```
cd "GitHub_Dashboard"
git init
git add .
git commit -m "Dashboard de piezometria, geoquimica e isotopos"
git branch -M main
git remote add origin https://github.com/<tu-usuario>/<nombre-repo>.git
git push -u origin main
```

Si no tienes un repositorio creado aún, créalo primero en https://github.com/new (puede ser privado si solo quieres compartirlo con colegas específicos que agregues como colaboradores).

## Actualizar el dashboard más adelante

Este HTML se genera automáticamente desde los scripts `generar_dashboard.py` y `process_geochem.py` (carpeta `BBDD Kinross/Piezometria/`). Para publicar una versión nueva:

1. Vuelve a correr esos scripts para regenerar `Niveles_Area_Estudio.html` y `geochem_images/`.
2. Copia los archivos actualizados a esta carpeta (reemplazando `index.html` y `geochem_images/`).
3. `git add . && git commit -m "Actualizacion de datos" && git push`
