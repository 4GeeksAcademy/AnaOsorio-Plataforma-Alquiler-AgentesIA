# Especificación: Panel administrativo AgentHub

## Objetivo

Definir un panel administrativo de AgentHub que permita consultar usuarios, agentes, skills, contrataciones y errores desde una sola interfaz. La implementación posterior será una página de escritorio prioritaria con datos de muestra y comportamiento cliente.

## Alcance y restricciones

- La aplicación se entrega en un único `index.html`.
- No se utilizan frameworks de interfaz ni herramientas de build. Las interacciones se implementan con JavaScript nativo.
- Tailwind CSS v4 se carga mediante su CDN oficial para usar utilidades, incluidas las variantes `dark:`. El CDN requiere conexión externa.
- No se añade CSS personalizado, bloques `<style>` ni atributos `style`.
- Todos los datos son hardcodeados. No hay backend, autenticación, llamadas de API ni persistencia de cambios de negocio.
- La experiencia se optimiza para escritorio; en pantallas estrechas el contenido debe seguir siendo utilizable, aunque no sea el foco principal.

## Estructura persistente

- Una barra lateral permanece visible al cambiar de sección y da acceso a Dashboard, Usuarios, Agentes, Skills, Contrataciones y Log de errores.
- La sección seleccionada se indica visualmente y su contenido se muestra en el área principal sin navegar a otra página.
- La barra superior incluye un control para alternar toda la interfaz entre tema claro y oscuro. El tema oscuro usa las utilidades `dark:` de Tailwind.
- El tema seleccionado se conserva en `localStorage` y se aplica al cargar la página.

## Secciones

### 1. Dashboard

Mostrar cuatro tarjetas de métricas:

- Ingresos totales generados durante el mes actual.
- Pérdida total por descuentos y cupones.
- Número de agentes activos en todos los clientes.
- Número de agentes actualmente marcados como fallando.

Debajo de las métricas, incluir un área de marcador de posición para el gráfico de actividad semanal. No se requiere una librería ni un gráfico funcional.

### 2. Gestión de usuarios

Mostrar una tabla con todos los usuarios de muestra y las columnas nombre, email, plan y estado. Cada fila tiene un menú de acciones activado por un botón `⋮` con las opciones:

- **Ver detalle:** abre un modal con el registro completo del usuario.
- **Eliminar:** la opción puede mostrarse, pero no ejecuta ninguna acción.

El modal se cierra con su botón de cierre o al hacer clic en el backdrop.

### 3. Gestión de agentes

Mostrar todos los agentes de muestra con nombre, propietario, estado actual (activo, inactivo o fallando) y sus skills asociadas. Las skills aparecen contraídas por defecto. Un control por agente las expande y contrae con una transición suave.

Cada agente tiene un menú de acciones:

- **Configurar:** abre un modal que muestra el prompt de sistema completo del agente.
- **Eliminar:** la opción puede mostrarse, pero no ejecuta ninguna acción.

### 4. Skills

Mostrar el catálogo de skills disponibles. Cada skill incluye nombre, descripción breve y cantidad de agentes que la tienen habilitada. La sección incluye una explicación breve de que una skill es una capacidad que se puede adjuntar a un agente.

Cada skill tiene un menú de acciones con **Ver detalle** y **Eliminar**. El detalle muestra la información completa disponible para esa skill; eliminar no ejecuta ninguna acción.

### 5. Contrataciones de agentes

Mostrar contratos activos y pasados en una tabla con cliente, agente alquilado, skills contratadas, fechas del contrato e importe total pagado. Cada fila tiene un menú de acciones. **Ver detalle** abre un modal con el desglose del contrato, incluyendo las skills contratadas y el precio individual de cada una.

Si el menú muestra **Marcar como devuelto** o **Eliminar**, esas acciones no ejecutan cambios.

### 6. Log de errores

Mostrar errores de ejecución con timestamp, nombre del agente, tipo de error y descripción breve. Usar badges de color para distinguir visualmente tipo o gravedad.

Cada entrada tiene un menú de acciones:

- **Ver detalle:** abre un modal con la traza completa del error.
- **Marcar como resuelto:** cambia el estado visible de esa entrada a resuelto durante la sesión actual.

## Datos de muestra

- Incluir registros representativos para todas las entidades y estados descritos, incluidos contratos activos y pasados, y errores de distintas gravedades.
- Mantener coherencia entre agentes, propietarios/clientes, skills asociadas, contratos y errores siempre que sea aplicable.
- Los totales del Dashboard deben ser valores de muestra plausibles y corresponder a los datos disponibles cuando sea razonable.
- Los registros completos deben incluir los campos necesarios para poblar los modales: usuario, prompt de sistema, detalle de skill, desglose de contrato y traza del error.

## Interacción y presentación

- Los menús de acciones se abren desde el botón de su fila y se pueden cerrar al volver a activar el botón, seleccionar una opción o hacer clic fuera del menú.
- Los modales presentan el contenido correspondiente sobre un backdrop y se cierran con un botón de cierre o al hacer clic en el backdrop.
- Las opciones sin implementación (Eliminar y Marcar como devuelto) permanecen inactivas; no eliminan datos ni alteran contratos.
- La expansión de skills permite alternar entre contraído y expandido, con transición suave.
- Los controles deben tener etiquetas accesibles, foco visible y nombres que expliquen su función. Los botones de menú exponen su estado expandido; los modales se identifican como diálogos y permiten cierre con Escape.
- Las tablas deben mantener sus encabezados asociados a las columnas y permitir identificar claramente el estado de cada registro.

## Criterios de aceptación

1. La página puede implementarse en un solo `index.html` y no depende de un proceso de build ni de un framework de interfaz.
2. La navegación lateral permite acceder a las seis secciones sin abandonar la página.
3. El Dashboard presenta las cuatro métricas requeridas y el placeholder semanal.
4. Usuarios, agentes, skills, contrataciones y errores muestran todos los campos indicados y sus menús de acciones.
5. Los modales de detalle contienen la información requerida y se cierran con botón y backdrop.
6. El control de tema cambia la interfaz completa entre claro y oscuro y conserva la selección al recargar.
7. Las skills de agentes están contraídas inicialmente y se expanden con una transición.
8. Los errores se distinguen mediante badges y se pueden marcar como resueltos visualmente.
9. Eliminar y Marcar como devuelto no ejecutan operaciones.
10. No se utiliza CSS personalizado ni estilos inline; los estilos provienen de utilidades de Tailwind cargadas por CDN.
