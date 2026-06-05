**PROYECTO DE DESARROLLO TÉCNICO WEB** 

## **Especificación Técnica de Requerimientos** 

**Sistema:** Gestión e Información Hotelera · **Formato:** requerimientos.md 

Este documento define el alcance funcional y los criterios de calidad que regirán el desarrollo del sitio web para el establecimiento hotelero. El propósito principal es guiar la maquetación de las interfaces estáticas y el diseño de los formularios de entrada de datos. 

## **1. Requerimientos Funcionales (RF)** 

Definen las acciones, servicios y flujos específicos que la aplicación web debe ejecutar para interactuar correctamente con los usuarios: 

- **RF-01:  Catálogo  Digital  de  Habitaciones:** La  plataforma  web  dispondrá  de  un  apartado estructurado para visualizar las opciones de alojamiento disponibles, especificando la categorización (Habitaciones Simples, Dobles, Matrimoniales y Suites), tarifas vigentes por pernoctación, desglose detallado de servicios incluidos (desayuno, conectividad, climatización) y material fotográfico de soporte. 

- **RF-02: Interfaz del Formulario de Reserva:** Módulo principal de captura de datos donde el cliente potencial  podrá  formalizar  una  solicitud  mediante  la  introducción  obligatoria  de  los  siguientes parámetros: fecha calendarizada de ingreso (check-in), fecha calendarizada de salida (check-out), selección del tipo de habitación deseada y los datos personales de contacto correspondientes. 

- **RF-03: Módulo de Atención y Consultas Especiales:** Integración de un formulario alternativo de comunicación directa. Permitirá al usuario enviar dudas generales, requerimientos especiales de accesibilidad, reportar necesidades de transporte o solicitar servicios de alimentación personalizados previos a su arribo. 

- **RF-04: Arquitectura de Navegación Estática:** Estructuración formal del portal web, compuesto obligatoriamente  por  una  página  de  inicio  (Home  Page)  de  alto  impacto  visual,  un  menú  de navegación dedicado a los servicios adicionales del hotel (zonas comunes, restaurante, piscina) y un área informativa de localización geográfica y reseña histórica corporativa. 

## **2. Requerimientos No Funcionales (RNF)** 

Establecen las restricciones operativas, de rendimiento, usabilidad y aspectos técnicos indispensables para asegurar la calidad de la experiencia digital: 

- **RNF-01: Adaptabilidad y Maquetación Líquida (Responsive Design):** La totalidad de las vistas creadas  en  HTML  y  CSS  deben  contar  con  una  arquitectura  fluida  que  garantice  una  óptima 

Especificación de Requerimientos de Software (ERS) 

1 

navegación, legibilidad y accesibilidad visual desde dispositivos móviles, tablets y ordenadores de escritorio. 

- **RNF-02: Lógica de Validación Cronológica en Front-end:** El script de validación asociado a los formularios  deberá  asegurar  la  integridad  lógica  de  las  fechas.  El  sistema  impedirá  de  forma restrictiva que la fecha de salida (check-out) sea seleccionada con una temporalidad anterior o igual a la fecha de ingreso programada (check-in). 

- **RNF-03: Eficiencia de Carga e Indexación de Medios:** Los recursos gráficos utilizados (imágenes de la infraestructura y habitaciones) deberán pasar por un proceso de compresión y optimización web, garantizando que el tiempo general de renderizado de la página no supere los 3 segundos en condiciones de conectividad móvil convencionales. 

- **RNF-04: Compatibilidad entre Navegadores:** El código fuente resultante deberá cumplir con los estándares web vigentes, asegurando una visualización idéntica y sin pérdida de funciones en los motores de búsqueda modernos más utilizados (Google Chrome, Mozilla Firefox, Microsoft Edge y Safari). 

Especificación de Requerimientos de Software (ERS) 

2 

