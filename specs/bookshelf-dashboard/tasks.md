# Tareas verificables: Panel administrativo AgentHub

## Integración visual

- [x] Crear `index.html` con la estructura base HTML, idioma español y viewport responsivo.
- [x] Cargar Tailwind CSS mediante CDN y configurar el modo oscuro por clase `dark`.
- [x] Cargar las tipografías Red Hat Text, Instrument Sans y Red Hat Mono acordes con `DESIGN.md`.
- [x] Añadir el sidebar fijo de 256 px con marca, navegación, perfil y contador de errores.
- [x] Añadir la barra superior de 64 px con título de sección, indicador de entorno y toggle de tema.
- [x] Reutilizar superficies, bordes, radios, espaciado y estados semánticos de las referencias Stitch.
- [x] Evitar CSS personalizado, bloques `<style>` y atributos `style`; usar solo utilidades Tailwind.
- [x] Verificar que el shell ocupa `100vh` y no usa alturas fijas heredadas de las maquetas.

## Contenido: bloque 1

### Dashboard

- [x] Renderizar una tarjeta para ingresos totales del mes.
- [x] Renderizar una tarjeta para pérdida por descuentos y cupones.
- [x] Renderizar una tarjeta para agentes activos.
- [x] Renderizar una tarjeta para agentes fallando.
- [x] Añadir debajo el placeholder visual de actividad semanal con los siete días.
- [x] Confirmar que las métricas son datos hardcodeados y no contienen acciones falsas.

### Usuarios

- [x] Renderizar una tabla con nombre, email, plan y estado.
- [x] Añadir al menos cinco usuarios representativos con estados activo e inactivo.
- [x] Añadir un botón `⋮` por fila con `aria-haspopup="menu"` y `aria-expanded`.
- [x] Mostrar las opciones Ver detalle y Eliminar en cada menú.
- [x] Implementar un modal que muestre el registro completo del usuario seleccionado.
- [x] Confirmar que Eliminar no modifica ni elimina registros.

### Agentes

- [x] Renderizar seis agentes representativos con nombre, propietario y estado.
- [x] Mostrar los estados activo, inactivo y fallando con badges semánticos.
- [x] Mantener las skills ocultas al cargar la página.
- [x] Añadir por agente un control expandible con transición suave.
- [x] Añadir menú `⋮` con Configurar y Eliminar.
- [x] Implementar el modal de Configurar con el prompt de sistema completo.
- [x] Confirmar que Eliminar no modifica ni elimina registros.

## Contenido: bloque 2

### Skills

- [x] Renderizar el catálogo de skills en cards reutilizando el diseño Stitch.
- [x] Mostrar nombre, descripción, tarifa o precio y cantidad de agentes habilitados.
- [x] Añadir una explicación breve sobre qué significa una skill en AgentHub.
- [x] Añadir menú `⋮` con Ver detalle y Eliminar.
- [x] Implementar el modal con nombre, descripción, permisos, precio y agentes vinculados.
- [x] Confirmar que Eliminar no modifica ni elimina cards.

### Contrataciones

- [x] Renderizar una tabla de contratos activos y pasados.
- [x] Mostrar cliente, agente alquilado, skills contratadas, fechas, importe y estado.
- [x] Añadir menú `⋮` por contrato con Ver detalle, Marcar como devuelto y Eliminar.
- [x] Implementar el modal de desglose con licencia base, skills individuales, descuento y total.
- [x] Confirmar que Marcar como devuelto y Eliminar no modifican contratos.

### Log de errores

- [x] Renderizar una tabla con timestamp, agente, tipo, descripción, estado y acciones.
- [x] Diferenciar visualmente errores críticos y advertencias mediante badges.
- [x] Añadir menú `⋮` con Ver detalle y Marcar como resuelto.
- [x] Implementar el modal con el timestamp, agente e identificador y la traza completa.
- [x] Cambiar la entrada seleccionada a Resuelto al ejecutar Marcar como resuelto.
- [x] Actualizar el contador de errores abiertos del sidebar después de resolver entradas.

## Navegación

- [x] Representar las seis secciones como paneles internos de `index.html`.
- [x] Conectar los controles del sidebar a cambios de sección sin recargar.
- [x] Cambiar el título superior según la sección activa.
- [x] Aplicar `aria-current="page"` al elemento activo del sidebar.
- [x] Mantener la navegación activa al cambiar el tema o resolver un error.
- [x] Mostrar el sidebar fijo a partir de `lg`.
- [x] Mostrar un botón móvil y convertir el sidebar en drawer debajo de `lg`.
- [x] Permitir cerrar el drawer al navegar a otra sección.

## Dropdowns

- [x] Crear una función común para abrir, cerrar y alternar menús `⋮`.
- [x] Mantener solo un menú abierto a la vez.
- [x] Actualizar `aria-expanded` al abrir y cerrar cada menú.
- [x] Cerrar el menú al seleccionar una opción.
- [x] Cerrar los menús al hacer clic fuera.
- [x] Cerrar los menús al pulsar Escape.
- [x] Mantener menús dentro de tablas sin recortar opciones innecesariamente.

## Modales

- [x] Crear una plantilla común para backdrop, cabecera, cuerpo y pie.
- [x] Implementar cierre por botón de cabecera y botón de pie.
- [x] Implementar cierre al hacer clic en el backdrop.
- [x] Implementar cierre con Escape.
- [x] Enfocar el botón de cierre al abrir cada modal.
- [x] Devolver el foco al control que abrió el modal al cerrarlo.
- [x] Bloquear el scroll del fondo mientras un modal esté abierto.
- [x] Añadir una trampa básica de foco dentro del modal abierto.
- [x] Etiquetar cada diálogo con `role="dialog"`, `aria-modal="true"` y título asociado.

## Modo oscuro

- [x] Leer `agenthub-theme` desde `localStorage` antes de cargar la interfaz visible.
- [x] Aplicar la clase `dark` al elemento raíz cuando el tema guardado sea oscuro.
- [x] Alternar la clase `dark` desde el toggle superior.
- [x] Guardar `light` o `dark` en `localStorage` al cambiar el tema.
- [x] Verificar variantes `dark:` en sidebar, top bar, cards, tablas, badges y modales.
- [x] Mantener el panel activo después de cambiar el tema.
- [ ] Respetar `prefers-reduced-motion` en transiciones visuales.

## Verificación final

- [x] Confirmar que existe un único archivo de implementación: `index.html`.
- [x] Confirmar que no existe CSS personalizado ni atributos `style` en `index.html`.
- [x] Confirmar que no hay framework de UI ni proceso de build.
- [ ] Abrir el panel en una resolución de escritorio de al menos 1280 px.
- [ ] Navegar y comprobar las seis secciones sin recargar ni cambiar de URL.
- [x] Verificar que las cuatro métricas y el placeholder semanal están visibles en Dashboard.
- [ ] Abrir y cerrar el modal de al menos un usuario mediante botón y backdrop.
- [ ] Abrir el prompt de al menos un agente y verificar que empieza contraído el panel de skills.
- [ ] Expandir y contraer al menos un agente con transición.
- [ ] Abrir y cerrar el detalle de al menos una skill.
- [ ] Verificar el desglose completo de al menos una contratación activa.
- [ ] Abrir la traza de al menos un error.
- [ ] Resolver al menos un error y confirmar el cambio de badge y contador.
- [ ] Cambiar a modo oscuro y recargar para comprobar persistencia.
- [x] Comprobar que Eliminar y Marcar como devuelto no alteran datos.
- [ ] Abrir el panel a un ancho móvil estrecho y comprobar que las tablas pueden desplazarse y el drawer es utilizable.
- [ ] Revisar la consola del navegador y confirmar que no existen errores JavaScript ni recursos obligatorios inexistentes.
