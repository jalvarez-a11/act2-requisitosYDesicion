Introducción

En la Actividad 1 se diagnosticó que la empresa recibe pedidos desde varios canales, maneja inventarios distribuidos y coordina entregas con diferentes rutas y repartidores, pero no cuenta con una vista centralizada del estado real de cada pedido. Esto provoca duplicación de información, retrasos, errores operativos y poca trazabilidad.

En esta entrega se convierten esas necesidades en requisitos funcionales y atributos de calidad. Después se priorizan, se definen escenarios medibles y se comparan dos alternativas arquitectónicas para tomar una decisión justificada.

2. Objetivo y alcance

Objetivo: diseñar la estructura inicial de una plataforma que centralice el registro y consulta de pedidos, la validación de inventario, la asignación de rutas y repartidores, el seguimiento de entregas y la gestión de incidencias.

Incluido

Registro de pedidos provenientes de varios canales.

Consulta de inventario distribuido.

Gestión de estados e historial de pedidos.

Asignación de rutas y repartidores.

Registro de seguimiento, intentos y resultados de entrega.

Gestión de incidencias y consulta por soporte.

Integración con pagos, geolocalización, notificaciones y ERP/CRM.

Fuera del alcance en esta etapa

Despliegue productivo y construcción completa de la solución.

Reemplazo del ERP/CRM o creación de un sistema propio de pagos.

Optimización avanzada de rutas mediante inteligencia artificial.

Selección definitiva de nube, lenguaje, framework o motor de base de datos.

3. Catálogo de requisitos funcionales

ID

Requisito

Descripción

Prioridad

RF-01

Registrar pedidos

Recibir y registrar pedidos de los canales autorizados.

Must

RF-02

Identificador único

Asignar un identificador único y evitar registros duplicados.

Must

RF-03

Consultar pedidos

Buscar pedidos y consultar estado e historial según permisos.

Must

RF-04

Validar inventario

Consultar disponibilidad antes de confirmar la preparación.

Must

RF-05

Gestionar estados

Permitir cambios válidos de estado y guardar cada cambio.

Must

RF-06

Asignar entrega

Asignar repartidor y ruta a un pedido preparado.

Must

RF-07

Seguimiento

Registrar recogida, tránsito, intento y resultado de entrega.

Must

RF-08

Gestionar incidencias

Crear, clasificar, consultar y cerrar incidencias asociadas a pedidos.

Should

RF-09

Notificaciones

Solicitar avisos cuando ocurran eventos importantes.

Should

RF-10

Indicadores

Consultar pedidos, retrasos y entregas fallidas.

Could

RF-11

Control de acceso

Limitar funciones y datos según el rol del usuario.

Must

RF-12

Integraciones

Intercambiar datos con pagos, geolocalización, notificaciones y ERP/CRM.

Should

4. Requisitos no funcionales / atributos de calidad

Los siguientes valores son objetivos iniciales de diseño tomados como referencia para el ejercicio. No son mediciones de una plataforma existente; deben validarse con el negocio y mediante pruebas.

ID / atributo

Criterio verificable propuesto

RNF-01 Rendimiento

El 95% de las consultas de estado de pedido debe responder en máximo 2 segundos bajo carga acordada.

RNF-02 Capacidad

Probar inicialmente 1.000 transacciones por hora como objetivo de referencia; ajustar según volumen real.

RNF-03 Seguridad

Cifrar las comunicaciones en tránsito y no almacenar contraseñas en texto plano.

RNF-04 Autorización

Cada rol solo puede consultar y ejecutar acciones autorizadas.

RNF-05 Disponibilidad

Objetivo inicial de 99,5% mensual, excluyendo mantenimientos programados.

RNF-06 Trazabilidad

El 100% de los cambios de estado debe guardar fecha/hora, pedido, evento y actor/sistema.

RNF-07 Mantenibilidad

Separar responsabilidades en módulos con dependencias explícitas.

RNF-08 Evolución

Permitir cambiar reglas de un dominio sin modificar innecesariamente los demás módulos.

RNF-09 Integración

Registrar fallos de servicios externos y permitir reintentos controlados sin duplicar pedidos.

RNF-10 Recuperación

Contar con copias de seguridad y un procedimiento de restauración probado.
