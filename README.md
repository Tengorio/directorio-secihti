# Directorio y Organigrama Institucional SECIHTI 2026

Herramientas de visualización del directorio de servidoras y servidores públicos de la **Secretaría de Ciencia, Humanidades, Tecnología e Innovación (SECIHTI)** — construidas a partir de datos 100% públicos.

👉 **[Ver en GitHub Pages](INSERTAR_URL)**

---

## ¿De dónde vienen los datos?

Todos los datos son públicos y provienen de fuentes oficiales. El trabajo aquí consistió en localizarlos, extraerlos, limpiarlos y organizarlos — no en generarlos. A continuación la trazabilidad completa:

### 1. Plataforma Nacional de Transparencia (SIPOT)
**Fuente principal · 229 servidoras/es públicos**

La LGTAIP obliga a todas las dependencias federales a publicar su directorio bajo el Artículo 70, fracción IV. Secihti cumple esta obligación a través del SIPOT.

- **Cómo acceder:** [plataformadetransparencia.org.mx](https://www.plataformadetransparencia.org.mx) → Buscar "Secretaría de Ciencia" → Sección *Directorio* → Descargar Excel por período
- **Período reportado:** Octubre–Diciembre 2025
- **Campos disponibles:** Nombre completo, cargo, área de adscripción, extensión telefónica, correo institucional, fecha de alta
- **Nota:** Los datos vienen en múltiples archivos por período; este repositorio unifica los más recientes en un solo dataset limpio

### 2. Portal de Transparencia de Secihti
**Fuentes complementarias · Unidad de Transparencia, Becas, SNII**

Algunos directorios operativos no aparecen en SIPOT pero están publicados directamente en el portal institucional:

| Recurso | URL |
|---|---|
| Unidad de Transparencia | [secihti.mx/…/unidad-de-transparencia](https://secihti.mx/asuntos-juridicos/transparencia/acceso-a-la-informacion/unidad-de-transparencia/) |
| Directorio de Becas Nacionales (2026) | [DIRECTORIO_BN.pdf](https://secihti.mx/wp-content/uploads/ciencia_y_humanidades/becas_y_apoyos/nacionales/documentos/2026/DIRECTORIO_BN.pdf) |
| Miércoles de Atención SNII | [secihti.mx/directorio/](https://secihti.mx/directorio/) |
| Integrantes Junta de Honor SNII | [Integrantes_Junta_de_Honor_2024.pdf](https://secihti.mx/wp-content/uploads/2026/01/Integrantes_Junta_de_Honor_2024.pdf) |

### 3. Portal CIBIOGEM
**Directorio de la Secretaría Ejecutiva y de titulares intersecretariales**

- [Directorio de titulares](https://cibiogem.secihti.mx/cibiogem-distribuidor/directorios/directorio-de-los-titulares-de-la-cibiogem/)
- [Directorio de la Secretaría Ejecutiva](https://cibiogem.secihti.mx/cibiogem-distribuidor/directorios/directorio-de-la-secretaria-ejecutiva-del-cibiogem/)

### 4. Comunicados oficiales de Secihti
**Confirmación de nombramientos y cargos de alto nivel**

Algunos cargos de nivel subsecretaría y dirección general no aparecen correctamente en el SIPOT del período cubierto (p. ej. cambios de titular posteriores a diciembre 2025). Para esos casos se verificaron comunicados de prensa oficiales:

- Nombramiento de Celina Peña Guzmán como Subsecretaria de DTVeI (vigente desde 16/feb/2026): [comunicado 10/mar/2026](https://secihti.mx/sala-de-prensa/celina-pena-guzman-asume-subsecretaria-de-desarrollo-tecnologico-vinculacion-e-innovacion-de-la-secihti/)
- Comunicado conjunto Rednacecyt (09/feb/2026), que confirma cargos de subsecretarías, DG Planeación y DG Becas: [PDF](https://secihti.mx/wp-content/uploads/2026/02/Comunicado_conjunto_09022026-1.pdf)

### 5. Estructura Orgánica Oficial
**PDF institucional de 28 páginas con el organigrama formal de Secihti**

Fuente para la jerarquía oficial de unidades administrativas. No incluye nombres de personas, pero es la referencia normativa de la estructura.

---

## Qué hay en este repositorio

| Archivo | Descripción |
|---|---|
| `index.html` | Página de inicio con estadísticas y navegación |
| `directorio.html` | Directorio completo con búsqueda y filtros por área, nivel y bloque |
| `organigrama.html` | Árbol interactivo (D3.js) con zoom, colapso y búsqueda de nodos |

---

## Limitaciones importantes

- **Período:** El SIPOT cubre hasta diciembre 2025. Cambios posteriores (como la llegada de Celina Peña Guzmán en feb/2026) se documentan solo a nivel de alta dirección.
- **Cobertura:** No todos los niveles aparecen en el SIPOT. Investgadoras e Investigadores por México (~1,300 registros) están en la base pero no en las vistas de directorio por defecto.
- **Cargos vs. personas:** El SIPOT reporta el cargo ocupado en el período, no necesariamente el titular actual. Siempre verificar con la fuente original ante dudas.
- **Sin datos sensibles:** Este repositorio no publica información que no esté ya en fuentes oficiales.

---

## ¿Quieres el dataset limpio?

El archivo Excel consolidado (SIPOT unificado + fuentes complementarias, datos limpios, sin duplicados, con columna de bloque administrativo asignado) no está incluido en el repositorio para no sobrecargar el repo con binarios.

Si lo quieres, puedes:
- **☕ [Invitarme un café](INSERTAR_URL_BMC)** y te lo mando por correo — incluye el CSV limpio y, si hay suficiente interés, el script de limpieza en Python también.
- O replicar el proceso tú mismo: descarga los Excel del SIPOT para el período que necesitas, aplica los pasos descritos en la sección de trazabilidad y úsalos como insumo.

---

## Contexto del trabajo

Este directorio no existía en forma consolidada. La información estaba dispersa en al menos cinco fuentes distintas, en formatos incompatibles, con duplicados entre períodos y sin estructura jerárquica consistente. El proceso implicó:

1. Identificar y descargar los archivos del SIPOT para los períodos relevantes
2. Unificar y deduplicar ~3,600 registros
3. Asignar cada área de adscripción a su bloque administrativo correspondiente (subsecretaría, unidad, etc.)
4. Contrastar con el PDF de estructura orgánica oficial para verificar jerarquías
5. Validar cargos de alto nivel contra comunicados públicos
6. Construir las visualizaciones HTML con D3.js y filtrado dinámico

---

*Datos públicos, trabajo propio. Abril 2026.*