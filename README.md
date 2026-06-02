# Ejercicio Cloud — Grupo Demo ESTILA

## 1. Nuestros datos

- Grupo: Demo docente
- Integrantes: Equipo ESTILA
- Fecha: 2026

---

## 2. Nuestra infraestructura Liferay actual (on-premise)

Actualmente ESTILA trabaja con una plataforma Liferay instalada en infraestructura propia, en modalidad on-premise.

El equipo técnico gestiona directamente gran parte de la pila tecnológica: servidores, sistema operativo, base de datos, actualizaciones, copias de seguridad, certificados, monitorización y resolución de incidencias.

La infraestructura actual puede resumirse así:

- **Servidor de aplicaciones:** Liferay ejecutándose sobre servidores gestionados internamente.
- **Base de datos:** Oracle administrada por el equipo técnico o por los equipos internos responsables.
- **Almacenamiento:** almacenamiento corporativo/local para documentos, ficheros, contenidos y recursos asociados al portal.
- **Copias de seguridad:** backups gestionados desde el entorno interno, con procedimientos propios de respaldo y restauración.
- **Seguridad:** certificados SSL, accesos, firewall, permisos y configuraciones bajo responsabilidad interna.
- **Operación:** monitorización de CPU, memoria, disponibilidad, logs, incidencias y rendimiento realizada por el equipo técnico.
- **Escalado:** ampliación de capacidad mediante cambios de infraestructura, servidores, recursos o configuración manual.

Este modelo ofrece control completo, pero también implica una carga operativa elevada. Cada cambio técnico requiere planificación, mantenimiento y validación interna.

---

## 3. Tabla de responsabilidades: quién hace qué

> La siguiente tabla compara cómo cambia la responsabilidad según el modelo elegido: on-premise, IaaS, PaaS o SaaS.

| Tarea | On-Premise | IaaS | PaaS | SaaS |
|---|---|---|---|---|
| Instalar el sistema operativo del servidor | Nosotros | Nosotros | Proveedor | Proveedor |
| Aplicar parches de seguridad del sistema operativo | Nosotros | Nosotros | Proveedor | Proveedor |
| Actualizar Liferay a una nueva versión | Nosotros | Nosotros | Compartido / Proveedor | Proveedor |
| Gestionar backups de la base de datos | Nosotros | Nosotros | Proveedor / Compartido | Proveedor |
| Renovar certificados SSL / HTTPS | Nosotros | Nosotros | Proveedor / Compartido | Proveedor |
| Escalar el servidor en picos de tráfico | Nosotros | Nosotros | Proveedor / Automatizado | Proveedor |
| Monitorizar CPU y memoria del servidor | Nosotros | Nosotros | Proveedor / Cliente | Proveedor |
| Configurar el firewall y la red | Nosotros | Nosotros | Proveedor / Cliente | Proveedor |
| Instalar y configurar el balanceador de carga | Nosotros | Nosotros | Proveedor | Proveedor |
| Gestionar el motor de búsqueda Elasticsearch | Nosotros | Nosotros | Proveedor / Compartido | Proveedor |
| Gestionar usuarios y permisos funcionales | Nosotros | Nosotros | Nosotros | Nosotros |
| Proteger los datos de negocio | Nosotros | Nosotros | Nosotros | Nosotros |
| Definir roles, accesos y gobierno | Nosotros | Nosotros | Nosotros | Nosotros |
| Validar que la aplicación funciona correctamente | Nosotros | Nosotros | Nosotros | Nosotros |
| Revisar integraciones con otros sistemas | Nosotros | Nosotros | Nosotros | Nosotros |
| Cumplir normativa y políticas internas | Nosotros | Nosotros | Nosotros | Nosotros |

---

## 4. Análisis de cada modelo

### On-Premise

En el modelo on-premise, ESTILA mantiene el control completo sobre la infraestructura, pero también asume prácticamente toda la responsabilidad técnica.

Esto incluye:

- servidores físicos o virtualizados;
- sistema operativo;
- base de datos;
- almacenamiento;
- red;
- firewall;
- certificados;
- backups;
- balanceadores;
- actualizaciones;
- monitorización;
- seguridad;
- continuidad del servicio.

La ventaja principal es el control. La desventaja es la carga operativa: el equipo debe mantener muchas capas técnicas que no siempre aportan valor directo al negocio.

---

### IaaS — Infrastructure as a Service

En IaaS, el proveedor cloud ofrece infraestructura básica: máquinas virtuales, almacenamiento, red y capacidad bajo demanda.

ESTILA dejaría de gestionar el hardware físico, pero seguiría teniendo mucha responsabilidad sobre:

- sistema operativo;
- parches;
- configuración de servidores;
- instalación de Liferay;
- base de datos si no se usa como servicio gestionado;
- backups;
- seguridad lógica;
- monitorización;
- escalado;
- configuración de red.

IaaS puede ser útil para una primera migración tipo "lift and shift", pero no elimina por completo la carga operativa. En muchos casos, simplemente cambia el lugar donde están los servidores.

---

### PaaS — Platform as a Service

En PaaS, el proveedor gestiona muchas más capas técnicas. El equipo ya no se centra tanto en servidores, sistema operativo o runtime, sino en la aplicación, los datos, la configuración y el gobierno.

Para ESTILA, un modelo tipo Liferay DXP Cloud tendría sentido porque:

- reduce la gestión directa de infraestructura;
- mantiene capacidad de personalización sobre Liferay;
- permite trabajar con despliegues más controlados;
- facilita automatización, escalado y operación;
- reduce tareas repetitivas de mantenimiento técnico;
- permite al equipo centrarse más en el portal, las integraciones y la evolución funcional.

En PaaS, ESTILA seguiría siendo responsable de aspectos clave:

- configuración funcional de Liferay;
- datos;
- usuarios y permisos;
- integraciones;
- validación de despliegues;
- cumplimiento normativo;
- gobierno;
- seguridad lógica;
- calidad del servicio.

PaaS no significa “el proveedor lo hace todo”. Significa que el proveedor asume más capas técnicas, pero el cliente sigue gobernando el uso correcto de la plataforma.

---

### SaaS — Software as a Service

En SaaS, el proveedor gestiona prácticamente toda la aplicación. El cliente accede al software por navegador y configura usuarios, permisos y opciones funcionales.

Este modelo reduce mucho la operación técnica, pero también limita la personalización.

Para ESTILA, SaaS podría no ser el modelo más adecuado si necesita mantener una plataforma Liferay personalizada, con desarrollos propios, integraciones específicas y control sobre la evolución del portal.

SaaS sería más adecuado para herramientas estándar como correo, CRM, gestión documental o aplicaciones corporativas cerradas, pero no necesariamente para un portal Liferay altamente adaptado.

---

## 5. Nuestra recomendación para ESTILA

**Modelo elegido:** PaaS

Recomendamos un modelo **PaaS**, orientado a Liferay DXP Cloud o a una plataforma gestionada equivalente, porque ofrece un equilibrio razonable entre control técnico y reducción de carga operativa.

ESTILA tiene experiencia técnica en Liferay on-premise, pero todavía no tiene experiencia real en cloud. Por eso, un modelo PaaS permitiría evolucionar hacia la nube sin trasladar toda la complejidad del modelo actual.

---

## 6. Por qué recomendamos PaaS

Recomendamos PaaS por los siguientes motivos:

1. **Reduce la carga operativa del equipo técnico**

   El equipo dejaría de gestionar directamente servidores, sistema operativo, parte de los parches, balanceadores, escalado y ciertas tareas de infraestructura.

2. **Mantiene capacidad de personalización**

   A diferencia de un SaaS cerrado, un modelo PaaS permite seguir trabajando sobre una plataforma Liferay personalizada.

3. **Facilita la migración progresiva**

   Permite pasar de un modelo on-premise a un entorno cloud sin rediseñar todo desde cero en una primera fase.

4. **Mejora la escalabilidad**

   El entorno cloud puede adaptarse mejor a picos de demanda, crecimiento de usuarios o nuevas necesidades del servicio.

5. **Introduce prácticas modernas de despliegue**

   El trabajo con repositorios, ramas, control de cambios y despliegues automatizados ayuda a profesionalizar la operación.

6. **Permite mejorar seguridad y gobierno**

   El modelo cloud facilita aplicar controles de acceso, trazabilidad, auditoría, MFA, políticas de despliegue y separación de responsabilidades.

---

## 7. Tareas que dejaríamos de gestionar directamente

Con un modelo PaaS, ESTILA dejaría de gestionar directamente muchas tareas de infraestructura, entre ellas:

- instalación del sistema operativo;
- aplicación de parches del sistema operativo;
- gestión física o virtual de servidores;
- parte de la configuración base del entorno;
- instalación manual de balanceadores;
- escalado básico de infraestructura;
- mantenimiento de capas técnicas inferiores;
- parte de la monitorización de infraestructura;
- parte de la gestión de certificados;
- parte de la operación del motor de búsqueda si está gestionado por la plataforma;
- parte de los backups técnicos de base de datos y plataforma.

Esto liberaría tiempo del equipo técnico para centrarse en tareas de mayor valor.

---

## 8. Tareas que seguiríamos gestionando nosotros

Aunque se migre a cloud, ESTILA seguiría teniendo responsabilidades importantes:

- configuración funcional de Liferay;
- gestión de usuarios y permisos;
- control de accesos;
- gobierno de datos;
- cumplimiento normativo;
- validación de despliegues;
- pruebas funcionales;
- revisión de integraciones;
- definición de políticas de seguridad;
- supervisión del servicio;
- análisis de logs funcionales;
- gestión de incidencias;
- coordinación con el proveedor;
- revisión de costes;
- documentación técnica;
- planificación de cambios.

La nube no elimina la responsabilidad del equipo. La transforma.

---

## 9. Riesgos a tener en cuenta

Antes de migrar, ESTILA debería analizar varios riesgos:

### Dependencias actuales

Es necesario identificar qué sistemas se conectan actualmente con Liferay:

- bases de datos;
- servicios internos;
- autenticación;
- integraciones Java;
- APIs;
- procesos batch;
- almacenamiento de documentos;
- sistemas de búsqueda;
- herramientas de monitorización.

### Datos

Hay que revisar:

- volumen de datos;
- sensibilidad de la información;
- requisitos de protección;
- políticas de retención;
- copias de seguridad;
- restauración;
- residencia del dato.

### Seguridad

Será necesario definir:

- quién puede acceder;
- qué permisos tiene cada rol;
- si se exige MFA;
- cómo se auditan los cambios;
- cómo se protegen las credenciales;
- cómo se gestionan secretos y certificados.

### Costes

El cloud permite pagar por uso, pero también puede generar costes inesperados si no se gobierna correctamente.

Habrá que controlar:

- cómputo;
- almacenamiento;
- tráfico de red;
- backups;
- logs;
- entornos de desarrollo y prueba;
- licencias;
- servicios gestionados.

### Operación

Migrar a cloud obliga a revisar cómo se opera el entorno:

- monitorización;
- alertas;
- RPO;
- RTO;
- continuidad;
- recuperación ante desastre;
- gestión de cambios;
- rollback;
- despliegues.

---

## 10. Conclusión del grupo

La migración de ESTILA a cloud no debe entenderse como “mover servidores a otro sitio”.

Debe entenderse como un cambio de modelo operativo.

En on-premise, ESTILA gestiona casi toda la pila tecnológica.

En IaaS, parte de la infraestructura física pasa al proveedor, pero el equipo sigue gestionando muchas capas técnicas.

En PaaS, el proveedor asume más responsabilidad sobre la plataforma y la infraestructura, mientras ESTILA mantiene el control sobre aplicación, datos, configuración, integraciones y gobierno.

En SaaS, la operación técnica se reduce mucho, pero también se reduce la capacidad de personalización.

Por el contexto actual de ESTILA, el modelo más equilibrado parece ser **PaaS**, especialmente si la evolución natural del fabricante apunta hacia Liferay DXP Cloud.

La decisión final deberá validarse cuando exista un entorno real, una arquitectura definida, requisitos de seguridad, análisis de costes y roadmap de migración.

---

## 11. Frase clave del ejercicio

> Cloud no significa dejar de tener responsabilidades.  
> Cloud significa cambiar qué responsabilidades gestionamos nosotros y cuáles delegamos en el proveedor.
