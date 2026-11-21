# Tareas de implementación AgentHub

Fuente de verdad: [SPECS.md](SPECS.md). Mantener estas casillas sin marcar hasta completar y verificar cada tarea.

## 1. Integración visual

- [ ] Crear `index.html` con estructura semántica HTML5 y `lang="es"`.
- [ ] Cargar Tailwind CSS desde CDN y configurar `darkMode: "class"`.
- [ ] Cargar Material Symbols desde CDN para iconos de navegación y acciones.
- [ ] Crear el shell principal con sidebar, barra superior y área de contenido.
- [ ] Aplicar la identidad AgentHub y la paleta clara neutral acordada.
- [ ] Definir estilos Tailwind consistentes para superficies, bordes, texto, botones y badges.
- [ ] Revisar que no haya frameworks, CSS personalizado ni atributos `style` inline.

## 2. Contenido de las 6 secciones

### Dashboard
- [ ] Cargar las métricas iniciales: `EUR 48.250`, `EUR 3.120`, agentes activos derivados y agentes fallando derivados.
- [ ] Mostrar cuatro tarjetas KPI con icono, etiqueta y valor.
- [ ] Añadir el placeholder estático «Actividad semanal», sin gráfico real.

### Usuarios
- [ ] Cargar los cinco usuarios con IDs, email, plan, estado, fecha de registro y agentes asociados de `SPECS.md`.
- [ ] Mostrar tabla con Nombre, Email, Plan, Estado y Acciones.
- [ ] Mostrar el número de agentes asociados en el detalle de cada usuario.
- [ ] Definir el estado vacío «No hay usuarios disponibles».

### Agentes
- [ ] Cargar los cuatro agentes con propietario, estado, skills y prompt de sistema.
- [ ] Mostrar nombre, propietario, estado y badge con el texto exacto.
- [ ] Mostrar las skills de cada agente en un control colapsable inicialmente cerrado.
- [ ] Definir el estado vacío «No hay agentes disponibles».

### Skills
- [ ] Cargar las cuatro skills con descripción, icono e IDs de agentes asociados.
- [ ] Añadir la explicación introductoria indicada en `SPECS.md`.
- [ ] Mostrar nombre, descripción breve y contador derivado de agentes habilitados.
- [ ] Definir el estado vacío «No hay skills disponibles».

### Contrataciones
- [ ] Cargar los cuatro contratos con cliente, agente, skills, fechas, estado e importes.
- [ ] Mostrar tabla con Cliente, Agente alquilado, Skills contratadas, Inicio, Finalización, Importe total y Acciones.
- [ ] Mostrar desglose económico por skill y verificar que cada total coincide con la suma.

### Errores
- [ ] Cargar las seis entradas con timestamp, agente, tipo, severidad, descripción, traza y estado inicial.
- [ ] Mostrar el estado `Pendiente` o `Resuelto` y el badge de tipo correspondiente.
- [ ] Mantener visibles las seis filas tras marcar errores como resueltos.

## 3. Navegación

- [ ] Crear los seis enlaces en el orden Dashboard, Usuarios, Agentes, Skills, Contrataciones y Errores.
- [ ] Cambiar de vista sin recargar la página ni usar rutas.
- [ ] Mantener una sola vista activa y actualizar el indicador activo.
- [ ] Actualizar el título superior para que coincida exactamente con la sección activa.
- [ ] Conservar los cambios de datos y el tema al cambiar de sección.

## 4. Dropdowns

- [ ] Añadir un botón de acciones accesible a cada registro y actualizar `aria-expanded`.
- [ ] Implementar las opciones de Usuarios: `Ver detalle` y `Eliminar`.
- [ ] Implementar las opciones de Agentes: `Configurar` y `Eliminar`.
- [ ] Implementar las opciones de Skills: `Ver detalle` y `Eliminar`.
- [ ] Implementar la opción de Contrataciones: `Ver detalle`.
- [ ] Implementar las opciones de Errores: `Ver detalle` y `Marcar como resuelto`.
- [ ] Mantener solo un menú abierto y cerrarlo con segundo clic o clic exterior.
- [ ] Cerrar el menú antes de ejecutar su acción y evitar que se salga del viewport.
- [ ] Deshabilitar visualmente `Marcar como resuelto` en errores ya resueltos.

## 5. Modales

- [ ] Implementar una estructura reutilizable con backdrop, panel, título y controles de cierre.
- [ ] Crear el detalle de usuario con todos los campos requeridos.
- [ ] Crear el detalle de skill con icono, descripción completa, contador y agentes asociados.
- [ ] Crear el detalle de contrato con datos y desglose económico completo.
- [ ] Crear el detalle de error con timestamp, agente, tipo, severidad, descripción, ID y traza monoespaciada.
- [ ] Crear la configuración del agente con título dinámico y `<textarea>` precargado con el prompt.
- [ ] Implementar `Guardar` para actualizar el prompt local y `Cancelar` para descartarlo.
- [ ] Cerrar modales con botón, clic en backdrop y Escape; mantener abierto al hacer clic dentro.
- [ ] Gestionar foco inicial, retorno del foco y etiqueta accesible del diálogo.

## 6. Modo oscuro

- [ ] Añadir un toggle de tema accesible en la barra superior.
- [ ] Alternar la clase `dark` sobre el elemento raíz sin recargar.
- [ ] Aplicar variantes oscuras a fondos, superficies, textos, bordes, tablas, dropdowns y modales.
- [ ] Verificar contraste de estados Activo, Suspendido, Fallando, Crítico, Advertencia e Informativo.
- [ ] Confirmar que el tema no se reinicia al navegar ni al abrir o cerrar modales.

## 7. Adaptaciones responsive

- [ ] Mantener sidebar fijo de 256 px desde `lg`.
- [ ] Mostrar drawer lateral con backdrop y botón de menú por debajo de `lg`.
- [ ] Cerrar el drawer al seleccionar sección, pulsar cerrar o hacer clic fuera.
- [ ] Adaptar el padding principal a escritorio, tablet y móvil.
- [ ] Configurar las tarjetas KPI en cuatro columnas desde `xl`, dos desde `md` y una en móvil.
- [ ] Mantener tablas legibles con scroll horizontal o presentación compacta en pantallas estrechas.
- [ ] Revisar controles táctiles de al menos 40 px y ausencia de desbordamientos o solapamientos.

## 8. Acciones locales y aceptación final

- [ ] Eliminar usuarios inmediatamente y mostrar el estado vacío al eliminar el último.
- [ ] Eliminar agentes inmediatamente y recalcular métricas y contadores de skills.
- [ ] Eliminar skills del catálogo y retirarlas de agentes y contratos según el modelo.
- [ ] Marcar errores como resueltos sin eliminar sus registros y actualizar su menú.
- [ ] Probar los seis enlaces de navegación y las acciones de todas las secciones.
- [ ] Probar el sitio a 1440 px, 768–1023 px y 390 px en los temas claro y oscuro.
- [ ] Iniciar `python3 server.py` y comprobar la página en `http://localhost:3000`.
- [ ] Confirmar que no hay llamadas a API, `fetch`, persistencia externa ni cambios de datos tras recargar.
