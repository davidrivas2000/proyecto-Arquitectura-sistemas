# Requerimientos no funcionales

| # | Atributo | Métrica | Umbral | Condición de carga | Verificación | Consecuencia si no se cumple |
|---|---|---|---|---|---|---|
| 1 | Rendimiento | p95 de latencia de las solicitudes | Menor a 400 ms | 200 usuarios concurrentes | Prueba de carga | El usuario abandona la reserva |
| 2 | Disponibilidad | Porcentaje de disponibilidad mensual | Igual o superior a 99.5 % | Operación continua durante el mes | Monitoreo de disponibilidad | El servicio no está disponible para los usuarios |
| 3 | Seguridad | Porcentaje de solicitudes protegidas por autenticación y autorización | 100 % en endpoints privados | Tráfico normal y pruebas de acceso no autorizado | Pruebas de seguridad automatizadas | Se expone información o se permite una operación no autorizada |

## Escenarios completos

### Escenario 1: Rendimiento

- Fuente: Usuario de la aplicación
- Estímulo: Envía una solicitud de consulta
- Artefacto: API de la aplicación
- Entorno: 200 usuarios concurrentes
- Respuesta: La API procesa y devuelve el resultado
- Medida: El p95 de latencia es menor a 400 ms

### Escenario 2: Disponibilidad

- Fuente: Monitor de operación
- Estímulo: Verifica periódicamente el servicio
- Artefacto: Servicio desplegado
- Entorno: Operación continua durante el mes
- Respuesta: El servicio responde correctamente
- Medida: La disponibilidad mensual es igual o superior a 99.5 %

### Escenario 3: Seguridad

- Fuente: Usuario autenticado o cliente no autorizado
- Estímulo: Solicita acceso a un endpoint privado
- Artefacto: API de la aplicación
- Entorno: Tráfico normal y pruebas de acceso no autorizado
- Respuesta: Se valida la identidad y los permisos antes de procesar la solicitud
- Medida: El 100 % de los endpoints privados rechaza solicitudes sin autorización válida