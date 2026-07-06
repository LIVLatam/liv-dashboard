# LIV · Dashboard web

Panel de control logístico y contractual de LIV México. Esta carpeta es el **proyecto** (el "repositorio") listo para publicarse en internet y compartirse con el equipo.

---

## Qué hay adentro (y por qué en dos archivos)

La idea central: **separar el diseño de los datos.** Antes todo vivía pegado en un solo HTML; ahora son dos piezas:

- **`index.html`** → el **motor y el diseño** del dashboard (las pestañas, filtros, tablas, colores). Esto casi no cambia.
- **`datos.js`** → **solo los datos** (un colegio por registro). Esto es lo que se actualiza.
- **`README.md`** → este archivo.

Ventaja: para actualizar la información NO se toca el diseño. Se cambian los datos y el dashboard se refresca solo. Nunca más "un HTML nuevo".

---

## Cómo verlo ahora mismo (sin internet, sin instalar nada)

Abrí **`index.html`** con doble clic (se abre en tu navegador). Toma los datos de `datos.js`, que está en la misma carpeta. Listo: ves el dashboard completo.

> Importante: `index.html` y `datos.js` tienen que estar **en la misma carpeta**. Si movés uno, movés los dos.

---

## De dónde salen los datos

La **fuente de verdad legible** es la pestaña **`Datos_Dashboard`** del Excel `Logística LIV México - campaña 1.xlsx` (en Drive). Una fila = un colegio, con todas las columnas del dashboard en español (Sí/No, precios por año, alumnos por grado, bonificación, particularidades, etc.).

Flujo actual:
1. Se actualiza la pestaña **Datos_Dashboard** del Excel (a mano o vía Claude).
2. Claude regenera `datos.js` a partir de esa tabla.
3. El dashboard queda actualizado.

Próximo paso (para que sea 100% automático): conectar `datos.js` a una **Google Sheet publicada**, así el dashboard lee los datos en vivo sin regenerar nada.

---

## Cómo publicarlo para el equipo (GitHub Pages · gratis)

Objetivo: obtener **una URL** que el equipo abre y siempre está actualizada. Pasos generales (te acompaño en vivo cuando quieras):

1. En **github.com** → **New repository** (repositorio nuevo). Nombre sugerido: `liv-dashboard`. Elegí **Public**. Create.
2. En el repo → **Add file → Upload files**. Arrastrá `index.html`, `datos.js` y `README.md`. Abajo, **Commit changes** (guardar).
3. En el repo → **Settings → Pages**. En *Source* elegí **Deploy from a branch**, rama **main**, carpeta **/(root)**. **Save**.
4. Esperá ~1 minuto. GitHub te muestra la dirección pública: `https://TU-USUARIO.github.io/liv-dashboard/`. Esa es la que compartís al equipo.

Para actualizar en el futuro: se sube el `datos.js` nuevo (mismo botón *Upload files*) y la web se actualiza sola.

---

## Glosario rápido

- **Repositorio / repo:** la carpeta del proyecto con su historial (como un Drive para código).
- **GitHub Pages:** el servicio gratis de GitHub que convierte estos archivos en una página web pública.
- **Deploy / publicar:** subir el proyecto a internet para que tenga una URL.
- **`datos.js`:** el archivo con los datos; lo único que se cambia para actualizar el panel.

_Generado con Claude · Julio 2026._
