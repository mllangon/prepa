# prepa
# Modelo OSI: Definición Técnico-Práctica

El modelo OSI (Open Systems Interconnection) es un marco de referencia conceptual que define cómo los datos se transmiten a través de una red en siete capas jerárquicas. Cada capa tiene funciones específicas y trabaja con las capas adyacentes para garantizar una comunicación eficiente y estandarizada entre dispositivos.

## Capas del Modelo OSI

### 1. Capa Física (Physical Layer)
**Función:** Transmite bits sin estructura (0s y 1s) a través del medio físico.  
**Características:**
- Define los niveles eléctricos y mecánicos.
- Se encarga de conectores, cables, voltajes, sincronización de bits.
- No interpreta datos, solo transmite señales.

### 2. Capa de Enlace de Datos (Data Link Layer)
**Función:** Proporciona transmisión libre de errores entre dos dispositivos directamente conectados.  
**Características:**
- Encapsula tramas (frames).
- Control de acceso al medio (MAC).
- Detección y corrección de errores.
- Ejemplo de protocolo: Ethernet, PPP.

### 3. Capa de Red (Network Layer)
**Función:** Determina la ruta lógica que deben seguir los datos.  
**Características:**
- Encapsula paquetes (packets).
- Direccionamiento lógico (IP).
- Encaminamiento (routing).
- Ejemplo de protocolo: IP, ICMP.

### 4. Capa de Transporte (Transport Layer)
**Función:** Proporciona comunicación de extremo a extremo con control de errores y de flujo.  
**Características:**
- Encapsula segmentos.
- Segmentación y reensamblado de datos.
- Garantiza la entrega correcta (TCP) o rápida (UDP).
- Protocolos: TCP, UDP.

### 5. Capa de Sesión (Session Layer)
**Función:** Gestiona sesiones o conexiones entre aplicaciones.  
**Características:**
- Establece, mantiene y termina sesiones.
- Sincronización y recuperación en caso de fallos.
- Coordinación del diálogo entre sistemas.

### 6. Capa de Presentación (Presentation Layer)
**Función:** Traduce datos entre el formato de la red y el formato de la aplicación.  
**Características:**
- Codificación y conversión de datos.
- Compresión y encriptación.
- Ejemplos: JPEG, ASCII, SSL/TLS.

### 7. Capa de Aplicación (Application Layer)
**Función:** Interfaz directa con el usuario final o con aplicaciones.  
**Características:**
- Servicios de red como email, FTP, navegación web.
- Proporciona protocolos de alto nivel.
- Protocolos: HTTP, FTP, SMTP, DNS.

---

## Comparación entre Modelo OSI y Modelo TCP/IP

| Característica            | Modelo OSI                        | Modelo TCP/IP                     |
|---------------------------|-----------------------------------|-----------------------------------|
| Capas                     | 7                                 | 4                                 |
| Desarrollo                | ISO                               | Departamento de Defensa de EE. UU.|
| Enfoque                   | Modelo teórico                    | Modelo práctico                   |
| Nombres de capas          | Físico, Enlace, Red, Transporte, Sesión, Presentación, Aplicación | Acceso a red, Internet, Transporte, Aplicación |
| Uso en la industria       | Más utilizado para enseñanza      | Base real de Internet             |
| Independencia de protocolo| Sí                                | No, está ligado a la pila TCP/IP  |



![Technical Diagram of Data Transmission through the OSI Model - visual selection](https://github.com/user-attachments/assets/8c5c75be-b8d2-4b4c-8617-66884b7dd264)



---
