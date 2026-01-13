# **Guía de Usuario \- Conexión Segura a la API de Validación de TIN**

Sistema de Validación de TIN \- CRS-CIAT

Esta guía está destinada únicamente a usuarios autorizados (aplicaciones de máquina a máquina).

## **Descripción General**

La API de validación de TIN en [https://ciat.org/validatin](https://ciat.org/validatin) utiliza un método de autenticación seguro basado en OAuth 2.0 con `private_key_jwt` (RFC 7523).

Esto significa que no se utilizan contraseñas compartidas. En su lugar, su aplicación genera un par de claves criptográficas (privada y pública) y utiliza la clave privada para firmar una solicitud de token al IAM ([https://ciat.org/iam/auth](https://ciat.org/iam/auth)).

El IAM verifica la firma utilizando la clave pública registrada previamente y, si es válida, emite un token de acceso temporal que usted utiliza para llamar a la API.

Este método es altamente seguro y recomendado para comunicación de máquina a máquina.

## **Generar Claves**

### **Paso 1: Generar el Par de Claves (Una sola vez)**

Necesita crear:

* Clave privada (private\_key.pem): Manténgala secreta. ¡Nunca la comparta\!  
* Certificado público (public\_cert.pem): Este es el que registra en el sistema.

Utilice OpenSSL (herramienta gratuita disponible en Windows, Linux y macOS):

`text`

`openssl req -x509 -newkey rsa:2048 -keyout private_key.pem -out public_cert.pem -days 365 -nodes`

Se le pedirá información (nombre, organización, país). Puede presionar Enter para dejar en blanco o ingresar datos genéricos.

Resultado: Dos archivos en la carpeta actual.

## **Registrar Certificado**

### **Paso 2: Registrar el Certificado Público**

Envía el contenido del archivo `public_cert.pem` al administrador del sistema CIAT o cárguelo a través del portal de registro de clientes (si está disponible).

El sistema asociará este certificado con su client\_id (un identificador único proporcionado).

Una vez registrado, puede comenzar a solicitar tokens.

## **Cómo Funciona la Autenticación**

### **Paso 3: Cómo Funciona la Autenticación (Explicación Detallada)**

Su aplicación crea un JWT pequeño con datos básicos (quién es usted, hora, dirección del IAM) y lo firma con su clave privada.

El IAM verifica la firma utilizando la clave pública registrada.

#### **Proceso Matemático de Firma y Verificación (RSA \- RS256)**

1. Se calcula un hash (resumen único) del mensaje JWT.  
2. Usando la clave privada, se aplica una operación matemática (elevar el hash a una potencia secreta módulo n).  
3. Resultado: la firma.  
4. El IAM calcula el mismo hash del mensaje.  
5. Aplica la operación inversa con la clave pública (elevar la firma a una potencia pública módulo n).  
6. Si el resultado coincide exactamente con el hash, la firma es válida → prueba irrefutable de que fue creada con la clave privada correspondiente.

Es imposible falsificar sin la clave privada debido a la extrema dificultad matemática de factorizar números grandes.

## **Obtener Token**

### **Paso 4: Obtener el Token de Acceso**

Recomendamos usar bibliotecas que automaticen este proceso:

* Python: Authlib  
* .NET/C\#: [MSAL.NET](https://msal.net/)  
* Java: Nimbus JOSE \+ JWT

Si se hace manualmente, envíe un POST al endpoint `https://ciat.org/iam/auth` con parámetros como `client_assertion_type=urn:ietf:params:oauth:client-assertion-type:jwt-bearer` y el JWT firmado como `client_assertion`.

El IAM responde con un access\_token (válido por horas).

## **Llamar a la API**

### **Paso 5: Llamar a la API**

En cada solicitud a [https://ciat.org/validatin](https://ciat.org/validatin), incluya el encabezado:

`text`

`Authorization: Bearer <su_access_token>`

La API verificará el token con el IAM (o directamente si es un JWT firmado por el IAM).

Renueve el token cuando expire.  