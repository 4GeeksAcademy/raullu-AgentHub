# Tareas de implementación AgentHub

Fuente de verdad: [SPECS.md](SPECS.md). Mantener estas casillas sin marcar hasta completar y verificar cada tarea.

## 1. Integración visual

- [x] Crear `index.html` con estructura semántica HTML5 y `lang="es"`.
- [x] Cargar Tailwind CSS desde CDN y configurar `darkMode: "class"`.
- [x] Cargar Material Symbols desde CDN para iconos de navegación y acciones.
- [x] Crear el shell principal con sidebar, barra superior y área de contenido.
- [x] Aplicar la identidad AgentHub y la paleta clara neutral acordada.
- [x] Definir estilos Tailwind consistentes para superficies, bordes, texto, botones y badges.
- [x] Revisar que no haya frameworks, CSS personalizado ni atributos `style` inline.

## 2. Contenido de las 6 secciones

### Dashboard
- [x] Cargar las métricas iniciales: `EUR 48.250`, `EUR 3.120`, agentes activos derivados y agentes fallando derivados.
- [x] Mostrar cuatro tarjetas KPI con icono, etiqueta y valor.
- [x] Añadir el placeholder estático «Actividad semanal», sin gráfico real.

### Usuarios
- [x] Cargar los cinco usuarios con IDs, email, plan, estado, fecha de registro y agentes asociados de `SPECS.md`.
- [x] Mostrar tabla con Nombre, Email, Plan, Estado y Acciones.
- [x] Mostrar el número de agentes asociados en el detalle de cada usuario.
- [x] Definir el estado vacío «No hay usuarios disponibles».

### Agentes
- [x] Cargar los cuatro agentes con propietario, estado, skills y prompt de sistema.
- [x] Mostrar nombre, propietario, estado y badge con el texto exacto.
- [x] Mostrar las skills de cada agente en un control colapsable inicialmente cerrado.
- [x] Definir el estado vacío «No hay agentes disponibles».

### Skills
- [x] Cargar las cuatro skills con descripción, icono e IDs de agentes asociados.
- [x] Añadir la explicación introductoria indicada en `SPECS.md`.
- [x] Mostrar nombre, descripción breve y contador derivado de agentes habilitados.
- [x] Definir el estado vacío «No hay skills disponibles».

### Contrataciones
- [x] Cargar los cuatro contratos con cliente, agente, skills, fechas, estado e importes.
- [x] Mostrar tabla con Cliente, Agente alquilado, Skills contratadas, Inicio, Finalización, Importe total y Acciones.
- [x] Mostrar desglose económico por skill y verificar que cada total coincide con la suma.

### Errores
- [x] Cargar las seis entradas con timestamp, agente, tipo, severidad, descripción, traza y estado inicial.
- [x] Mostrar el estado `Pendiente` o `Resuelto` y el badge de tipo correspondiente.
- [x] Mantener visibles las seis filas tras marcar errores como resueltos.

## 3. Navegación

- [x] Crear los seis enlaces en el orden Dashboard, Usuarios, Agentes, Skills, Contrataciones y Errores.
- [x] Cambiar de vista sin recargar la página ni usar rutas.
- [x] Mantener una sola vista activa y actualizar el indicador activo.
- [x] Actualizar el título superior para que coincida exactamente con la sección activa.
- [x] Conservar los cambios de datos y el tema al cambiar de sección.

## 4. Dropdowns

- [x] Añadir un botón de acciones accesible a cada registro y actualizar `aria-expanded`.
- [x] Implementar las opciones de Usuarios: `Ver detalle` y `Eliminar`.
- [x] Implementar las opciones de Agentes: `Configurar` y `Eliminar`.
- [x] Implementar las opciones de Skills: `Ver detalle` y `Eliminar`.
- [x] Implementar la opción de Contrataciones: `Ver detalle`.
- [x] Implementar las opciones de Errores: `Ver detalle` y `Marcar como resuelto`.
- [x] Mantener solo un menú abierto y cerrarlo con segundo clic o clic exterior.
- [x] Cerrar el menú antes de ejecutar su acción y evitar que se salga del viewport.
- [x] Deshabilitar visualmente `Marcar como resuelto` en errores ya resueltos.

## 5. Modales

- [x] Implementar una estructura reutilizable con backdrop, panel, título y controles de cierre.
- [x] Crear el detalle de usuario con todos los campos requeridos.
- [x] Crear el detalle de skill con icono, descripción completa, contador y agentes asociados.
- [x] Crear el detalle de contrato con datos y desglose económico completo.
- [x] Crear el detalle de error con timestamp, agente, tipo, severidad, descripción, ID y traza monoespaciada.
- [x] Crear la configuración del agente con título dinámico y `<textarea>` precargado con el prompt.
- [x] Implementar `Guardar` para actualizar el prompt local y `Cancelar` para descartarlo.
- [x] Cerrar modales con botón, clic en backdrop y Escape; mantener abierto al hacer clic dentro.
- [x] Gestionar foco inicial, retorno del foco y etiqueta accesible del diálogo.

## 6. Modo oscuro

- [x] Añadir un toggle de tema accesible en la barra superior.
- [x] Alternar la clase `dark` sobre el elemento raíz sin recargar.
- [x] Aplicar variantes oscuras a fondos, superficies, textos, bordes, tablas, dropdowns y modales.
- [x] Verificar contraste de estados Activo, Suspendido, Fallando, Crítico, Advertencia e Informativo.
- [x] Confirmar que el tema no se reinicia al navegar ni al abrir o cerrar modales.

## 7. Adaptaciones responsive

- [x] Mantener sidebar fijo de 256 px desde `lg`.
- [x] Mostrar drawer lateral con backdrop y botón de menú por debajo de `lg`.
- [x] Cerrar el drawer al seleccionar sección, pulsar cerrar o hacer clic fuera.
- [x] Adaptar el padding principal a escritorio, tablet y móvil.
- [x] Configurar las tarjetas KPI en cuatro columnas desde `xl`, dos desde `md` y una en móvil.
- [x] Mantener tablas legibles con scroll horizontal o presentación compacta en pantallas estrechas.
- [ ] Revisar controles táctiles de al menos 40 px y ausencia de desbordamientos o solapamientos.

## 8. Acciones locales y aceptación final

- [x] Eliminar usuarios inmediatamente y mostrar el estado vacío al eliminar el último.
- [x] Eliminar agentes inmediatamente y recalcular métricas y contadores de skills.
- [x] Eliminar skills del catálogo y retirarlas de agentes y contratos según el modelo.
- [x] Marcar errores como resueltos sin eliminar sus registros y actualizar su menú.
- [x] Probar los seis enlaces de navegación y las acciones de todas las secciones.
- [ ] Probar el sitio a 1440 px, 768–1023 px y 390 px en los temas claro y oscuro.
- [ ] Iniciar `python3 server.py` y comprobar la página en `http://localhost:3000`.
- [x] Confirmar que no hay llamadas a API, `fetch`, persistencia externa ni cambios de datos tras recargar.
