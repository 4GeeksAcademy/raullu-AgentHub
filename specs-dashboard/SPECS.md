# Especificacion funcional y visual de AgentHub

## 1. Vision general del producto

AgentHub es un panel SaaS interno para administradores. Permite supervisar usuarios, agentes de inteligencia artificial, skills disponibles, contrataciones y errores operativos.

El producto presentado sera un prototipo visual e interactivo basado exclusivamente en datos locales. No representara una integracion real con usuarios, pagos, agentes ni sistemas de monitoreo.

### Objetivos visuales

- Transmitir una interfaz empresarial, profesional y confiable.
- Mostrar informacion densa sin sobrecargar al administrador.
- Mantener patrones visuales uniformes en todas las secciones.
- Permitir completar las tareas principales sin recargar la pagina.
- Ser util en escritorio, tablet y movil.

### Fuera de alcance

- Autenticacion real y gestion de permisos.
- Persistencia en servidor, APIs, WebSockets, bases de datos o almacenamiento externo.
- Ejecucion real de agentes o skills.
- Procesamiento real de pagos, cupones o facturacion.
- Generacion real de trazas o graficos a partir de datos remotos.

## 2. Usuario objetivo y alcance

El usuario objetivo es el administrador interno de AgentHub, que debe poder inspeccionar datos, revisar detalles, configurar prompts simulados, eliminar registros visualmente y marcar errores como resueltos.

El alcance comprende seis vistas: Dashboard, Gestion de usuarios, Gestion de agentes, Skills, Contrataciones de agentes y Log de errores.

**Navegacion:** la seleccion de una vista reemplaza el contenido del area principal y conserva el tema claro u oscuro.

**Eliminacion:** eliminar de cualquier lista debe quitar inmediatamente el elemento de los datos locales de esa sesion. Esta accion no solicita confirmacion modal salvo que se indique expresamente un texto propio en el componente correspondiente.

**Persistencia:** ninguna accion persiste al recargar. Al cambiar de seccion se conservaran los datos modificados en memoria mientras la pagina siga abierta. El modo oscuro tambien se conservara al cambiar de seccion y puede conservarse en `localStorage` si se implementa; no es obligatorio.

## 3. Stack y restricciones tecnologicas

### Tecnologias obligatorias

- HTML5 semantico.
- Tailwind CSS cargado mediante CDN.
- JavaScript vanilla.
- Utilidades responsivas y variantes `dark:` de Tailwind.
- Datos hardcodeados en memoria.

### Restricciones

- No se usaran React, Vue, Angular, Svelte ni otros frameworks frontend.
- No se implementara backend, API, base de datos, fetch ni persistencia remota.
- No se crearan archivos CSS personalizados.
- No se usaran atributos `style` inline.
- No se usaran scripts de servidor para representacion o mutacion de datos.
- Se permite una implementacion de un unico `index.html` o varios HTML enlazados. La solucion mas sencilla sera un unico `index.html` con vistas renderizadas por JavaScript.
- Los iconos podran cargarse con una biblioteca compatible mediante CDN o representarse con texto/iconos Unicode. No se exigira una biblioteca concreta.

## 4. Arquitectura de navegacion

### 4.1. Estructura base

La aplicacion tendra una estructura principal con tres zonas:

1. **Sidebar izquierda:** fija en escritorio y oculta o desplazable en movil.
2. **Barra superior:** fija visualmente sobre el area principal y contiene el titulo de la vista activa y el toggle de tema.
3. **Area principal:** ocupa el resto de la pantalla y contiene el contenido de la vista seleccionada.

**NAV-01 — Sidebar persistente**

El sidebar siempre permanecera visible en escritorio a partir de `lg`. Tendra una anchura de `256px`, fondo claro u oscuro segun el tema, borde derecho y posicion fija respecto al viewport.

**NAV-02 — Identidad**

La parte superior mostrara el nombre **AgentHub** y un icono o simbolo representativo. El nombre sera legible y no se reducira a una abreviatura en escritorio.

**NAV-03 — Enlaces de seccion**

El sidebar incluira exactamente seis enlaces en este orden: Dashboard, Usuarios, Agentes, Skills, Contrataciones y Errores. Cada enlace mostrara icono, etiqueta y un area tactil de al menos `40px` de altura.

**NAV-04 — Indicador activo**

La seccion activa tendra fondo distinto, borde izquierdo o peso tipografico elevado segun el sistema visual. Solo una seccion podra estar activa. El titulo de la barra superior debera coincidir exactamente con la etiqueta activa.

**NAV-05 — Navegacion tablet/movil**

Debajo de `lg`, el sidebar se convertira en un menu lateral deslizable abierto mediante un boton de menu en la barra superior. El menu tendra backdrop propio y se cerrara al elegir una seccion, pulsar el boton de cerrar o hacer clic fuera.

**NAV-06 — Cambio de vista**

Al seleccionar una seccion se ocultara el contenido anterior y se renderizara la nueva vista sin recargar. El tema actual se aplicara a la vista nueva y no se reiniciara.

**NAV-07 — Historial visual**

No se implementara navegacion mediante rutas reales ni historial del navegador. El estado activo se mantendra en variables JavaScript durante la sesion.

## 5. Sistema de diseño y responsive

### 5.1. Paleta propuesta

Dado que no se exige una identidad corporativa previa, se usara la siguiente paleta neutral:

- **Fondo claro:** gris muy claro, p. ej. `#F8FAFC` representado con `bg-slate-50`.
- **Superficie clara:** blanco, `bg-white`.
- **Texto principal claro:** gris oscuro, `text-slate-900`.
- **Texto secundario claro:** gris medio, `text-slate-600`.
- **Fondo oscuro:** gris azulado oscuro, p. ej. `bg-slate-950`.
- **Superficie oscura:** gris azulado, p. ej. `bg-slate-900`.
- **Texto principal oscuro:** `text-slate-50`.
- **Texto secundario oscuro:** `text-slate-300`.
- **Acento:** azul, p. ej. `blue-600`, con `blue-500` para estados oscuros o hover.
- **Bordes:** `slate-200` en claro y `slate-700` en oscuro.

**DESIGN-01 — Tipografia**

Se usara la familia sans-serif predeterminada de Tailwind cargada sin archivos CSS propios. El cuerpo tendra `16px` base. Títulos de sección: `24px`, peso `600/700`. Valores destacados de metricas: `30px`, peso `700`. Texto secundario: `14px`.

**DESIGN-02 — Espaciado y radios**

El padding principal sera `24px` en escritorio, `16px` en tablet y `12px` en movil. Los componentes principales usaran radios `12px` o `8px`. Las superficies internas y controles usaran radios `8px`. No se usaran radios excesivos ni pills fuera de badges.

**DESIGN-03 — Bordes y sombras**

Las superficies tendran borde de `1px`, color segun tema, y sombra sutil `shadow-sm`. Los modales podran usar `shadow-xl`. Se evitara la sombra pesada para tablas y contenedores de seccion.

**DESIGN-04 — Iconografia**

Los iconos se usaran para identificar navegacion, metricas y botones de accion. Tendran un contorno lineal consistente y un tamaño de `18px` a `20px`. El boton `⋮` sera visualmente reconocible y tendra un area tactil minima de `40px` cuadradas.

**DESIGN-05 — Estados interactivos**

Los controles tendran:

- Hover: cambio leve de fondo o color sin movimiento.
- Focus: contorno visible de `2px` con color azul y `outline-offset-2`.
- Active: fondo mas oscuro o escala visual minima.
- Disabled: opacidad reducida y cursor no permitido cuando aplique.
- Loading: no existe una carga real; no se mostrara un spinner salvo en una simulacion futura que no forme parte de esta especificacion.

**DESIGN-06 — Layout responsive**

- Escritorio `>=1024px`: sidebar fijo y contenido con ancho disponible.
- Tablet `768px-1023px`: sidebar oculto, barra superior con menu, dos columnas para metricas y tablas con scroll horizontal.
- Movil `<768px`: sidebar como drawer, padding reducido, metricas en una columna, encabezados compactos, tablas con scroll horizontal o tarjetas responsivas segun implementacion.

**DESIGN-07 — Accesibilidad basica**

Todos los botones tendran etiqueta accesible. Las acciones con iconos tendran `aria-label`. Los dropdowns tendran `aria-haspopup="menu"` y `aria-expanded` actualizado. Los modales tendran `role="dialog"`, titulo asociado y foco inicial en el primer cierre o control seguro.

## 6. Dashboard

**DASH-01 — Tarjetas de metricas**

La vista mostrara cuatro tarjetas en una cuadricula. Cada tarjeta tendra icono representativo, etiqueta, valor destacado y fondo de superficie. Tendran borde redondeado, padding uniforme y sombra sutil.

La cuadricula sera de cuatro columnas desde `xl`, dos columnas desde `md` y una columna en movil.

**DASH-02 — Ingresos mensuales**

La primera tarjeta mostrara la etiqueta `Ingresos del mes`, el valor `EUR 48.250` y un icono de moneda o grafico ascendente.

**DASH-03 — Perdidas por descuentos**

La segunda tarjeta mostrara `Perdidas por descuentos` y el valor `EUR 3.120`, con icono de ticket o porcentaje.

**DASH-04 — Agentes activos**

La tercera tarjeta mostrara `Agentes activos` y el valor `3`. Su icono representara estado disponible. El numero coincidirá con los agentes hardcodeados cuyo estado sea activo.

**DASH-05 — Agentes fallando**

La cuarta tarjeta mostrara `Agentes fallando` y el valor `1`. Su icono representara advertencia o error. El numero coincidirá con los agentes cuyo estado sea fallando.

**DASH-06 — Placeholder de actividad semanal**

Debajo de las metricas aparecera un contenedor de ancho completo con altura minima de `260px`, borde solido o discontinuo segun propuesta visual, fondo ligeramente diferenciado y etiqueta centrada `Actividad semanal` o `Grafico de actividad semanal`. No se implementara ningun grafico real. Se mostrara texto auxiliar opcional `Datos de ejemplo`.

**DASH-07 — Reflow responsive**

En escritorio las cuatro tarjetas compartiran una fila con columnas iguales. En tablet tendran dos columnas por dos filas. En movil tendran una tarjeta por fila y el placeholder conservara ancho completo y altura estable.

## 7. Gestion de usuarios

**USER-01 — Tabla de usuarios**

Se mostrara una tabla con cinco usuarios hardcodeados y las columnas: Nombre, Email, Plan y Estado. Tambien tendra una columna de Acciones de ancho fijo.

**USER-02 — Presentacion de filas**

Cada fila tendra altura suficiente para lectura, separadores horizontales, hover con fondo leve y textos alineados. El nombre podra incluir avatar con iniciales. El email sera texto secundario legible y no interactivo.

**USER-03 — Badge de estado**

El estado sera `Activo` o `Suspendido`. Activo usara fondo verde claro y texto verde oscuro en claro; en oscuro usara variantes adecuadas. Suspendido usara rojo claro y rojo oscuro.

**USER-04 — Dropdown de acciones**

Cada fila tendra un boton `⋮` con area tactil minima. El menu tendra las opciones `Ver detalle` y `Eliminar`, alineadas a la derecha de la fila. Solo un dropdown podra estar abierto a la vez.

**USER-05 — Detalle de usuario**

Al elegir `Ver detalle`, se abrira un modal que muestre Nombre, Email, Plan, Estado, ID de usuario, fecha de registro y numero de agentes asociados. El usuario seleccionado sera el unico contenido mostrado.

**USER-06 — Cierre de detalle**

El modal se cerrara con un boton `Cerrar` con icono `X`, al pulsar Escape si se implementa y al hacer clic fuera del panel sobre el backdrop. Un clic dentro del modal no lo cerrara.

**USER-07 — Eliminacion simulada**

Al elegir `Eliminar`, la fila se quitara inmediatamente de la tabla y de los datos locales. Si el usuario posee agentes, esos agentes quedaran visibles sin cambios en el prototipo o podran mostrar `Sin propietario asignado` solo si el desarrollador decide implementar esa derivacion. Para evitar contradicciones, se propone que la eliminacion conserve los agentes existentes y muestre su propietario actual mediante el nombre hardcodeado, sin recalcular relaciones.

**USER-08 — Estado vacio**

Si se eliminan los cinco usuarios, se mostrara una fila o contenedor con el texto `No hay usuarios disponibles` y un boton visualmente secundario `Restaurar datos` que no sera obligatorio; si existe, restaurara los datos iniciales de esa vista.

## 8. Gestion de agentes

**AGENT-01 — Listado de agentes**

Se mostrara una lista o cuadricula con al menos cuatro agentes. Cada registro tendra Nombre, Propietario, Estado, badge de estado, lista colapsable de skills y dropdown de acciones.

**AGENT-02 — Disposicion de tarjeta**

Cada agente sera una fila o tarjeta con cabecera identificable. En escritorio podra presentarse como fila dentro de un contenedor con columnas; en movil se apilara Nombre/Propietario/Estado y controles.

**AGENT-03 — Estados de agente**

Los estados permitidos seran `Activo`, `Inactivo` y `Fallando`. Activo usara verde; Inactivo usara gris; Fallando usara rojo. El badge tendra el texto exacto del estado.

**AGENT-04 — Skills colapsables**

El nombre de skills del agente tendra un control expandible con texto `Skills` y un icono de flecha. Inicialmente todas las listas se cerraran. Al pulsar se expandiran con una transicion suave de altura/opacidad y mostraran las skills asociadas.

**AGENT-05 — Segundo pulsacion**

Al volver a pulsar el mismo control, la lista se colapsara con la misma transicion. El icono se girara desde cerrado a expandido y de vuelta. Solo el elemento pulsado cambia; no se necesita acordion exclusivo.

**AGENT-06 — Dropdown de acciones**

El dropdown tendra exactamente las opciones `Configurar` y `Eliminar`.

**AGENT-07 — Modal de configuracion**

Al elegir `Configurar`, se abrira un modal cuyo titulo sera `Configurar {nombre del agente}` y un campo `<textarea>` editable con el prompt de sistema actual.

**AGENT-08 — Edicion y guardado**

El textarea permitira seleccionar y modificar todo el texto. El modal tendra botones `Cancelar` y `Guardar`. Cancelar cerrara sin aplicar cambios locales. Guardar actualizara el prompt del agente en memoria y cerrara el modal, mostrando visualmente que se guardo si se decide incluir un toast local.

**AGENT-09 — Eliminacion simulada**

Al elegir `Eliminar`, el agente desaparecerá de la lista local. Los contratos que lo referencien pueden seguir mostrando su nombre hardcodeado para representar datos históricos. Los contadores de skills deberan recalcularse visualmente al eliminar el agente si esa implementacion esta activa.

**AGENT-10 — Estado vacio**

Si no quedan agentes, se mostrara `No hay agentes disponibles` y se mantendra el encabezado de la seccion.

## 9. Skills

**SKILL-01 — Catalogo explicativo**

La seccion mostrara un bloque superior explicando: `Una skill es una capacidad configurada que amplía las acciones de un agente, como navegar por la web, leer documentos, gestionar calendarios o automatizar tareas.`

**SKILL-02 — Presentacion del catalogo**

Habrá al menos cuatro skills presentadas como tarjetas o filas. Cada registro mostrara Nombre, Descripcion breve y numero de agentes con la skill habilitada.

**SKILL-03 — Contadores consistentes**

Los contadores se calcularan o confirmaran a partir del modelo hardcodeado: Navegacion web usada por 3 agentes, Lectura de documentos usada por 2, Gestion de calendario usada por 2 y Automatizacion usada por 1.

**SKILL-04 — Acciones de skill**

Cada registro tendra un dropdown con `Ver detalle` y `Eliminar`.

**SKILL-05 — Modal de detalle**

Ver detalle abrirá un modal con Nombre, descripcion completa, icono, numero de agentes habilitados y una lista de nombres de esos agentes.

**SKILL-06 — Eliminacion simulada**

Eliminar quitara la skill del catalogo local y la retirara visualmente de las listas de agentes y contratos. Los datos existentes pueden conservar el nombre historico en contratos para evitar una inconsistencia temporal, pero el contador y el catálogo se actualizaran de forma inmediata.

**SKILL-07 — Estado vacio**

Si se eliminan todas las skills, se mostrara `No hay skills disponibles` dentro del catalogo.

## 10. Contrataciones de agentes

**CONTRACT-01 — Tabla de contratos**

Se mostrara una tabla con al menos cuatro contratos. Las columnas seran Cliente, Agente alquilado, Skills contratadas, Inicio, Finalizacion, Importe total y Acciones.

**CONTRACT-02 — Presentacion compacta**

Las skills contratadas podran mostrarse como un texto separado por comas o como badges compactos. En movil se permitira scroll horizontal para conservar las fechas y importes legibles.

**CONTRACT-03 — Montos coherentes**

Cada contrato mostrara importes derivados de sus skills mas una tarifa base o mensual. Los importes individuales sumaran exactamente el importe total mostrado.

**CONTRACT-04 — Acciones**

Cada fila tendra un dropdown con al menos `Ver detalle`.

**CONTRACT-05 — Modal de detalle**

Al elegir Ver detalle se abrira un modal con Cliente, Agente, ID del contrato, fechas, estado de contrato si existe y una tabla de desglose economico.

**CONTRACT-06 — Desglose economico**

El desglose mostrara cada skill contratada y su precio individual, luego un subtotal y el importe total pagado. Los totales podran expresarse en EUR. El total sera igual a la suma de los precios.

**CONTRACT-07 — Cierre del modal**

El modal se cerrara mediante `Cerrar`, Escape si se implementa o clic sobre el backdrop. El contenido interno no cerrara el modal.

**CONTRACT-08 — Actualizacion local**

No existira accion de crear o eliminar contratos en el alcance principal. Si se implementa un dropdown adicional, no podra introducir datos ni acciones no especificadas.

## 11. Log de errores

**ERROR-01 — Registro de errores**

Se mostrara un listado con seis entradas hardcodeadas. Cada entrada mostrara Timestamp, Agente, Tipo, Descripcion breve, Estado visual y Acciones.

**ERROR-02 — Tipos con color**

Los tipos permitidos seran `Critico`, `Advertencia` e `Informativo`. Critico usara rojo, Advertencia usara amarillo/anaranjado e Informativo usara azul. Cada entrada tendra un badge legible con el texto exacto del tipo.

**ERROR-03 — Estado resuelto**

Cada error tendra un estado interno `Pendiente` o `Resuelto`. El estado inicial sera Pendiente salvo que el dato lo indique de otro modo. El estado se mostrara mediante texto secundario o badge adicional.

**ERROR-04 — Dropdown de acciones**

El dropdown tendra las opciones `Ver detalle` y `Marcar como resuelto`. La opcion quedara deshabilitada visualmente si el error ya esta resuelto.

**ERROR-05 — Modal de traza**

Ver detalle abrirá un modal con Timestamp, Agente, Tipo, Severidad, Descripcion completa, identificador de error y una traza completa presentada en un bloque monoespaciado sin agregar estilos inline.

**ERROR-06 — Marcar como resuelto**

Al seleccionar `Marcar como resuelto`, el estado local del registro cambiara a Resuelto, el badge o texto se actualizara inmediatamente y la opcion se deshabilitara para ese registro.

**ERROR-07 — Accion visual**

La fila resuelta podra mostrar una marca de comprobacion y una opacidad leve, pero conservara todos los datos visibles. No se eliminara del registro.

**ERROR-08 — Estado vacio**

No se aplicara estado vacio porque el prototipo siempre conservara los seis registros iniciales al cargar, aun si se marcan como resueltos.

## 12. Inventario de componentes reutilizables

**COMP-01 — Sidebar**

- Propósito: navegacion principal entre las seis secciones.
- Estructura: contenedor, marca, lista de enlaces y estado activo.
- Variantes: fijo escritorio y drawer movil.
- Estados: cerrado, abierto, activo, hover y focus.
- Uso: visible en todas las vistas.
- Responsive: fijo desde `lg`; drawer debajo de `lg`.

**COMP-02 — Barra superior**

- Propósito: identificar la vista actual y exponer acciones globales.
- Estructura: boton de menu movil, titulo de seccion y toggle de tema.
- Estados: normal y drawer abierto.
- Uso: visible en todas las vistas.
- Responsive: titulo compacto en movil y menu disponible debajo de `lg`.

**COMP-03 — Tarjeta de metrica**

- Propósito: presentar una KPI breve.
- Contenido: icono, etiqueta y valor destacado.
- Estados: hover opcional, normal y tema claro/oscuro.
- Uso: Dashboard exclusivamente.
- Responsive: cuatro, dos o una columna segun viewport.

**COMP-04 — Tabla de datos**

- Propósito: presentar usuarios y contratos de forma escaneable.
- Contenido: encabezado semántico, filas, separadores y acciones.
- Estados: hover, vacio y con dropdown abierto.
- Uso: Usuarios y Contrataciones.
- Responsive: scroll horizontal en anchos insuficientes.

**COMP-05 — Dropdown de acciones**

- Propósito: agrupar acciones contextuales.
- Contenido: boton `⋮` y menu de opciones.
- Estados: cerrado, abierto, hover de opcion, focus y accion deshabilitada.
- Uso: Usuarios, Agentes, Skills, Contratos y Errores.
- Responsive: el menu se alineara dentro del viewport y se cerrara al abrir otro menu.

**COMP-06 — Modal overlay**

- Propósito: mostrar detalles o editar el prompt sin abandonar la vista.
- Contenido: encabezado, cuerpo, acciones y backdrop.
- Estados: cerrado, abierto y contencion de focus.
- Uso: todas las secciones que requieren detalle o configuracion.
- Responsive: ancho completo con margenes en movil y anchura limitada en escritorio.

**COMP-07 — Badge de estado**

- Propósito: comunicar estados breves con color y texto.
- Variantes: activo verde, inactivo gris, fallando rojo, suspendido rojo, critico rojo, advertencia amarillo/anaranjado e informativo azul.
- Estados: normal y claro/oscuro.
- Uso: Usuarios, Agentes y Errores.

**COMP-08 — Lista de skills colapsable**

- Propósito: mostrar skills sin expandir el diseño por defecto.
- Contenido: control con etiqueta y flecha; grupo de nombres al expandir.
- Estados: cerrado, expandiendo, abierto y colapsando.
- Uso: Gestion de agentes y, opcionalmente, dentro de contratos como resolucion visual.
- Responsive: ancho completo en movil.

**COMP-09 — Toggle de modo oscuro**

- Propósito: alternar todo el panel entre claro y oscuro.
- Contenido: iconos de sol/luna y control toggle.
- Estados: claro, oscuro y focus.
- Comportamiento: aplica o elimina la clase `dark` sobre el elemento raiz.
- Uso: barra superior en todas las vistas.

**COMP-10 — Botones y controles de cierre**

- Propósito: ejecutar acciones y cerrar superficies.
- Variantes: primario azul, secundario neutro, peligro rojo y cerrar con icono `X`.
- Estados: normal, hover, focus, active y disabled.
- Uso: modales, drawer, dropdowns y confirmaciones futuras.

## 13. Interacciones globales y estados

**GLOBAL-01 — Navegacion**

Al seleccionar una seccion, el titulo y el indicador activo cambiaran a la seccion correspondiente. El tema no cambiará ni se reiniciara.

**GLOBAL-02 — Apertura de dropdown**

Cada boton `⋮` abrirá su menu junto al boton. El menu tendra posicion relativa que evite desbordarse fuera del viewport. Un segundo clic sobre el mismo boton cerrara el menu.

**GLOBAL-03 — Cierre por clic externo**

Cualquier clic fuera de un dropdown abierto lo cerrara. Al abrir otro dropdown, el primero se cerrara y el nuevo se abrira.

**GLOBAL-04 — Ejecucion de opcion**

Seleccionar una opcion ejecutara su accion inmediatamente. El dropdown se cerrara antes de abrir el modal o modificar el registro.

**GLOBAL-05 — Apertura de modal**

Al abrir un modal, se mostrara un overlay semitransparente sobre toda la pantalla y un panel centrado por encima. El body podra bloquear scroll. El registro seleccionado determinara el contenido.

**GLOBAL-06 — Cierre de modal**

Cerrara mediante boton de cierre, backdrop y Escape si se implementa. Los clics dentro del panel no cerraran el modal.

**GLOBAL-07 — Colapsable**

Los colapsables conservaran altura cero cuando esten cerrados y se mostraran con una transicion de `200ms` a `300ms`. No usaran cambios bruscos de posicion ni desplazaran otros controles fuera de forma inesperada.

**GLOBAL-08 — Modo oscuro**

El toggle cambiara de claro a oscuro y viceversa aplicando variantes `dark:` a superficies, textos y bordes. Se conservara al navegar entre secciones. Se podra usar `localStorage` para conservarlo entre recargas; en su ausencia solo se conserva en memoria.

**GLOBAL-09 — Eliminacion**

Eliminar quitara el elemento seleccionado de su coleccion local sin llamada a servidor. Esta accion sera reversible solo si se implementa restauracion local; no se mostrara un modal de confirmacion obligatorio.

**GLOBAL-10 — Guardado de prompt**

Guardar reemplazara el prompt del agente seleccionado en memoria, cerrara el modal y no realizara peticiones. Cancelar descartara los cambios sin modificar el prompt original.

**GLOBAL-11 — Resolucion de error**

Marcar como resuelto cambiara el estado local y actualizará badges y controles sin recargar ni invocar APIs.

**GLOBAL-12 — Escape y foco**

Cuando se implemente Escape, cerrara dropdown o modal. Al cerrar un modal, el foco volverá al elemento que lo abrió si el navegador lo permite.

## 14. Modelo de datos hardcodeados

### 14.1. Usuarios

Campos: `id`, `name`, `email`, `plan`, `status`, `registeredAt`, `agentIds`.

| id | name | email | plan | status | registeredAt | agentIds |
|---|---|---|---|---|---|---|
| usr-001 | Marta Ruiz | marta@northstar.io | Empresa | Activo | 2025-01-14 | agt-001, agt-004 |
| usr-002 | Daniel Vega | daniel@lumina.es | Profesional | Activo | 2025-02-03 | agt-002 |
| usr-003 | Lucia Torres | lucia@verde.tech | Profesional | Activo | 2025-03-19 | agt-003 |
| usr-004 | Carlos Mendez | carlos@atlas.co | Basico | Suspendido | 2025-04-08 | ningun agente |
| usr-005 | Elena Soto | elena@orionlabs.es | Empresa | Activo | 2025-05-21 | ningun agente |

### 14.2. Agentes

Campos: `id`, `name`, `ownerId`, `ownerName`, `status`, `skills`, `systemPrompt`.

| id | name | ownerId | ownerName | status | skills | systemPrompt |
|---|---|---|---|---|---|---|
| agt-001 | Atlas Research | usr-001 | Marta Ruiz | Activo | Navegacion web, Lectura de documentos, Gestion de calendario | Eres un agente de investigacion que usa fuentes verificables y devuelve resumenes claros. |
| agt-002 | Orion Support | usr-002 | Daniel Vega | Fallando | Navegacion web, Automatizacion | Eres un agente de soporte que sigue procedimientos internos y escala incidencias ambiguas. |
| agt-003 | Lumina Scheduler | usr-003 | Lucia Torres | Activo | Lectura de documentos, Gestion de calendario | Eres un agente que organiza reuniones y valida conflictos de disponibilidad. |
| agt-004 | Northstar Operations | usr-001 | Marta Ruiz | Activo | Navegacion web | Eres un agente operativo que monitorea tareas y automatiza flujos aprobados. |

Los agentes fallando seran exactamente uno. Los agentes activos seran exactamente tres. Los agentes inactivos no existen en el conjunto inicial; el estado Inactivo seguirá disponible para datos futuros o eliminacion/restauracion.

### 14.3. Skills

Campos: `id`, `name`, `description`, `enabledAgentIds`, `iconKey`.

| id | name | description | enabledAgentIds | enabledCount |
|---|---|---|---|---|
| skl-001 | Navegacion web | Busca informacion, navega paginas y extrae datos publicos de forma controlada. | agt-001, agt-002, agt-004 | 3 |
| skl-002 | Lectura de documentos | Lee archivos, resume documentos y extrae campos relevantes. | agt-001, agt-003 | 2 |
| skl-003 | Gestion de calendario | Consulta disponibilidad y administra eventos dentro de calendarios autorizados. | agt-001, agt-003 | 2 |
| skl-004 | Automatizacion | Ejecuta tareas repetibles y flujos definidos por el administrador. | agt-002 | 1 |

### 14.4. Contratos

Campos: `id`, `clientName`, `agentId`, `agentName`, `skillIds`, `skillNames`, `startDate`, `endDate`, `status`, `breakdown`, `total`.

| id | clientName | agentId / agentName | skills | startDate | endDate | total EUR |
|---|---|---|---|---|---|---|
| con-001 | Northstar S.A. | agt-001 / Atlas Research | Navegacion web EUR 300, Lectura de documentos EUR 250, Gestion de calendario EUR 200 | 2026-01-01 | 2026-03-31 | 750 |
| con-002 | Lumina Studio | agt-002 / Orion Support | Navegacion web EUR 300, Automatizacion EUR 350 | 2026-02-01 | 2026-04-30 | 650 |
| con-003 | Verde Tecnologias | agt-003 / Lumina Scheduler | Lectura de documentos EUR 250, Gestion de calendario EUR 200 | 2026-03-01 | 2026-05-31 | 450 |
| con-004 | Orion Labs | agt-004 / Northstar Operations | Navegacion web EUR 300 | 2026-04-01 | 2026-06-30 | 300 |

Los precios individuales no incluyen IVA ni cargos adicionales. El importe total sera igual a la suma exacta de las skills mostradas.

### 14.5. Errores

Campos: `id`, `timestamp`, `agentId`, `agentName`, `type`, `severity`, `briefDescription`, `trace`, `status`.

| id | timestamp | agentName | type | briefDescription | status |
|---|---|---|---|---|---|
| err-001 | 2026-11-21 09:42:18 | Orion Support | Critico | Timeout al ejecutar el flujo de automatizacion. | Pendiente |
| err-002 | 2026-11-21 09:38:03 | Atlas Research | Advertencia | La fuente externa devolvio una respuesta incompleta. | Pendiente |
| err-003 | 2026-11-21 09:15:44 | Lumina Scheduler | Informativo | Reintento completado al consultar disponibilidad. | Resuelto |
| err-004 | 2026-11-21 08:57:20 | Northstar Operations | Advertencia | Limite de solicitudes alcanzado temporalmente. | Pendiente |
| err-005 | 2026-11-21 08:31:09 | Orion Support | Critico | Fallo de autenticacion al usar una conexion aprobada. | Pendiente |
| err-006 | 2026-11-20 18:22:51 | Atlas Research | Informativo | Sesion de navegacion cerrada correctamente. | Resuelto |

Cada error tendra una traza completa ficticia asociada a su agente. La traza sera texto plano presentado con formato monoespaciado y no ejecutara contenido.

### 14.6. Metricas derivadas

| metricKey | label | value | coherenceRule |
|---|---|---|---|
| revenueMonth | Ingresos del mes | EUR 48.250 | Valor mensual fijo de ejemplo, superior al total de los cuatro contratos mostrados por representar ingresos agregados de todo el mes. |
| discountLoss | Perdidas por descuentos | EUR 3.120 | Valor fijo mensual de cupones y descuentos aplicados. |
| activeAgents | Agentes activos | 3 | Contar agentes con status `Activo`. |
| failingAgents | Agentes fallando | 1 | Contar agentes con status `Fallando`. |

## 15. Criterios de aceptacion

1. **NAVEGACION-01:** existen las seis vistas y al seleccionarlas el area principal cambia sin recargar, con el indicador activo coincidente. Se valida con NAV-01 a NAV-07.
2. **DASH-01:** Dashboard muestra exactamente cuatro tarjetas con ingresos, descuentos, agentes activos y agentes fallando, mas el placeholder de actividad semanal. Se valida con DASH-01 a DASH-07.
3. **USER-01:** Gestion de usuarios muestra al menos cinco filas con Nombre, Email, Plan y Estado. Se valida con USER-01 a USER-03.
4. **USER-02:** cada fila de usuario contiene el dropdown con Ver detalle y Eliminar. Se valida con USER-04.
5. **USER-03:** Ver detalle abre el modal del usuario seleccionado y Eliminar lo retira inmediatamente. Se valida con USER-05 y USER-07.
6. **USER-04:** el modal de usuario cierra por boton y backdrop y el clic interno no lo cierra. Se valida con USER-06 y GLOBAL-06.
7. **AGENT-01:** Gestion de agentes muestra al menos cuatro agentes con propietario, estado y skills. Se valida con AGENT-01 a AGENT-03.
8. **AGENT-02:** las cuatro skills colapsables inician cerradas y cada una se abre y cierra mediante transicion al pulsar su control. Se valida con AGENT-04, AGENT-05 y GLOBAL-07.
9. **AGENT-03:** Configurar abre un modal con el prompt del agente dentro de un textarea editable. Se valida con AGENT-07.
10. **AGENT-04:** Guardar cambia el prompt local y cerrar sin guardar descarta la edicion. Se valida con AGENT-08 y GLOBAL-10.
11. **AGENT-05:** Eliminar retira el agente seleccionado de la lista local. Se valida con AGENT-09.
12. **SKILL-01:** Skills incluye el bloque explicativo y al menos cuatro skills con descripcion y contador. Se valida con SKILL-01 a SKILL-03.
13. **SKILL-02:** Ver detalle muestra la informacion completa y Eliminar retira la skill localmente. Se valida con SKILL-04 a SKILL-06.
14. **CONTRACT-01:** Contrataciones muestra al menos cuatro contratos con todas las columnas requeridas. Se valida con CONTRACT-01 y CONTRACT-02.
15. **CONTRACT-02:** cada total es igual a la suma de sus precios individuales y el modal muestra el desglose completo. Se valida con CONTRACT-03 y CONTRACT-06.
16. **CONTRACT-03:** Ver detalle abre el contrato correcto y el modal cierra por boton y backdrop. Se valida con CONTRACT-05 y CONTRACT-07.
17. **ERROR-01:** Log de errores muestra al menos seis registros con timestamp, agente, tipo, descripcion y estado. Se valida con ERROR-01 a ERROR-03.
18. **ERROR-02:** los colores y textos de Critico, Advertencia e Informativo son distinguibles. Se valida con ERROR-02.
19. **ERROR-03:** Ver detalle abre la traza completa del error correspondiente. Se valida con ERROR-05.
20. **ERROR-04:** Marcar como resuelto cambia inmediatamente el estado visual y deshabilita la accion para ese registro. Se valida con ERROR-04, ERROR-06 y ERROR-07.
21. **INTER-01:** al abrir un dropdown se cierran los otros menus abiertos y hacer clic fuera lo cierra. Se valida con GLOBAL-02 y GLOBAL-03.
22. **INTER-02:** seleccionar una opcion ejecuta su accion asociada y el menu se cierra antes del cambio. Se valida con GLOBAL-04.
23. **MODAL-01:** todos los modales bloquean visualmente el fondo con un overlay, muestran el registro correcto y cierran por boton/backdrop. Se valida con GLOBAL-05 y GLOBAL-06.
24. **THEME-01:** el toggle cambia toda la interfaz entre claro y oscuro mediante variantes `dark:`. Se valida con COMP-09 y GLOBAL-08.
25. **THEME-02:** el tema permanece seleccionado al navegar entre secciones y al cambiar entre modales y vistas. Se valida con NAV-06 y GLOBAL-08.
26. **RESP-01:** escritorio mantiene sidebar fijo y cuadricula de metricas en cuatro columnas. Se valida con NAV-01 y DESIGN-06.
27. **RESP-02:** tablet usa sidebar movil o drawer y metricas en dos columnas. Se valida con NAV-05 y DASH-07.
28. **RESP-03:** movil usa una columna para metricas, controles tactiles y drawer sin desbordamientos horizontales. Se valida con DESIGN-06 y NAV-05.
29. **STACK-01:** la implementacion usa HTML5, Tailwind CDN y JavaScript vanilla. Se valida con la seccion 3.
30. **STACK-02:** no existen archivos CSS personalizados, atributos style ni frameworks frontend. Se valida con la seccion 3.
31. **DATA-01:** no existen llamadas a APIs ni backend y todas las acciones modifican unicamente datos locales de la pagina. Se valida con GLOBAL-09 a GLOBAL-11.
32. **DATA-02:** las relaciones entre usuarios, agentes, skills, contratos y errores son coherentes con el modelo de datos. Se valida con la seccion 14.
33. **A11Y-01:** botones, dropdowns y modales tienen estados de focus y etiquetas accesibles basicas. Se valida con DESIGN-07 y COMP-05 a COMP-10.
34. **EMPTY-01:** no quedan elementos de datos sin un estado vacio definido donde corresponde. Se valida con USER-08, AGENT-10 y SKILL-07.

## 16. Validacion final de especificacion

- Las seis secciones estan cubiertas con requisitos identificables.
- Cada seccion contiene al menos tres requisitos concretos y verificables.
- Todos los componentes reutilizables solicitados estan definidos.
- Las interacciones globales incluyen navegación, dropdown, modal, colapsable y tema.
- Los estados iniciales, acciones locales y transiciones estan documentados.
- El modelo contiene cinco usuarios, cuatro agentes, cuatro skills, cuatro contratos, seis errores y cuatro metricas.
- Las relaciones entre entidades son coherentes.
- La especificacion cumple HTML5, Tailwind CDN, JavaScript vanilla y ausencia de backend.
- No se especifica ningun archivo CSS personalizado ni estilo inline.
