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

