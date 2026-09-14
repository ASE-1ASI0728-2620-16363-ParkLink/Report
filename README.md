# ParkLink — Informe de Proyecto TB1

> **Estado del documento:** Trabajo de Base 1 (TB1). Este informe presenta evidencia de descubrimiento, especificación y diseño arquitectónico. Los elementos señalados como pendientes no constituyen resultados validados.

## Navegación rápida

- [Información del informe](#información-del-informe)
- [Capítulo I — Perfil y problema](#capítulo-i--perfil-y-problema)
- [Capítulo II — Investigación y análisis](#capítulo-ii--investigación-y-análisis)
- [Capítulo III — Especificación](#capítulo-iii--especificación)
- [Capítulo IV — Diseño de arquitectura](#capítulo-iv--diseño-de-arquitectura)
- [Conclusiones](#conclusiones)
- [Bibliografía](#bibliografía)
- [Anexos](#anexos)

## Información del informe

| Campo | Información |
|---|---|
| Universidad | Universidad Peruana de Ciencias Aplicadas |
| Carrera | Ingeniería de Software |
| Curso | 1ACC0238 — Aplicaciones para Dispositivos Móviles |
| Entrega | TB1 |
| Startup | ParkLink |
| Producto | ParkLink |
| Periodo, NRC y docente | TODO — confirmar datos vigentes antes de la exportación |
| Mes y año | TODO — confirmar antes de la exportación |

### Relación de integrantes

| Código | Apellidos y nombres |
|---|---|
| U202310971 | Pietro Osores Marchese |
| — | TODO – Integrante pendiente |
| — | TODO – Integrante pendiente |
| — | TODO – Integrante pendiente |

### Registro de versiones

| Versión | Fecha | Responsable | Cambio |
|---|---|---|---|
| 0.1 | TODO — registrar fecha | Pietro Osores Marchese | Estructura inicial del informe TB1 y consolidación de evidencia disponible. |
| 0.2 | TODO — registrar fecha | TODO — validar responsables | Revisión de contenidos, entrevistas y diagramas antes de la entrega. |

### Project Report Collaboration Insights

Este informe distingue entre evidencia disponible, decisiones de diseño propuestas y datos pendientes de validación. La relación de contribuciones individuales debe completarse con evidencias verificables de repositorio y revisión del equipo; por ello no se asignan contribuciones históricas a una sola persona.

| Área | Evidencia disponible | Estado |
|---|---|---|
| Investigación de usuarios | Cuatro entrevistas registradas, dos por segmento | Parcial: faltan dos entrevistas para el mínimo de tres por segmento |
| Requerimientos | Épicas, historias de usuario y criterios de aceptación documentados | Disponible para revisión |
| Arquitectura | Decisiones, límites de contexto y diagramas propuestos | Diseño TB1, sujeto a validación técnica |
| Participación | Un integrante confirmado | Pendiente de completar integrantes y evidencias individuales |

### Student Outcome

| Resultado | Evidencia en TB1 | Estado |
|---|---|---|
| Adquirir y aplicar nuevos conocimientos según sea necesario | Se aplican técnicas de entrevistas, Lean UX, priorización y modelado DDD/C4 para estructurar el problema y una arquitectura propuesta. | Evidencia documental disponible; la demostración individual requiere sustentación. |


# Capítulo I — Perfil y problema

## 1.1 Startup Profile

### Descripción

ParkLink propone una plataforma para conectar a conductores que necesitan encontrar estacionamiento con propietarios que cuentan con espacios que podrían poner a disposición. El foco inicial es reducir la incertidumbre al buscar estacionamiento y ordenar la publicación, disponibilidad, reserva y pago de espacios.

| Elemento | Definición de trabajo |
|---|---|
| Propósito | Facilitar la búsqueda y reserva de estacionamientos, y habilitar la gestión de espacios para propietarios. |
| Propuesta de valor para conductores | Consultar opciones cercanas, comparar información y solicitar una reserva. |
| Propuesta de valor para propietarios | Publicar espacios, configurar disponibilidad y revisar reservas. |
| Alcance TB1 | Descubrimiento, requisitos y arquitectura propuesta; no acredita operación en producción. |

### Perfil del integrante confirmado

| Integrante | Perfil |
|---|---|
| Pietro Osores Marchese — U202310971 | Estudiante de Ingeniería de Software. La evidencia individual y la distribución definitiva de responsabilidades se deben validar con los registros de trabajo y la sustentación. |

## 1.2 Solution Profile

### Producto

**ParkLink** es una propuesta de producto digital de estacionamiento. Permite modelar una experiencia en la que un conductor localiza un espacio, revisa sus condiciones y solicita una reserva; un propietario registra y administra la oferta de su espacio.

### Problema

Los conductores entrevistados describen incertidumbre al buscar un espacio disponible y valoran conocer disponibilidad, precio y distancia antes de llegar. Los propietarios entrevistados describen gestión manual, poca visibilidad de sus espacios y necesidad de controlar horarios y precios. Estas observaciones se limitan a la muestra registrada y no deben generalizarse a toda la población.

### Análisis 5W2H

| Pregunta | Respuesta basada en el alcance TB1 |
|---|---|
| **What?** | Dificultad para encontrar y administrar estacionamientos disponibles. |
| **Why?** | La información y la coordinación pueden estar dispersas o ser manuales. |
| **Who?** | Conductores urbanos y propietarios de espacios de estacionamiento. |
| **Where?** | Entornos urbanos donde conductor y oferta deben coordinar un intervalo de uso. |
| **When?** | Antes y durante la búsqueda de un estacionamiento, y al configurar o administrar un espacio. |
| **How?** | Con búsqueda, detalle, reserva, gestión de disponibilidad y notificaciones propuestas. |
| **How much?** | No se cuenta con datos de mercado ni estimación económica validada para TB1. |

## 1.3 Lean UX

### Proceso

El ciclo propuesto sigue cuatro actividades: declarar el problema, formular supuestos, construir una solución mínima verificable y medir con usuarios. La etapa de medición queda pendiente hasta completar el plan de investigación y las pruebas con la muestra definida.

### Problem statements

1. Los conductores urbanos necesitan reducir la incertidumbre de encontrar un estacionamiento porque la búsqueda manual puede consumir tiempo y dificultar la planificación del trayecto.
2. Los propietarios necesitan una forma clara de gestionar sus espacios porque la coordinación manual puede limitar su visibilidad y control de horarios.

### Supuestos

| Tipo | Supuesto a validar |
|---|---|
| Negocio | Una plataforma puede crear valor si conecta oferta de espacios con demanda de conductores. |
| Usuario | Los conductores considerarían útil comparar disponibilidad, precio y distancia antes de elegir. |
| Usuario | Los propietarios valorarían poder definir horarios, precio y estado de disponibilidad. |
| Riesgo | La información mostrada debe diferenciar una consulta de disponibilidad de una reserva confirmada. |

### Hipótesis

| ID | Hipótesis | Señal de validación propuesta |
|---|---|---|
| H1 | Si un conductor consulta espacios por destino y ve precio, horario y distancia, podrá evaluar opciones antes de desplazarse. | Prueba de tarea con participantes y registro de comprensión; pendiente. |
| H2 | Si un propietario configura horarios, precio y activación de un espacio, podrá gestionar su oferta sin coordinación manual dispersa. | Prueba de tarea con propietarios; pendiente. |
| H3 | Si una reserva se confirma solo tras validar disponibilidad y pago, conductor y propietario recibirán una señal trazable del estado. | Prueba de flujo y revisión técnica; pendiente. |

### Lean UX Canvas

![Lean UX Canvas de ParkLink](docs/tb1/assets/lean-ux-canvas.svg)

| Bloque | Contenido |
|---|---|
| Problema de negocio | Incertidumbre de búsqueda para conductores y gestión manual para propietarios. |
| Usuarios | Conductores urbanos; propietarios de espacios. |
| Resultados de usuario | Comparar una opción antes de reservar; configurar una oferta y conocer reservas. |
| Resultados de negocio | Pendiente de definir métricas y periodo de medición. |
| Ideas de solución | Búsqueda, filtros, detalle, reserva, publicación, disponibilidad y notificaciones. |
| Supuestos | Las personas aceptarán una experiencia digital si la información y el control resultan claros. |
| Hipótesis | H1, H2 y H3, con pruebas aún pendientes. |
| Experimentos | Entrevistas ampliadas, pruebas de tarea y evaluación de prototipos. |

## 1.4 Segmentos objetivo

| Segmento | Necesidades observadas en la muestra | Límites de evidencia |
|---|---|---|
| Conductores urbanos | Conocer opciones cercanas; revisar disponibilidad, precio y distancia. | Dos entrevistas registradas; falta una entrevista adicional. |
| Propietarios de estacionamientos | Publicar espacios; configurar horarios y precio; controlar reservas. | Dos entrevistas registradas; falta una entrevista adicional. |


# Capítulo II — Investigación y análisis

## 2.1 Competidores y análisis competitivo

La comparación siguiente es un marco de posicionamiento basado en la información documentada para TB1. No se presenta como estudio de mercado actualizado ni como verificación de funcionalidades vigentes de terceros.

| Alternativa considerada | Enfoque descrito en el análisis | Oportunidad para ParkLink | Límite |
|---|---|---|---|
| Apparka | Pago y gestión de estacionamiento. | Integrar descubrimiento, reserva y comunicación en un recorrido coherente. | Requiere verificación competitiva independiente antes de una decisión comercial. |
| Parkopedia | Consulta de ubicaciones de estacionamiento. | Diferenciar el detalle de disponibilidad y la reserva propuesta. | No se afirma cobertura ni funciones vigentes. |
| Quadra | Gestión operativa de estacionamientos. | Considerar una experiencia orientada a propietarios de espacios pequeños. | No se afirma mercado objetivo ni alcance actual. |
| ParkLink | Búsqueda, publicación, reserva, pago y notificación propuestos. | Conectar los dos segmentos en un modelo trazable. | La propuesta requiere validación con usuarios y viabilidad de negocio. |

### Estrategias de trabajo

| Estrategia | Hipótesis de diferenciación | Evidencia requerida |
|---|---|---|
| Disponibilidad y reserva | Separar la consulta de disponibilidad de la confirmación transaccional de una reserva. | Pruebas de flujo, reglas de concurrencia y validación con usuarios. |
| Oferta de propietarios | Permitir configurar espacios, horarios, precios y estado. | Pruebas de tarea con propietarios. |
| Información para decidir | Mostrar detalle, precio, horario y distancia cuando el dato esté disponible. | Evaluación de comprensión y origen verificable de datos. |
| Confianza | Trazar confirmaciones, cancelaciones, pagos y notificaciones. | Diseño de auditoría, seguridad e integración de pagos. |

## 2.2 Entrevistas

### Diseño de entrevistas

Las entrevistas semiestructuradas buscan conocer prácticas, dificultades y expectativas de los dos segmentos. La guía indaga por contexto de uso, proceso actual, problemas, información necesaria y reacción ante una plataforma. No se utiliza para estimar prevalencia estadística.

| Segmento | Preguntas de exploración |
|---|---|
| Conductores urbanos | ¿Cómo busca estacionamiento? ¿Qué información necesita antes de llegar? ¿Qué ocurre si no encuentra espacio? ¿Qué esperaría de una reserva? |
| Propietarios | ¿Cómo administra los espacios? ¿Qué dificulta su gestión? ¿Cómo define horario y precio? ¿Qué control espera de una plataforma? |

### Registro de entrevistas — conductores

| Entrevistado | Edad | Evidencia registrada | Hallazgos descritos |
|---|---:|---|---|
| Humberto Garcia Calla | 50 | Resumen de entrevista; material audiovisual no se publica por privacidad. | Reportó incertidumbre al llegar a un destino y búsquedas de hasta 20 minutos. Indicó interés en ver espacios libres cerca del destino, con precio y distancia en el mapa. |
| Juan Pablo Yataca Juarez | 25 | Resumen de entrevista; material audiovisual no se publica por privacidad. | Indicó que usa vehículo principalmente los fines de semana, ha cancelado planes por no encontrar estacionamiento y valoró reservar antes de salir y extender una reserva. |
| TODO — entrevista adicional de conductor | — | Pendiente. | Se requiere para alcanzar el mínimo de tres entrevistas del segmento. |

**Estadística descriptiva transparente:** edades conocidas `n=2`; suma `50 + 25 = 75`; promedio `75 / 2 = 37.5 años`. Este promedio no representa a la población de conductores ni permite inferir porcentajes.

### Registro de entrevistas — propietarios

| Entrevistado | Edad | Evidencia registrada | Hallazgos descritos |
|---|---:|---|---|
| Jarol Saquiray Vargas | 24 | Resumen de entrevista; material audiovisual no se publica por privacidad. | Indicó que administra tres espacios de manera informal con conocidos y por WhatsApp. Señaló interés en publicar espacios y configurar horario y precio. |
| Dlan Garcia Levano | 23 | Resumen de entrevista; material audiovisual no se publica por privacidad. | Describió espacios de un edificio residencial sin gestión sistematizada y necesidad de habilitarlos o deshabilitarlos según horario, sin eliminarlos. |
| TODO — entrevista adicional de propietario | — | Pendiente. | Se requiere para alcanzar el mínimo de tres entrevistas del segmento. |

**Estadística descriptiva transparente:** edades conocidas `n=2`; suma `24 + 23 = 47`; promedio `47 / 2 = 23.5 años`. Este promedio no representa a la población de propietarios ni permite inferir porcentajes.

### Análisis de entrevistas y límites

| Tema | Indicio en la muestra | Implicancia de requisito | Límite |
|---|---|---|---|
| Búsqueda | Los dos resúmenes de conductores priorizan información antes de desplazarse. | US01–US04: búsqueda, disponibilidad, filtros y detalle. | Dos registros cualitativos; falta una entrevista. |
| Reserva | Un conductor menciona reservar y extender. | US05, US08 y reglas de disponibilidad. | No valida adopción ni frecuencia. |
| Gestión de oferta | Ambos propietarios describen una necesidad de control de espacios. | US09–US13: publicación, configuración, estado, reservas e ingresos. | Dos registros cualitativos; falta una entrevista. |
| Confianza operativa | Los flujos requieren confirmación y trazabilidad. | US14–US16, US20 y TS01/TS04/TS06. | Debe validarse con prototipos y pruebas técnicas. |

## 2.3 Needfinding

### Hallazgos priorizados

| Necesidad | Persona afectada | Oportunidad | Requisito relacionado |
|---|---|---|---|
| Evaluar opciones antes de llegar | Conductor | Presentar información de búsqueda y detalle de forma comprensible. | US01–US04 |
| Asegurar un intervalo de uso | Conductor | Solicitar reserva con confirmación y manejo de cancelación/extensión. | US05–US08 |
| Publicar y controlar oferta | Propietario | Registrar espacio, horarios, precio y estado. | US09–US12 |
| Conocer el resultado de operaciones | Ambos segmentos | Notificar confirmaciones y conservar comprobantes/historial. | US07, US13, US16, US20 |

### User Personas

Los perfiles son arquetipos de diseño construidos a partir de los patrones descritos. No representan personas reales completas ni atribuyen datos no declarados.

![Personas basadas en la muestra](docs/tb1/assets/user-personas.svg)

| Arquetipo | Objetivo | Frustración | Necesidad prioritaria |
|---|---|---|---|
| Conductor que planifica su llegada | Elegir un espacio antes de desplazarse. | Incertidumbre de encontrar lugar al llegar. | Comparar disponibilidad, precio y distancia; solicitar reserva. |
| Propietario que administra oferta | Controlar cuándo y cómo ofrece sus espacios. | Coordinación manual y escasa visibilidad. | Configurar horario, precio, estado y revisar reservas. |

### User Task Matrix

| Tarea | Conductor | Propietario | Riesgo que debe resolverse |
|---|---|---|---|
| Buscar una opción | Inicia por destino y revisa resultados. | No aplica. | La disponibilidad mostrada no equivale a una reserva. |
| Evaluar detalle | Revisa precio, horario, distancia y condiciones disponibles. | Mantiene información de su espacio. | Información incompleta o desactualizada. |
| Reservar | Define intervalo y confirma la solicitud. | Recibe el efecto de una reserva confirmada. | Conflicto de reserva concurrente. |
| Configurar oferta | No aplica. | Publica, fija horario/precio y cambia estado. | Efecto de cambios sobre reservas existentes. |
| Consultar resultado | Revisa historial, comprobante o aviso. | Revisa reservas e ingresos. | Trazabilidad y autorización. |

### Empathy Maps

![Empathy Maps de los arquetipos](docs/tb1/assets/empathy-maps.svg)

| Arquetipo | Piensa y siente | Ve y hace | Dolor | Ganancia esperada |
|---|---|---|---|---|
| Conductor | Necesita reducir incertidumbre antes del trayecto. | Busca opciones y compara información. | Tiempo y estrés asociados a la búsqueda. | Llegar con una opción evaluada y una confirmación trazable. |
| Propietario | Quiere mantener control sobre su oferta. | Coordina o administra espacios disponibles. | Gestión dispersa y poca visibilidad. | Actualizar reglas de oferta y conocer reservas. |

### As-Is Scenario Maps

![Escenarios actuales](docs/tb1/assets/as-is-scenarios.svg)

| Escenario | Inicio | Dificultad | Resultado actual |
|---|---|---|---|
| Conductor | Se aproxima a un destino. | No cuenta con certeza de espacio disponible. | Busca opciones manualmente; puede perder tiempo o cambiar el plan. |
| Propietario | Tiene un espacio potencialmente disponible. | Coordina disponibilidad y condiciones por canales manuales. | Menor control y visibilidad de la oferta. |

### Ubiquitous Language

| Término | Definición acordada para TB1 | No significa |
|---|---|---|
| Espacio | Unidad de estacionamiento que un propietario puede publicar. | Una reserva confirmada. |
| Disponibilidad | Estado consultable para un intervalo; puede cambiar. | Garantía definitiva de uso. |
| Reserva | Compromiso creado tras validar reglas del dominio. | Una simple búsqueda. |
| Intervalo | Fecha/hora de inicio y fin solicitada para una reserva. | Horario genérico del propietario. |
| Confirmación | Estado trazable de una operación aceptada. | Notificación sin operación registrada. |
| Pago | Operación gestionada por el contexto de pagos. | Acceso directo a datos bancarios. |
| Idempotencia | Repetir una solicitud no duplica su efecto de negocio. | Reintentar sin control. |
| Evento de dominio | Hecho de negocio publicado después de un cambio válido. | Comando o petición HTTP. |


# Capítulo III — Especificación

## 3.1 To-Be Scenario Mapping

![Escenarios objetivo](docs/tb1/assets/to-be-scenarios.svg)

| Escenario | Pasos propuestos | Resultado esperado | Condición de control |
|---|---|---|---|
| Conductor | Busca por destino, compara opciones, revisa detalle, solicita reserva, completa pago y recibe confirmación. | Cuenta con una reserva confirmada o recibe una respuesta clara de no disponibilidad. | La confirmación depende de validación de reserva y pago. |
| Propietario | Registra espacio, define horario/precio, habilita oferta, revisa reserva y consulta movimientos. | Gestiona la oferta sin eliminarla cuando cambia temporalmente su disponibilidad. | Los cambios deben respetar las reservas ya confirmadas. |

## 3.2 Épicas

| ID | Épica | Propósito |
|---|---|---|
| EP01 | Búsqueda y descubrimiento de estacionamientos | Ayudar al conductor a localizar y evaluar opciones. |
| EP02 | Reserva y gestión de reservas | Mantener el ciclo de vida de una reserva sin conflictos. |
| EP03 | Publicación y gestión de espacios | Permitir al propietario administrar la oferta. |
| EP04 | Pagos y facturación | Gestionar cobros, reembolsos y comprobantes. |
| EP05 | Gestión de cuenta y autenticación | Registrar, autenticar y autorizar usuarios por rol. |
| EP06 | Notificaciones y comunicación | Informar eventos relevantes de forma trazable. |

## 3.3 User Stories

Las prioridades se expresan como **Must**, **Should** y **Could** para planificación de TB1; no acreditan implementación.

| ID | Prioridad | Historia | Criterio de aceptación verificable |
|---|---|---|---|
| US01 | Must | Como conductor, deseo buscar estacionamientos cerca de mi destino para planificar la llegada. | Dado un destino, cuando busco, entonces se muestran opciones disponibles con la información que el sistema tenga para precio, horario y distancia. |
| US02 | Must | Como conductor, deseo consultar disponibilidad para evitar elegir un espacio ocupado. | Dada una opción, cuando consulto un intervalo, entonces el sistema responde disponibilidad consultable y aclara que puede cambiar hasta confirmar. |
| US03 | Should | Como conductor, deseo filtrar opciones por precio y horario para comparar alternativas. | Dada una búsqueda, cuando aplico filtros soportados, entonces solo se muestran opciones que cumplen los criterios. |
| US04 | Should | Como conductor, deseo ver el detalle de un espacio para decidir informado. | Dada una opción, cuando abro el detalle, entonces se muestran los datos publicados disponibles, incluidas condiciones y horario. |
| US05 | Must | Como conductor, deseo reservar un espacio para asegurar un intervalo de uso. | Dado un espacio disponible, cuando confirmo un intervalo válido, entonces se crea una reserva o se informa que no puede confirmarse. |
| US06 | Should | Como conductor, deseo cancelar una reserva para liberar el espacio si ya no lo necesito. | Dada una reserva cancelable según política pendiente de definir, cuando la cancelo, entonces cambia su estado y se ejecuta el flujo aplicable. |
| US07 | Could | Como conductor, deseo consultar mi historial de reservas para revisar operaciones anteriores. | Dado un usuario autenticado, cuando abre su historial, entonces ve únicamente sus reservas autorizadas. |
| US08 | Should | Como conductor, deseo extender una reserva activa para solicitar más tiempo. | Dada una reserva activa, cuando solicito extensión, entonces el sistema valida el intervalo adicional antes de confirmar cualquier cambio. |
| US09 | Must | Como propietario, deseo registrar un espacio para ofrecerlo. | Dado un propietario autenticado, cuando completa los datos mínimos definidos, entonces el espacio queda registrado bajo su control. |
| US10 | Must | Como propietario, deseo configurar horario y precio para controlar la oferta. | Dado un espacio propio, cuando cambio horario o precio, entonces se valida la regla y el cambio queda trazado para futuras disponibilidades. |
| US11 | Must | Como propietario, deseo habilitar o deshabilitar un espacio temporalmente. | Dado un espacio propio, cuando cambio su estado, entonces la oferta futura se actualiza sin eliminar el registro ni invalidar reservas confirmadas. |
| US12 | Should | Como propietario, deseo ver reservas activas de mi espacio para administrarlo. | Dado un propietario autenticado, cuando consulta su espacio, entonces ve solo reservas asociadas a sus espacios. |
| US13 | Could | Como propietario, deseo consultar el historial de ingresos para revisar resultados. | Dado un rango y un propietario autorizado, cuando consulta movimientos, entonces se muestran operaciones registradas bajo reglas de visibilidad definidas. |
| US14 | Must | Como conductor, deseo pagar una reserva para completar la transacción. | Dada una reserva apta para pago, cuando el proveedor confirma el cobro, entonces el sistema registra un único resultado de pago. |
| US15 | Should | Como conductor, deseo solicitar un reembolso aplicable a una cancelación. | Dada una cancelación elegible por política pendiente, cuando se solicita el reembolso, entonces se registra su estado sin duplicar la operación. |
| US16 | Should | Como conductor, deseo ver un comprobante de pago para tener respaldo. | Dado un pago registrado y autorizado, cuando solicito comprobante, entonces se presenta el detalle disponible de esa operación. |
| US17 | Must | Como conductor, deseo registrarme para usar funcionalidades protegidas. | Dado un formulario válido, cuando completo el registro, entonces se crea una cuenta con rol de conductor. |
| US18 | Must | Como propietario, deseo registrarme para publicar espacios. | Dado un formulario válido y requisitos de verificación por definir, cuando completo el registro, entonces se crea una cuenta con rol de propietario. |
| US19 | Must | Como usuario registrado, deseo iniciar sesión para acceder según mi rol. | Dadas credenciales válidas, cuando inicio sesión, entonces se emite una sesión autorizada; con credenciales inválidas se rechaza sin revelar información sensible. |
| US20 | Should | Como conductor, deseo recibir una notificación de reserva confirmada. | Dada una reserva confirmada, cuando se publica el evento correspondiente, entonces se intenta generar una notificación trazable sin alterar la reserva. |

### Evidencia de landing page

El alcance solicita considerar una landing page. No existe evidencia suficiente en TB1 para declarar su contenido, comportamiento o implementación. Se registra como **brecha de evidencia**: definir objetivo, audiencia, mensajes, prototipo, métricas y criterio de aceptación antes de incorporarla al backlog de entrega.

## 3.4 Technical Stories

| ID | Prioridad | Necesidad técnica | Criterio de aceptación |
|---|---|---|---|
| TS01 | Must | Control transaccional de reservas concurrentes. | Dos solicitudes incompatibles para el mismo espacio e intervalo no dejan más de una reserva confirmada. |
| TS02 | Must | Proyección de disponibilidad para búsqueda rápida. | Un cambio válido de disponibilidad actualiza la proyección; PostgreSQL conserva la fuente de verdad. |
| TS03 | Must | Autenticación y autorización por roles. | Un token y rol válido permiten solo acciones autorizadas; el acceso no autorizado se rechaza. |
| TS04 | Must | Auditoría de reservas, pagos, reembolsos y disponibilidad. | Toda operación crítica confirmada produce un registro de auditoría con actor, acción, entidad y fecha. |
| TS05 | Should | Almacenamiento de fotos mediante object storage compatible con S3. | Las imágenes se gestionan mediante URLs controladas y permisos definidos, sin exponer credenciales. |
| TS06 | Must | Idempotencia de pagos y webhooks. | La repetición del mismo identificador o clave no duplica el cobro ni la transición de estado. |
| TS-AI01 | Should | Interpretación controlada de intención de estacionamiento. | El AI Agent transforma lenguaje natural en parámetros validados o solicita aclaración; no consulta bases de datos directamente. |
| TS-AI02 | Should | Herramientas permitidas para el AI Agent. | El agente solo puede invocar `searchParking()`, `getParkingDetails()`, `checkAvailability()`, `calculateDistance()` y `getReservationOptions()` mediante interfaces autenticadas. |
| TS-AI03 | Should | Trazabilidad y seguridad de interacción AI. | Cada invocación guarda correlación, herramienta, resultado resumido y resultado de autorización, sin registrar secretos. |
| TS-MSG01 | Must | Publicación confiable de eventos de dominio. | Un cambio confirmado usa outbox o mecanismo equivalente para publicar eventos sin perder el vínculo con la transacción. |
| TS-MSG02 | Must | Consumo idempotente y reintentos. | Un consumidor reconoce mensajes repetidos, reintenta fallos transitorios y envía fallos agotados a DLQ. |
| TS-MSG03 | Must | Correlación de operaciones distribuidas. | Comandos, eventos y notificaciones transportan un `correlationId` para seguir una operación. |
| TS-OBS01 | Should | Observabilidad distribuida. | Las solicitudes y mensajes producen logs estructurados y trazas con identificador de correlación. |
| TS-SEC01 | Must | Protección de servicios y datos. | Todo tráfico externo usa HTTPS; los servicios verifican identidad, rol y autorización de recurso antes de ejecutar comandos. |
| TS-GW01 | Must | API Gateway para tráfico síncrono. | El gateway enruta APIs REST/HTTPS, valida tokens y aplica límites o políticas sin contener reglas de dominio. |

## 3.5 Impact Mapping

![Impact Map de ParkLink](docs/tb1/assets/impact-map.svg)

| Objetivo de producto sin métrica aún validada | Actor | Cambio de comportamiento buscado | Entregables vinculados |
|---|---|---|---|
| Reducir incertidumbre antes de buscar estacionamiento | Conductor | Evalúa una opción antes de desplazarse. | US01–US05, US20; TS01–TS03. |
| Dar control a la oferta de estacionamientos | Propietario | Configura y administra su espacio con reglas explícitas. | US09–US13, US18; TS04–TS06. |
| Mantener una operación confiable | Ambos | Recibe resultados trazables de reservas y pagos. | US05–US08, US14–US16; TS01, TS04, TS06, TS-MSG01–03, TS-SEC01. |

## 3.6 Product Backlog actualizado

| Orden | Ítem | Prioridad | Dependencia principal |
|---:|---|---|---|
| 1 | US17, US18, US19 | Must | TS03, TS-SEC01, TS-GW01 |
| 2 | US09, US10, US11 | Must | TS04 |
| 3 | US01, US02 | Must | TS02, TS-GW01 |
| 4 | US05 | Must | TS01, TS04, TS-MSG01, TS-MSG03 |
| 5 | US14 | Must | TS06, TS-MSG01–03 |
| 6 | US03, US04 | Should | US01–US02 |
| 7 | US12, US20 | Should | TS-MSG02–03 |
| 8 | US06, US08, US15, US16 | Should | TS01, TS06 |
| 9 | US07, US13 | Could | Autorización y auditoría |
| 10 | TS-AI01, TS-AI02, TS-AI03, TS-OBS01 | Should | TS-GW01, TS-SEC01, TS-MSG03 |
| 11 | Landing page | Pendiente | Brecha de evidencia documentada; no planificar sin definición validada. |

