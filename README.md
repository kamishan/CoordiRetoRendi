# CoordiRetoRendi

Introducción a las Pruebas de Carga y Estrés del API de Coordinadora
Este documento presenta una introducción a las pruebas de carga y estrés realizadas sobre el API de Coordinadora, específicamente la URL:

https://apiv2-test.coordinadora.com/guias/cm-guias-consultas-ms/guia/99020012725

El objetivo principal de estas pruebas es evaluar exhaustivamente el desempeño del sistema bajo diversas condiciones de carga. Buscamos identificar el límite máximo de capacidad del API y observar su comportamiento a medida que aumentamos gradualmente tanto el número de usuarios concurrentes como la frecuencia de las solicitudes.

Para lograr este objetivo, se diseñaron y ejecutaron dos tipos de pruebas:

Prueba de Carga: Diseñada para simular la carga de usuarios esperada en condiciones normales de operación.
Prueba de Estrés: Concebida para llevar al sistema más allá de su capacidad normal, buscando identificar su punto de quiebre y la manera en que se degrada su rendimiento bajo presión extrema.
A continuación, se detallan las configuraciones específicas de cada prueba:

Configuración de las Pruebas:

Prueba de Carga:

Usuarios Simultáneos: 20
Frecuencia de Solicitudes: 2 solicitudes por segundo
Duración: 1 minuto
Total de Solicitudes Esperadas: Aproximadamente 100
Prueba de Estrés:

Usuarios Iniciales: 100, incrementando 50 usuarios cada 15 segundos.
Frecuencia de Solicitudes: Incremento gradual desde 10 hasta 100 solicitudes por segundo.
Duración: 1 minuto
Total de Solicitudes Esperadas: Hasta 6,000
Métricas Clave de Desempeño:

Para analizar los resultados de las pruebas y evaluar el comportamiento del API, se monitorizarán las siguientes métricas clave:

Tiempo de Respuesta Promedio (Percentil 95 - p(95)): Mide el tiempo promedio que tarda el API en responder a las solicitudes, considerando el percentil 95 para eliminar valores atípicos y enfocarnos en la experiencia del usuario más representativa.
Tasa de Errores (HTTP 4xx, HTTP 5xx): Indica el porcentaje de solicitudes que resultan en errores del lado del cliente (4xx) o del servidor (5xx), lo que señala posibles problemas de funcionalidad o capacidad.
RPS (Requests Per Second - Solicitudes por Segundo): Mide la cantidad de solicitudes que el API es capaz de procesar por segundo, reflejando su capacidad de rendimiento.
Análisis de Resultados Esperados:

Prueba de Carga:

Objetivo: Validar la consistencia del API bajo una carga esperada, asegurando un rendimiento estable en condiciones operativas normales.
Resultados Esperados:
Tiempo de Respuesta Promedio: Debería ser inferior o igual a 500 milisegundos (≤ 500ms), garantizando una buena experiencia de usuario.
Tasa de Éxito: Debería ser superior o igual al 99% (≥ 99%), indicando una alta fiabilidad del API bajo carga normal.
Prueba de Estrés:

Objetivo: Identificar el punto de quiebre del sistema y observar la degradación de su rendimiento bajo condiciones extremas.
Resultados Esperados:
Degradación Progresiva del Rendimiento: Se espera que a medida que aumenta la carga, el tiempo de respuesta se incremente y la tasa de éxito disminuya.
Identificación del Límite de Usuarios Concurrentes: La prueba busca determinar la cantidad máxima de usuarios que el API puede soportar antes de experimentar fallos significativos o una degradación inaceptable del rendimiento.
Entrega Final:

El resultado de este análisis se presentará en un informe que incluirá:

Gráficos de Rendimiento: Visualizaciones gráficas de las métricas clave (tiempo de respuesta, RPS, tasa de errores) a lo largo del tiempo durante ambas pruebas.
Estadísticas Detalladas de Errores: Un desglose de los tipos de errores HTTP encontrados y su frecuencia.
Recomendaciones de Optimización: Basadas en los resultados obtenidos, se proporcionarán recomendaciones específicas para optimizar el rendimiento y la escalabilidad del API, si se identifican áreas de mejora.
Este informe proporcionará una visión clara y detallada del comportamiento del API bajo carga, permitiendo identificar posibles cuellos de botella y áreas de mejora para garantizar una experiencia de usuario óptima y un sistema robusto y escalable.
