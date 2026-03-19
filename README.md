# Rincon-post2-u2
Proyecto: Diseño de Interfaz Móvil Paso a Paso
Paso 1: Definición de la App y Selección de Flujo
1. Nombre y Categoría de la Aplicación
Nombre de la aplicación: Parkeado
Categoría: Transporte
Parkeado es una aplicación móvil diseñada para facilitar la búsqueda y reserva de espacios de estacionamiento en zonas urbanas con alta demanda, mediante visualización en tiempo real.
2. Usuario Objetivo Principal
La aplicación está dirigida a adultos entre 25 y 45 años que residen o trabajan en zonas urbanas con alta congestión vehicular.
Se trata de personas que utilizan automóvil propio como medio principal de transporte y tienen dificultades frecuentes para encontrar estacionamiento disponible cerca de su destino.
3. Problema que Resuelve
Los conductores en zonas urbanas pierden tiempo y experimentan altos niveles de estrés al no encontrar estacionamiento disponible cerca de su destino.
4. Definición del Flujo de Usuario (Tres Pantallas Interconectadas)
El flujo principal de la aplicación permite al usuario buscar, seleccionar y reservar un espacio de estacionamiento de manera rápida y estructurada.
Pantalla 1: Mapa Principal / Búsqueda
El usuario visualiza un mapa interactivo con espacios de estacionamiento disponibles en tiempo real. Además, puede ingresar una dirección o punto de interés en la barra de búsqueda.
Desde esta pantalla, el usuario selecciona un espacio disponible para consultar más información.
Transición: Al seleccionar un espacio, el usuario es dirigido a la Pantalla 2.
Pantalla 2: Detalle del Estacionamiento
En esta pantalla se muestra información detallada del espacio seleccionado, incluyendo:
•	Precio por hora
•	Nivel de disponibilidad
•	Distancia desde la ubicación actual
•	Horario de funcionamiento
•	Calificación de usuarios
El usuario puede presionar el botón “Reservar espacio” para continuar.
Transición: Al confirmar la reserva, el usuario es dirigido a la Pantalla 3.
Pantalla 3: Confirmación de Reserva
Se muestra un resumen de la reserva realizada, incluyendo:
•	Dirección del estacionamiento
•	Tiempo límite estimado para llegar
•	Código o comprobante de reserva
La pantalla incluye un botón para “Iniciar navegación”, que permite al usuario dirigirse al destino.

Paso 2: Construcción del Design System en Figma y Paso 3: Diseño de las 3 Pantallas con Accesibilidad WCAG AA
Map Screen
Map Screen.jpg
Park Slot Details Screen
Park Slot Details Screen.jpg
Reservation Confirmation Screen
Reservation Confirmation Screen.jpg
Paso 4: Documentación de Microinteracciones
Microinteracción 1: Confirmación de Reserva de Estacionamiento
1. Nombre Descriptivo
Confirmación dinámica de reserva
Esta microinteracción ocurre cuando el usuario confirma la reserva de un espacio desde la pantalla de detalle del estacionamiento.
2. Trigger
El usuario presiona el botón primario “Reservar espacio” en la Pantalla 2 (Detalle del Estacionamiento).
3. Rules
•	El botón cambia inmediatamente al estado loading.
•	Se deshabilita la interacción adicional del botón mientras se procesa la solicitud.
•	Se envía la solicitud de reserva al sistema (simulado a nivel prototipo).
•	Si la reserva es exitosa:
•	El botón cambia al estado success.
•	Se redirige automáticamente a la Pantalla 3 (Confirmación).
•	Si ocurre un error:
•	El botón vuelve al estado default.
•	Se activa un mensaje de error mediante un componente de feedback (snack bar).
4. Feedback
•	Animación de spinner dentro del botón (duración aproximada: 300–500 ms).
•	Cambio visual de color del botón al estado exitoso (ej. verde o tonalidad confirmatoria dentro del sistema de color).
•	Transición suave (ease-in-out, 200 ms) hacia la pantalla de confirmación.
•	En caso de error, aparición de snack bar con mensaje claro: “No se pudo completar la reserva. Intenta nuevamente.”
5. Loop / Modo
•	Si la reserva falla, el sistema retorna al estado inicial permitiendo reintentar la acción.
•	Si el usuario no interactúa tras un error, el snack bar desaparece automáticamente después de 4 segundos.
•	No existe repetición automática del proceso sin intervención del usuario.

Microinteracción 2: Aplicación de Filtros en el Mapa
1. Nombre Descriptivo
Filtrado dinámico de estacionamientos
Esta microinteracción permite al usuario refinar los resultados visibles en el mapa según criterios como precio o distancia.
2. Trigger
El usuario presiona el ícono de Filtro (mínimo 44x44 pt) ubicado en la Pantalla 1 (Mapa Principal).
3. Rules
•	Se despliega un panel modal inferior (bottom sheet).
•	El usuario selecciona uno o más criterios (ej. “Menor precio”, “Más cercano”).
•	Al presionar el botón “Aplicar filtros”:
•	El panel se cierra.
•	El mapa actualiza los marcadores visibles según el criterio seleccionado.
•	Si el usuario presiona “Cancelar”, no se aplican cambios.
4. Feedback
•	Animación de aparición del bottom sheet desde la parte inferior (300 ms, ease-out).
•	Resaltado visual de las opciones seleccionadas (cambio de color y estado activo).
•	Actualización visual de los marcadores en el mapa con ligera animación de fade-in (200 ms).
•	Aparición temporal de un badge o texto indicador: “Filtros aplicados”.
5. Loop / Modo
•	El usuario puede abrir y modificar los filtros tantas veces como desee.
•	Si no hay resultados disponibles tras aplicar filtros, se muestra un mensaje: “No se encontraron espacios con estos criterios”.
•	El sistema mantiene los filtros activos hasta que el usuario los cambie o los limpie manualmente.
Link figma: https://www.figma.com/design/3L4GycTYOl29aedJtaA4PA/Untitled?node-id=0-1&t=as7Xyn8UBZ5oJo2I-1


