**ESTRUCTURA BACK-END Y PERSISTENCIA** 

## **Modelado de Datos Relacional** 

**Arquitectura:** Modelo Entidad - Relación · **Formato:** Modelado de datos.md 

Este informe detalla la especificación lógica del esquema de almacenamiento que recopilará de forma estructurada los registros generados mediante la interacción del usuario con la interfaz web hotelera. 

## **1. Diccionario de Datos Relacional** 

## **Entidad Física: Habitacion** 

Estructura lógica que define el catálogo real de dependencias habitacionales integradas dentro del inventario del hotel. 

|**Campo**|**Tipo de Dato**|**Restricciones**|**Descripción e Integridad**|
|---|---|---|---|
|`id_habitacion`|INT|Llave Primaria /|Identificador exclusivo e inequívoco|
|||Autoincremental|asignado internamente a cada habitación.|
|`tipo`|VARCHAR(50)|NOT NULL|Categoría comercial asignada: 'Simple',|
||||'Doble', 'Matrimonial', 'Suite'.|
|`precio_noche`|DECIMAL(10,2)|NOT NULL|Costo financiero establecido por|
||||pernoctación expresado en moneda de|
||||curso legal.|
|`capacidad`|INT|NOT NULL|Métrica entera que delimita la cantidad|
||||máxima permitida de huéspedes en la|
||||unidad.|
|`estado`|VARCHAR(30)|DEFAULT 'Disponible'|Bandera de control de disponibilidad:|
||||'Disponible', 'Ocupada', 'Mantenimiento'.|



## **Entidad Lógica: Reserva** 

Almacenamiento de transacciones operativas generadas por la cumplimentación completa del formulario web de reservas. 

Diseño Conceptual y Lógico de Base de Datos 

1 

|**Campo**|**Tipo de Dato**|**Restricciones**|**Descripción e Integridad**|
|---|---|---|---|
|`id_reserva`|INT|Llave Primaria /|Código identificativo de control para el|
|||Autoincremental|seguimiento del trámite del cliente.|
|`nombre_cliente`|VARCHAR(100)|NOT NULL|Nombres y apellidos completos del titular|
||||responsable de la reserva.|
|`correo_cliente`|VARCHAR(100)|NOT NULL|Dirección de correo electrónico validada|
||||para el envío de comprobantes de|
||||confirmación.|
|`id_habitacion`|INT|Llave Foránea|Vínculo relacional directo que asocia la|
|||(Habitacion)|reserva a una unidad de inventario física.|
|`fecha_checkin`|DATE|NOT NULL|Fecha formal programada para el ingreso|
||||físico y toma de la habitación.|
|`fecha_checkout`|DATE|NOT NULL|Fecha formal programada para la salida|
||||física y liberación de inventario.|
|`notas_especiales`|TEXT|NULL|Bloque de texto para observaciones|
||||personalizadas ingresadas opcionalmente.|



## **2. Reglas de Negocio y Cardinalidad Relacional** 

El diseño de persistencia se articula bajo las siguientes directrices y restricciones estructurales: 

- **Cardinalidad Una a Muchas (1:N):** Una instancia registrada dentro de la entidad `Habitacion` posee la capacidad de asociarse cronológicamente a múltiples registros históricos contenidos en la tabla `Reserva` a lo largo del tiempo operacional del hotel. 

- **Restricción de Integridad Referencial:** Cualquier inserción de datos ejecutada dentro de la entidad `Reserva` requiere de forma estricta la existencia previa de un código válido correlativo mapeado en el 

- campo `id_habitacion` . 

- **Validación de Superposición Cronológica:** El motor de lógica del backend deberá garantizar que dos reservas independientes asociadas al mismo `id_habitacion` no presenten colisiones ni cruces en los rangos de fechas comprendidos entre sus respectivos campos de entrada y salida. 

Diseño Conceptual y Lógico de Base de Datos 

2 

