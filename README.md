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
# Procesos TCP y UDP: Definición Técnico-Práctica

En el modelo de comunicaciones de redes, los protocolos TCP y UDP pertenecen a la **Capa de Transporte**. Ambos permiten que los datos se transmitan entre aplicaciones en diferentes dispositivos a través de la red, pero tienen diferencias clave en cuanto a fiabilidad, velocidad y complejidad.

---

## TCP (Transmission Control Protocol)

**Definición:**  
TCP es un protocolo orientado a la conexión que proporciona una comunicación fiable y ordenada entre dos dispositivos. Asegura que los datos lleguen completos, en orden y sin errores.

**Características:**
- Establece una conexión mediante el proceso de **Three-Way Handshake**.
- Proporciona control de flujo y control de congestión.
- Los datos se dividen en **segmentos**.
- Garantiza la entrega de los datos y su reordenamiento si llegan desordenados.
- Reconocimiento de paquetes mediante **ACKs (Acknowledgements)**.
- Utiliza números de secuencia.
- Más lento debido al procesamiento adicional, pero confiable.

**Aplicaciones comunes:**
- Navegadores web (HTTP/HTTPS)
- Email (SMTP, IMAP)
- Transferencia de archivos (FTP)

---

## UDP (User Datagram Protocol)

**Definición:**  
UDP es un protocolo no orientado a la conexión que proporciona una comunicación rápida sin garantizar la entrega o el orden de los datos. Se usa cuando la velocidad es prioritaria frente a la fiabilidad.

**Características:**
- No establece conexión previa.
- No ofrece control de flujo ni congestión.
- Los datos se envían como **datagramas** individuales.
- No se realiza comprobación de entrega ni reintentos.
- Bajo retardo y menor sobrecarga de red.
- Puede perder paquetes sin notificar.

**Aplicaciones comunes:**
- Transmisiones en tiempo real (video/audio)
- Juegos en línea
- DNS (consulta rápida)
- VoIP

---

## Comparación entre TCP y UDP

| Característica            | TCP                               | UDP                             |
|---------------------------|------------------------------------|----------------------------------|
| Tipo de conexión          | Orientado a conexión               | No orientado a conexión          |
| Fiabilidad                | Alta (garantiza entrega y orden)  | Baja (no garantiza entrega)      |
| Velocidad                 | Más lento                         | Más rápido                       |
| Tamaño de encabezado      | Mayor (20 bytes o más)            | Menor (8 bytes)                  |
| Control de flujo/congestión | Sí                              | No                               |
| Reordenamiento de datos   | Sí                                | No                               |
| Uso típico                | HTTP, FTP, Email                  | Streaming, DNS, Juegos en línea  |


![Comparison of TCP and UDP Processes - visual selection](https://github.com/user-attachments/assets/097c3860-c786-426e-994d-ec9b2cc0722f)

---

# División de la red 192.168.50.0 en 4 subredes iguales

## Dirección base
- Dirección de red: `192.168.50.0`
- Clase: C (por pertenecer al rango 192.0.0.0 - 223.255.255.255)
- Máscara por defecto de clase C: `/24` o `255.255.255.0`

## Objetivo
Dividir la red `192.168.50.0/24` en **4 subredes de igual tamaño**.

### Paso 1: Determinar cuántos bits se necesitan para dividir en 4 subredes
Para dividir en subredes, se toman bits prestados de la porción de **host** de la dirección. En una red /24, hay 8 bits disponibles para host (último octeto).

Para obtener al menos 4 subredes:
- 2 bits → 2² = 4 subredes (mínimo requerido)

Entonces, nueva máscara:
- `/24` + 2 bits = `/26`
- Máscara: `255.255.255.192`

### Paso 2: Calcular el número de direcciones por subred
Una red `/26` deja **6 bits para hosts**:
- 2⁶ = 64 direcciones por subred
- Direcciones utilizables = 64 - 2 = **62 hosts por subred**
  - (Se resta 1 para la dirección de red y 1 para la dirección de broadcast)

## Resultado

| Parámetro                        | Valor                   |
|----------------------------------|--------------------------|
| Nueva máscara de subred         | `/26` o `255.255.255.192` |
| Total de subredes posibles      | 4                        |
| Direcciones por subred          | 64                       |
| Direcciones de host utilizables | 62                       |

## Subredes resultantes

| Subred         | Rango de hosts            | Broadcast         |
|----------------|---------------------------|-------------------|
| 192.168.50.0/26  | 192.168.50.1 - 192.168.50.62  | 192.168.50.63    |
| 192.168.50.64/26 | 192.168.50.65 - 192.168.50.126 | 192.168.50.127   |
| 192.168.50.128/26| 192.168.50.129 - 192.168.50.190| 192.168.50.191   |
| 192.168.50.192/26| 192.168.50.193 - 192.168.50.254| 192.168.50.255   |



---


