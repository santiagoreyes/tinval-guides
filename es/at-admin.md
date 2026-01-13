# Guía de Usuario - Administrador de Autoridad Tributaria

Sistema de Validación de TIN - CRS-CIAT

> Para usuarios autorizados únicamente.

## Navegación Rápida

- [Estadísticas](#estadísticas)
- [Cargar Certificado](#cargar-certificado)
- [Gestionar Usuarios](#gestionar-usuarios)
- [Configuración de API](#configuración-de-api)

## Estadísticas

*(Agrega aquí tu contenido, capturas de pantalla, pasos, etc.)*

## Cargar Certificado

### Proceso para cargar certificado público:

1. Navegar a la sección "Certificados" en el menú principal
2. Hacer clic en "Subir Certificado"
3. Seleccionar el archivo `public_cert.pem`
4. Verificar que el certificado sea válido
5. Hacer clic en "Guardar"

### Requisitos del certificado:
- Formato: PEM (Privacy Enhanced Mail)
- Algoritmo: RSA con mínimo 2048 bits
- Certificado público solamente (no incluir clave privada)
- Máximo tamaño: 5KB

### Verificación del certificado:
El sistema validará automáticamente:
- Formato correcto del certificado
- Fecha de expiración (mínimo 30 días de validez)
- Estructura de clave RSA válida

## Gestionar Usuarios

### Crear nuevo usuario:

1. Ir a "Gestión de Usuarios"
2. Hacer clic en "Nuevo Usuario"
3. Completar los campos obligatorios:
   - Nombre completo
   - Correo electrónico
   - Rol (Seleccionar: USUARIO, AT_ADMIN, CIAT_ADMIN)
   - País asignado
4. Hacer clic en "Crear Usuario"

### Permisos por rol:

- **USUARIO**: Validar TINs individuales y por lote, ver resultados
- **AT_ADMIN**: Gestionar usuarios, cargar certificados, configuración API, ver estadísticas
- **CIAT_ADMIN**: Todas las funciones del sistema, administración global

### Restablecer contraseña:

1. Buscar usuario en la lista
2. Hacer clic en "Acciones" → "Restablecer Contraseña"
3. El sistema generará una contraseña temporal
4. Enviar la nueva contraseña al usuario por correo seguro

## Configuración de API

### Endpoints disponibles:

- **Validación individual**: `POST /api/v1/validate/single`
- **Validación por lote**: `POST /api/v1/validate/batch`
- **Consulta de resultados**: `GET /api/v1/results/{id}`

### Configurar límites de tasa:

1. Navegar a "Configuración API"
2. Establecer límites por usuario:
   - Máximo de solicitudes por minuto
   - Máximo de TINs por lote
   - Tiempo de espera máximo
3. Guardar configuración

### Monitoreo de API:

El sistema proporciona:
- Métricas de uso en tiempo real
- Logs de errores y accesos
- Alertas de sobrecarga
- Reportes de actividad diaria/semanal/mensual

### Pruebas de conexión:

Para verificar la conectividad API:
1. Ir a "Herramientas" → "Prueba de Conexión"
2. Seleccionar endpoint a probar
3. Hacer clic en "Probar Conexión"
4. Verificar respuesta y tiempo de respuesta

---

*Para asistencia técnica, contacte al equipo de soporte: support.tinvalidator@ciat.org*