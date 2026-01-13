# Guía de Usuario - Administrador CIAT

Sistema de Validación de TIN - CRS-CIAT

> Esta guía está destinada únicamente a usuarios autorizados.

## Navegación Rápida

- [Estadísticas](#estadísticas)
- [Gestionar Países](#gestionar-países)
- [Definiciones de Nivel por País](#definiciones-de-nivel-por-país)
- [Configuración de Reglas Nivel 1](#configuración-de-reglas-nivel-1)
- [Salud del Sistema](#salud-del-sistema)

## Estadísticas

### Panel de Resumen
El panel de estadísticas proporciona información en tiempo real sobre el uso y rendimiento del sistema.

### Métricas Principales:
- **Validaciones Totales**: Número de TINs validados (diario, semanal, mensual)
- **Tasa de Éxito**: Porcentaje de validaciones exitosas
- **Actividad por País**: Volumen de validaciones por país participante
- **Uso de API**: Número de llamadas API vs uso de interfaz web
- **Horas Pico**: Patrones de carga del sistema durante el día

### Generar Reportes:
1. Navegar a "Estadísticas" → "Reportes"
2. Seleccionar tipo de reporte (Resumen, Detallado, Personalizado)
3. Elegir rango de fechas
4. Seleccionar países (opcional)
5. Hacer clic en "Generar Reporte"
6. Exportar a PDF, Excel o CSV

### Monitoreo en Tiempo Real:
- Contador de validaciones en vivo
- Gráficos de tiempo de respuesta API
- Monitoreo de tasa de errores
- Seguimiento de actividad de usuarios

## Gestionar Países

### Agregar Nuevo País:
1. Ir a "Países" → "Agregar Nuevo País"
2. Ingresar información del país:
   - Código de País (ISO 3166-1 alpha-2)
   - Nombre del País (nombre oficial)
   - Nombre de la Autoridad Tributaria
   - Información de Contacto
   - Estado (Activo/Inactivo)
3. Cargar bandera/logo del país (opcional)
4. Hacer clic en "Guardar"

### Gestión de Estado del País:
- **Activo**: El país puede participar en validaciones
- **Inactivo**: País suspendido temporalmente
- **Pendiente**: Esperando aprobación/configuración
- **Retirado**: Ya no participa

### Operaciones Masivas:
- Importar lista de países via CSV
- Actualizar múltiples países simultáneamente
- Exportar configuración de países

## Definiciones de Nivel por País

### Tipos de Acuerdos:
1. **Acuerdos Bilaterales**: Validación directa entre dos países
2. **Acuerdos Multilaterales**: Múltiples países bajo marco común
3. **Acceso Unilateral**: El país puede validar pero no ser validado

### Configurar Acuerdos:
1. Seleccionar "Acuerdos" del menú principal
2. Elegir tipo de acuerdo
3. Seleccionar países participantes
4. Definir niveles de validación (1, 2 o 3)
5. Establecer fechas efectivas
6. Configurar reglas de notificación

### Niveles de Validación:
- **Nivel 1**: Solo validación de formato
- **Nivel 2**: Verificación básica de existencia
- **Nivel 3**: Validación completa con detalles del contribuyente

### Monitoreo de Acuerdos:
- Seguir fechas de expiración de acuerdos
- Monitorear uso contra cuotas
- Generar reportes de cumplimiento
- Enviar recordatorios de renovación

## Configuración de Reglas Nivel 1

### Tipos de Reglas:
1. **Reglas de Formato**: Validación de estructura de TIN
2. **Reglas de Dígito de Control**: Validación matemática
3. **Reglas de Longitud**: Conteo mínimo/máximo de caracteres
4. **Reglas de Patrón**: Coincidencia de expresiones regulares

### Crear Reglas de Formato:

Nombre de Regla: Formato_TIN_US
País: Estados Unidos
Tipo de Regla: Patrón
Patrón: ^[0-9]{3}-[0-9]{2}-[0-9]{4}$
Descripción: Valida formato XXX-XX-XXXX


### Prioridad de Reglas:
1. Reglas específicas por país
2. Reglas regionales (si aplica)
3. Reglas globales predeterminadas

### Probar Reglas:
1. Ir a "Reglas" → "Probar Reglas"
2. Ingresar TINs de prueba
3. Seleccionar país
4. Ejecutar validación
5. Revisar resultados y aplicación de reglas

### Mantenimiento de Reglas:
- Control de versiones para cambios de reglas
- Registro de auditoría de modificaciones
- Capacidad de reversión
- Actualizaciones programadas de reglas

## Salud del Sistema

### Panel de Monitoreo:
- **Tiempo de Actividad del Sistema**: Disponibilidad actual e histórica
- **Rendimiento de API**: Tiempos de respuesta y tasas de éxito
- **Salud de Base de Datos**: Estado de conexión y rendimiento
- **Recursos del Servidor**: Uso de CPU, memoria y disco
- **Estado de Red**: Conectividad y latencia

### Verificaciones de Salud:
1. **Conectividad de Base de Datos**: Verificar todas las conexiones de base de datos
2. **Endpoints de API**: Probar todos los endpoints de API
3. **Servicios Externos**: Verificar integraciones con terceros
4. **Validez de Certificados**: Verificar certificados SSL/TLS
5. **Estado de Copias de Seguridad**: Confirmar completación de backups

### Configuración de Alertas:
1. Navegar a "Salud" → "Alertas"
2. Establecer umbrales para:
   - Uso de CPU (>80%)
   - Uso de memoria (>85%)
   - Espacio en disco (<10% libre)
   - Errores de API (>5% tasa de error)
   - Tiempo de respuesta (>5 segundos)
3. Configurar canales de notificación:
   - Alertas por correo
   - Notificaciones SMS
   - Advertencias en panel

### Tareas de Mantenimiento:
- **Diarias**: Rotación de logs, limpieza de archivos temporales
- **Semanales**: Optimización de base de datos, generación de reportes
- **Mensuales**: Backup completo del sistema, verificaciones de renovación de certificados
- **Trimestrales**: Auditoría de seguridad, revisión de rendimiento

### Respuesta a Incidentes:
1. **Detección**: Alertas del sistema o reportes de usuarios
2. **Evaluación**: Determinar severidad y alcance
3. **Contención**: Aislar componentes afectados
4. **Resolución**: Aplicar correcciones o soluciones alternativas
5. **Recuperación**: Restaurar operaciones normales
6. **Revisión**: Analizar causa raíz y prevenir recurrencia

---

*Para emergencias del sistema, contacte al soporte técnico de CIAT inmediatamente: ciat.emergencia@ciat.org*