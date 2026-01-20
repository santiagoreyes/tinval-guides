# Guía de Usuario - Administrador de Autoridad Tributaria

Sistema de Validación de TIN - CRS-CIAT

> Para usuarios autorizados únicamente.

## Navegación Rápida

- [Estadísticas](#estadísticas)
- [Subir Certificado](#cargar-certificado)
- [Gestionar Usuarios](#gestionar-usuarios)
- [Configuración de API](#configuración-de-api)

## Estadísticas
Puede generar informe usando los diferentes filtros de: informe, fecha inicio, fecha fin, nivel periódo, país destino, país origen. Solo se pueden ver datos donde el país esté involucrado como Origen o Destino.

### Pasos
1. Navegue en la sección "Estadíscas" en el menú principal.
2. Elija los diferentes filtros a su disposición.
3. Presione en "Generar Informe" se deplegara la información solicitada.
4. Puede "Descargar" el Informe.

![Estadísticas](AT-ADMIN_EstadisticasAdmin_01.png)

## Subir Certificado
El administrador debera ingresar los datos del cliente asi como el certificado segun las especificaciones solicitadas. Tambien podra actualizar el certificado.

### Proceso para subir certificado público:

1. Navegar a la sección "Subir Certificado" en el menú principal
2. Ingrese el nombre del Cliente
3. Ingrese el correo del Cliente
4. Seleccionar el archivo `public_cert.pem`
5. Verificar que el certificado sea válido
6. Hacer clic en "Registrar Cliente".

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
  
![Subir Certificado](AT-ADMIN_SubirCertificado_01.png)

## Gestionar Usuarios
El administrador podra crear usuarios nuevos o editar los datos de los usarios ya creados. Tambien puede desahabiltar usuarios.

### Crear nuevo usuario:

1. Ir a "Gestión de Usuarios"
3. Completar la información en "Crear Nuevo Usuario" con los campos obligatorios:
   - Nombre
   - Apellido
   - Correo electrónico
   - Contraseña
   - Confirma Contraseña
4. Hacer clic en "Crear Usuario"

![Gestionar Usuarios](AT-ADMIN_GestionarUsuario_01.png)

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

![Configuración de API](AT-ADMIN_ConfiguracionApi_01.png)

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
