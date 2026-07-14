# Last-Mile Logistics Route & Fleet Optimizer (v2.0)
Este proyecto es un **Planificador Inteligente de Rutas de Última Milla** interactivo desarrollado en Python. Resuelve el problema clásico de optimización de flotas con restricciones de capacidad (**CVRP - Capacitated Vehicle Routing Problem**) y ventanas horarias de entrega (**VRPTW**).

La herramienta está pensada para simular el reparto urbano real (ejemplificado en Barcelona), organizando automáticamente las entregas en múltiples viajes eficientes cuando se supera la carga de la furgoneta.

## Características Clave
*   **Heurística de Optimización (Vecino Más Cercano):** Algoritmo ávido de distancias geodésicas (fórmula de Haversine) para reducir al máximo los kilómetros recorridos por la flota.
*   **Gestión Dinámica de Capacidad (CVRP):** El sistema calcula el peso de los paquetes y obliga al vehículo a regresar al Almacén Central para "recargar" cuando se alcanza el límite configurado.
*   **Control de Ventanas Horarias (VRPTW):** Calcula la hora estimada de llegada a cada cliente basándose en la velocidad media y el tiempo de descarga. Identifica y emite alertas visuales rojas si una entrega se realiza con retraso.
*   **Mapas Interactivos con Folium:** Genera mapas integrados sobre OpenStreetMap donde cada viaje independiente de la furgoneta se dibuja en un color diferente para facilitar el análisis visual.
*   **Métricas Financieras y Medioambientales:** Reportes en tiempo real sobre el consumo de gasoil estimado (L), coste monetario de la ruta (€) y la huella de carbono generada en kilogramos de $CO_2$.

## Tecnologías Utilizadas
*   **Python 3** como motor lógico.
*   **Folium** para el renderizado del mapa interactivo y capas de rutas.
*   **Geopy** para el cálculo preciso de distancias por coordenadas terrestres.
*   **IPywidgets** para el panel de control y controles deslizantes del usuario.
*   **IPython.display HTML** para la incrustación segura del mapa en navegadores modernos.

## Ejemplo de Ejecución
Al configurar una furgoneta con capacidad máxima de **180 kg** para entregar pedidos a **8 clientes** distribuidos por la ciudad:
1. El sistema detecta que el peso acumulado es superior a 180 kg y divide el trabajo en **2 viajes**.
2. Traza el **Viaje 1 en azul** y el **Viaje 2 en verde**, ambos saliendo y regresando al Almacén Central.
3. Evalúa la hora de llegada estimada de cada tramo y avisa si se cumple el pacto horario del cliente.
4. Genera el mapa interactivo permitiendo hacer clic en cada parada para ver los detalles del pedido y del viaje.
