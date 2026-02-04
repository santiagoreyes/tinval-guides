# Guía de Usuario

Sistema de Validación de TIN - CRS-CIAT

> Esta guía está destinada únicamente a usuarios autorizados.

Guias Previas: [Guía de Acceso](./access.md)

## Navegación Rápida

- [Comenzando](#comenzando)
- [Proceso de Validación](#proceso-de-validación)  
- [Preguntas Frecuentes](#preguntas-frecuentes)

## Comenzando

### ¿Cómo funciona el Validador de TIN?
- Sistema basado en la nube gestionado por Ciat
- Los países pueden inscribirse para usar el sistema siguiendo el proceso definido.
- Los países pueden validar lotes de TINs usando un endpoint de API o una interfaz web.

### ¿Cómo funciona la Seguridad?
- Seguridad de API basada en Oauth2 con Certificados Auto-firmados
- Seguridad web basada en inicio de sesión y contraseña segura.

### ¿Quién puede acceder al Sistema?
- Usuario de Administración del País, para gestionar usuarios, cargar certificados públicos, definir endpoints de API.
- Usuarios de API (basados en acceso por token), para validar lotes de TINs.
- Usuarios web, para validar TINs individuales, lotes de TINs, y ver resultados de validación.
- Administrador de Ciat, para tareas de administración y configuración del sistema, también para ver estadísticas.

## Proceso de Validación

### Guía Paso a Paso

**Flujo de Procesamiento de Lotes de TINs:**

1. **Envío del Lote**
   - El usuario envía un archivo por lotes (batch) con TINs para validar
   - Métodos de envío disponibles:
     - Portal web
     - API del sistema

2. **Validación Inicial del Archivo**
   - El sistema verifica:
     - ✅ Estructura del archivo
     - ✅ Reglas básicas de formato
     - ✅ Países destino registrados
   - **Resultados posibles:**
     - ❌ Si falla: Lote rechazado con errores específicos
     - ✅ Si pasa: Lote aceptado y almacenado para procesamiento

3. **Decisión de Procesamiento**
   - Basado en el tamaño del lote (umbral definido por CIAT):
     - **Procesamiento Inmediato**: Lotes pequeños
     - **Procesamiento Diferido**: Lotes grandes

4. **Procesamiento de Validación**
   - Cada registro TIN se valida individualmente
   - Se aplican las reglas definidas entre:
     - País solicitante (**origen**)
     - País del TIN (**destino**)
   - Cada resultado de validación se almacena en la base de datos

5. **Generación de Respuesta**
   - **Para procesamiento diferido:**
     - Respuesta construida y almacenada
     - Disponible para recuperación posterior
   - **Para procesamiento en línea:**
     - Respuesta enviada inmediatamente en la solicitud original


## Preguntas Frecuentes

### ¿Qué formatos de archivo son compatibles?
El sistema admite XML, JSON y csv

### ¿Cuánto tiempo toma la validación?
El tiempo típico de validación es de 0.2-0.3 segundos por TIN. El procesamiento por lotes de 1000 TINs generalmente se completa en 3-4 minutos. Dado que la validación de Nivel 2 y 3 depende de los países proveedores, el tiempo de respuesta puede variar.

---

*Para guías más detalladas, inicie sesión y acceda a la documentación específica por rol.*
