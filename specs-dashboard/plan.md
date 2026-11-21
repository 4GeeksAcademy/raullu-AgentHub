## Plan: AgentHub en un único HTML

Implementar un prototipo local de seis vistas en un único `index.html`, tomando `specs-dashboard/SPECS.md` como contrato funcional y los cuatro HTML de Stitch como guía visual. Reutilizar la composición y el lenguaje visual de sus dashboards, tarjetas móviles, tabla, drawer, acordeones, badges y modales, pero reemplazar datos y comportamientos con el modelo exacto del spec.

**Tareas de implementación**
1. **Integración visual** — Crear `index.html` con HTML5, Tailwind CDN, Material Symbols y el shell visual inspirado en Stitch: sidebar, topbar, área principal, superficies, tipografía y controles. Configurar el tema claro neutral; no incluir CSS externo ni estilos inline. *Base para las tareas 2–7.*
2. **Contenido de las 6 secciones** — Añadir el estado hardcodeado del modelo de `SPECS.md` y renderizadores para Dashboard (4 KPIs y placeholder sin gráfico), Usuarios (tabla), Agentes (propietario/estado/skills), Skills (bloque explicativo y catálogo), Contrataciones (tabla y desglose) y Errores (seis registros). Incluir vacíos donde corresponde y derivar contadores de las colecciones en memoria. *Depende de 1.*
3. **Navegación** — Conectar las seis secciones sin recarga, mantener una sola vista activa, actualizar el título exacto y el indicador activo, y conservar el estado de datos al cambiar de vista. *Depende de 1 y 2.*
4. **Dropdowns** — Implementar un dropdown único por vez para Usuarios, Agentes, Skills, Contrataciones y Errores; cerrar por segundo clic, clic externo o al ejecutar una acción, con posición dentro del viewport y atributos accesibles. Opciones: Usuarios y Skills, `Ver detalle`/`Eliminar`; Agentes, `Configurar`/`Eliminar`; Contratos, `Ver detalle`; Errores, `Ver detalle`/`Marcar como resuelto` (deshabilitada si ya está resuelto). *Depende de 2 y 3.*
5. **Modales** — Crear una base reutilizable para detalles de usuario, skill, contrato y error, además de configuración de agente con `<textarea>`. Cerrar con botón, backdrop y Escape; clic interior no cierra. Guardar/cancelar prompt, retornar foco y evitar editar al cancelar. *Depende de 2 y 4.*
6. **Modo oscuro** — Incorporar toggle global que añade/elimina `dark` en la raíz y preserve el tema al navegar y abrir/cerrar modales. Definir variantes Tailwind para todas las superficies, textos, bordes y estados semánticos. *Depende de 1; integrar con 3 y 5.*
7. **Adaptaciones responsive** — Completar sidebar fijo desde `lg`, drawer/backdrop por debajo de `lg`, espaciado adaptable, KPIs 4/2/1 columnas, tablas legibles con scroll o presentación compacta y controles táctiles. *Depende de 1–6.*
8. **Verificación final** — Ejecutar el servidor del repositorio y validar manualmente datos, acciones locales, temas, accesibilidad básica y los breakpoints definidos. Corregir defectos contra criterios de aceptación, sin ampliar alcance.

**Archivos relevantes**
- `index.html` — único archivo nuevo; shell, vistas, datos, renderizado e interacciones.
- `specs-dashboard/SPECS.md` — fuente normativa para etiquetas, estados, modelo, alcance y aceptación.
- `stitch-reference/code-desktop.html` y `code-desktop-dm.html` — guía para sidebar, barra superior, densidad de escritorio, tablas, tarjetas y variante oscura.
- `stitch-reference/code-mobile.html` y `code-mobile-dm.html` — guía para drawer, tarjetas compactas, modales y jerarquía móvil.
- `DESIGN.md` y `DESIGN-DARKMODE.md` — consultar solo como referencia secundaria; unificar tokens según el spec y corregir contradicciones entre ambos.
- `server.py` — sirve `index.html` en el puerto 3000.

**Verificación por tareas**
1. Tras **Integración visual**, iniciar `python3 server.py`, abrir `http://localhost:3000` y revisar carga, tema base y shell.
2. Tras **Contenido**, verificar los datos iniciales: cinco usuarios, cuatro agentes (3 activos/1 fallando), contadores de skills 3/2/2/1, cuatro contratos con sumas exactas y seis errores.
3. Tras **Navegación**, recorrer las seis secciones y comprobar indicador/título exactos y que los cambios en memoria sobreviven al cambio de vista.
4. Tras **Dropdowns** y **Modales**, probar acciones, menú único y cierre externo; validar botón/backdrop/Escape, clic interior, foco y guardar/cancelar prompt.
5. Tras **Modo oscuro**, alternar tema y recorrer vistas y modales para detectar superficies, textos o bordes sin variante adecuada.
6. Tras **Adaptaciones responsive**, revisar 1440 px, 768–1023 px y 390 px; confirmar sidebar/drawer, KPIs 4/2/1, controles táctiles, tablas legibles y ausencia de desbordamientos.
7. Recorrer eliminaciones y resolución de errores; confirmar estados vacíos requeridos, que las filas de errores se conservan y que recargar restablece los datos iniciales.
8. Confirmar que el único archivo creado/modificado es `index.html`, sin frameworks, fetch/APIs, persistencia externa, CSS personalizado ni atributos `style`.

**Decisiones**
- Prioridad absoluta a `specs-dashboard/SPECS.md`; los valores y acciones divergentes de Stitch se descartan. Se conservan patrones visuales, no el contenido ajeno al modelo.
- Una sola página y un solo estado JavaScript en memoria; renderizar la vista activa desde ese estado para mantener coherentes datos y métricas.
- Recomendación visual: claro `#F8FAFC` / `#FFFFFF` / `#E2E8F0`, texto `#0F172A` / `#475569`, azul `#2563EB`; oscuro `#0B0F17` / `#111827` / `#1E293B`, borde `#1F2937`, texto `#F8FAFC` / `#94A3B8`, azul `#3B82F6`. Estados semánticos verde, ámbar y rojo según contraste por tema.
- El Dashboard usa solo el placeholder estático, aunque Stitch muestre gráficos. Usuarios y contratos siguen semántica de tabla; en móvil pueden usar scroll horizontal o filas compactas, según legibilidad.
- Reutilizar la paleta neutral exigida por el spec sobre el tinte lavanda de `DESIGN.md` y normalizar los tokens oscuros contradictorios de `DESIGN-DARKMODE.md`.
- Mantener el CDN del prototipo Stitch (`https://cdn.tailwindcss.com`) y `tailwind.config` con `darkMode: "class"` para compatibilidad directa con sus utilities/configuración; el `README.es.md` recomienda Tailwind v4, por lo que confirmar la compatibilidad de clases al implementar y no mezclar sintaxis de versiones.
- No incluir acciones fuera del alcance como crear/exportar usuarios o contratos, reiniciar agentes, resolver todos los errores o enviar facturas.

**Fuera de alcance**
- Backend, autenticación, APIs, fetch, persistencia al recargar, framework frontend, CSS personalizado externo y funcionalidades comerciales u operativas reales.
