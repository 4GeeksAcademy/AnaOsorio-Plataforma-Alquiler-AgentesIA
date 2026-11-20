# Plan de implementación: Panel administrativo AgentHub

## Objetivo

Crear una SPA administrativa de escritorio en `index.html`, usando Tailwind CSS por CDN y JavaScript vanilla. La solución consolidará el sistema visual y los patrones de las referencias Stitch en una única página, sin framework, proceso de build, CSS personalizado ni estilos inline.

## Fuentes de diseño

- `specs/bookshelf-dashboard/spec.md`: alcance funcional y criterios de aceptación.
- `DESIGN.md`: sistema visual, paleta, tipografía, espaciado, componentes y motion.
- `stitch-reference/`: estructuras HTML, datos, estilos y comportamientos reutilizables por sección.

## Restricciones

- El único archivo de implementación será `index.html`.
- Los datos serán hardcodeados dentro del HTML o de su bloque JavaScript.
- No habrá backend, autenticación, llamadas API ni persistencia de datos de negocio.
- Eliminar y Marcar como devuelto quedarán presentes como opciones sin efecto funcional.
- La prioridad será escritorio con una adaptación básica a pantallas estrechas.
- Los estilos deberán provenir de utilidades Tailwind y los iconos podrán mantenerse como SVG inline.

## Estrategia visual

1. Partir del shell de Stitch: sidebar fijo de 256 px, barra superior de 64 px, perfil y contador de errores.
2. Reutilizar tarjetas elevadas, tablas estándar, badges, menús, modales y estados semánticos de las referencias.
3. Consolidar los tokens visuales de `DESIGN.md` sin duplicar hojas de estilo ni bloques `<style>`.
4. Sustituir enlaces entre páginas por navegación interna en la misma página.
5. Usar `min-h-screen` en lugar de alturas fijas heredadas de las maquetas.

## Secuencia de implementación

### 1. Integración visual

Crear la estructura base del documento y el shell administrativo. Aplicar el sistema visual claro/oscuro, tipografía, superficies, bordes y espaciado de Stitch. Incorporar sidebar, top bar, indicadores de entorno y el perfil administrativo.

### 2. Contenido de las secciones

Implementar el contenido en dos bloques controlados:

- Dashboard, Usuarios y Agentes.
- Skills, Contrataciones y Log de errores.

Cada sección reutilizará los fragmentos más cercanos a Stitch, pero los datos se centralizarán para mantener coherencia entre entidades.

### 3. Navegación

Representar las seis secciones como paneles dentro de `index.html`. Los controles laterales cambiarán el panel visible sin recargar. La navegación activa, el título superior y el contador de errores deben permanecer sincronizados.

En pantallas inferiores a `lg`, el sidebar debe convertirse en un drawer con botón de apertura y cierre básico.

### 4. Dropdowns

Consolidar una implementación única para los botones `⋮` de tablas y cards. Debe gestionar exclusividad entre menús, `aria-expanded`, cierre por selección, clic exterior y Escape.

Las opciones funcionales abrirán modales; Eliminar y Marcar como devuelto solo cerrarán el menú.

### 5. Modales

Consolidar el patrón de backdrop, cabecera, cuerpo y pie. Implementar los diálogos de usuario, prompt de agente, skill, contrato y traza de error. Los modales se cerrarán por botón, footer, backdrop y Escape.

### 6. Modo oscuro

Inicializar el tema desde `localStorage` antes del render principal. El toggle alternará la clase `dark` en `<html>` y guardará la preferencia. Todas las variantes visuales deberán tener contrapartes `dark:`.

### 7. Verificación

Comprobar navegación, datos, dropdowns, modales, expansión de skills, resolución de errores, persistencia de tema y adaptación móvil básica. Confirmar además que no existe otro archivo de implementación y que no hay CSS personalizado ni estilos inline.

## Dependencias

1. La integración visual precede al contenido de las secciones.
2. El shell y la navegación deben estar operativos antes de probar vistas aisladas.
3. Los datos y las vistas dependen del patrón común de dropdown.
4. Los modales dependen de los datos de las secciones y del patrón común de cierre.
5. El modo oscuro puede inicializarse desde el shell y verificarse al finalizar cada componente.
6. La verificación final empieza después de completar las seis secciones e interacciones.

## Resultado esperado

Un único `index.html` con las seis secciones, navegación persistente, datos hardcodeados, dropdowns, modales, expansión de skills, resolución visual de errores y modo claro/oscuro persistente.
