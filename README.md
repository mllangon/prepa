# prepa
#Parte I
---
# Pregunta 1: Modelo OSI

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
# Pregunta 2: Procesos TCP y UDP: Definición Técnico-Práctica

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

# Pregunta 3: División de la red 192.168.50.0 en 4 subredes iguales

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

# Pregunta 4: Routers, Tablas de Enrutamiento y Tipos de Enrutamiento

## ¿Qué es un router?

Un **router** (enrutador) es un dispositivo de red que se encarga de **encaminar paquetes de datos** entre diferentes redes. Su función principal es recibir un paquete, examinar su dirección de destino, y decidir hacia qué interfaz de red reenviarlo, basándose en su **tabla de enrutamiento**.

### Características prácticas de un router:
- Conecta redes diferentes (por ejemplo, una red local a Internet).
- Decide la ruta más adecuada para los paquetes de datos.
- Opera principalmente en la **capa 3 (Red)** del modelo OSI.
- Puede aplicar políticas de seguridad, NAT, QoS, filtrado de tráfico, etc.
- Soporta tanto **enrutamiento estático** como **dinámico**.

---

## ¿Qué es una tabla de enrutamiento?

Una **tabla de enrutamiento** es una estructura interna que contiene las rutas conocidas por el router y las decisiones que debe tomar para reenviar paquetes hacia sus destinos. Cada entrada define cómo alcanzar una red específica.

### Elementos comunes de una tabla de enrutamiento:
- **Red de destino**: dirección IP y máscara.
- **Máscara o prefijo**: determina el tamaño de la red.
- **Próximo salto (next hop)**: dirección IP del siguiente router en la ruta.
- **Interfaz de salida**: la interfaz por la cual debe salir el paquete.
- **Métrica**: valor que ayuda a elegir la mejor ruta cuando hay varias.

---

## Ejemplo de tabla de enrutamiento

| Destino          | Máscara        | Next Hop        | Interfaz | Métrica |
|------------------|----------------|------------------|----------|---------|
| 192.168.1.0      | 255.255.255.0  | 0.0.0.0 (directo) | eth0     | 1       |
| 10.0.0.0         | 255.0.0.0      | 192.168.1.2       | eth1     | 2       |
| 0.0.0.0 (default)| 0.0.0.0        | 192.168.1.1       | eth0     | 10      |

### ¿Cómo funciona?
- Si un paquete llega con destino `10.5.4.3`, el router busca la entrada más específica en la tabla.
- Coincide con `10.0.0.0/8`, así que lo reenvía a través de `eth1` al next hop `192.168.1.2`.
- Si no encuentra una coincidencia específica, usa la **ruta por defecto (default route)**.

---

## Enrutamiento Estático vs Dinámico

| Característica             | Enrutamiento Estático                | Enrutamiento Dinámico                  |
|---------------------------|--------------------------------------|----------------------------------------|
| Configuración              | Manual (por el administrador)       | Automática (mediante protocolos)       |
| Flexibilidad               | Baja                                 | Alta                                   |
| Complejidad                | Simple de implementar                | Más compleja                          |
| Adaptación a cambios       | No se adapta automáticamente         | Se ajusta automáticamente              |
| Uso de CPU/memoria         | Bajo                                 | Requiere más recursos                  |
| Protocolos utilizados      | No usa protocolos                    | RIP, OSPF, EIGRP, BGP, etc.            |
| Idóneo para                | Redes pequeñas y estables            | Redes grandes y en constante cambio    |


![Technical Diagram of a Router with Routing Table - visual selection](https://github.com/user-attachments/assets/c468d72f-44cd-410c-a31d-6f2f589ce4ec)



---

# Pregunta 5: NAT (Network Address Translation)

## ¿Qué técnica representa?

La técnica descrita es **NAT (Network Address Translation)**, un mecanismo de red que permite que múltiples dispositivos dentro de una red privada accedan a redes externas (como Internet) usando una única dirección IP pública.

---

## ¿Qué es NAT?

**NAT** es un proceso que modifica las direcciones IP de los paquetes que pasan a través de un router u otro dispositivo de red. Permite que los dispositivos de una red privada utilicen direcciones privadas (no enrutable en Internet) y, al salir a Internet, estas se traduzcan en una única dirección IP pública.

---

## ¿Cómo funciona?

1. Un dispositivo interno (por ejemplo, con dirección 192.168.1.10) envía un paquete hacia una dirección externa (por ejemplo, 8.8.8.8).
2. El router con NAT reemplaza la dirección IP de origen del paquete (192.168.1.10) por su dirección IP pública (por ejemplo, 203.0.113.1).
3. El router guarda esta traducción en una tabla de NAT (asocia la IP interna y el puerto con la IP pública y un puerto asignado).
4. Cuando el servidor externo responde, el router consulta la tabla y reenvía la respuesta al dispositivo interno correspondiente.

Este proceso se conoce como **NAT dinámico** o **PAT (Port Address Translation)** cuando se usan puertos para distinguir entre múltiples conexiones salientes.

---

## Beneficios de NAT

1. **Ahorro de direcciones IPv4 públicas:** Permite que cientos de dispositivos compartan una sola IP pública.
2. **Seguridad básica:** Oculta las direcciones IP internas de los dispositivos, dificultando accesos directos desde el exterior.

![Understanding Network Address Translation (NAT) - visual selection](https://github.com/user-attachments/assets/91415af0-a364-4dc5-8805-189f9f929d6c)


---
PARTE II
---

# Proyecto de VLANs con Router-on-a-Stick

Este proyecto simula una red con múltiples VLANs separadas por roles o departamentos: Arquitectos, Escribas, Comercio y Mercaderes. Todas las VLANs están interconectadas a través de un router configurado como **Router-on-a-Stick**, el cual enruta el tráfico entre ellas utilizando subinterfaces.

---

## Topología de Red

- **Router**: Router-on-a-Stick (modelo 1941)
- **Switch central**: 2960-24TT
- **VLANs configuradas**:
  - VLAN 10 - Arquitectos
  - VLAN 20 - Escribas
  - VLAN 30 - Comercio
  - VLAN 40 - Mercaderes

---

## Configuración de Subredes y Subinterfaces

| VLAN | Nombre       | Subred            | Dispositivos         | IPs de Dispositivos | IP de la subinterfazRouter |
|------|--------------|-------------------|-----------------------|---------------------|---------------------------|
| 10   | Arquitectos  | 192.168.10.0/24   | PC0, PC3              |  .2, .3               |     192.168.10.1       |
| 20   | Escribas     | 192.168.20.0/24   | PC1, PC2              | .2, .3               |     192.168.20.1       |
| 30   | Comercio     | 192.168.30.0/24   | Smartphone2, Smartphone4 | .2, .3           |     192.168.30.1       |
| 40   | Mercaderes   | 192.168.40.0/24   | Servidor              | .2                   |     192.168.40.1       |

---

## Configuración del Router

```bash
enable
configure terminal

interface GigabitEthernet0/0.10
 encapsulation dot1Q 10
 ip address 192.168.10.1 255.255.255.0
 no shutdown

interface GigabitEthernet0/0.20
 encapsulation dot1Q 20
 ip address 192.168.20.1 255.255.255.0
 no shutdown

interface GigabitEthernet0/0.30
 encapsulation dot1Q 30
 ip address 192.168.30.1 255.255.255.0
 no shutdown

interface GigabitEthernet0/0.40
 encapsulation dot1Q 40
 ip address 192.168.40.1 255.255.255.0
 no shutdown

interface GigabitEthernet0/0
 no shutdown
```
---
# Conexión entre dos ciudades

Este proyecto conecta múltiples casas distribuidas en dos ciudades remotas mediante routers intermedios y una nube WAN. Cada casa tiene su red local (LAN) y está conectada a un router local, que a su vez está conectado a un router de interconexión. Las comunicaciones entre ciudades se realizan a través de una red WAN basada en conexiones seriales y una nube Frame Relay.

---

## Direccionamiento IP por Casa

### Ciudad A

**CASA 1** - Red: `192.168.10.0/24`
- PC0: `192.168.10.3`
- PC1: `192.168.10.2`
- Router14:
  - Gbit0/0: `192.168.10.1`
  - Serial0/0/0: `10.0.0.1`

**CASA 2** - Red: `192.168.11.0/24`
- PC2: `192.168.11.2`
- Laptop0: `192.168.11.3`
- Router15:
  - Gbit0/0: `192.168.11.1`
  - Serial0/0/0: `10.0.0.5`

**CASA 3** - Red: `192.168.12.0/24`
- Laptop1: `192.168.12.3`
- PC3: `192.168.12.2`
- Router16:
  - Gbit0/0: `192.168.12.1`
  - Serial0/0/0: `10.0.0.9`

**CASA 4** - Red: `192.168.13.0/24`
- PC4: `192.168.13.2`
- PC5: `192.168.13.3`
- Router17:
  - Gbit0/0: `192.168.13.1`
  - Serial0/0/0: `10.0.0.13`

---

### Ciudad B

**CASA 5** - Red: `192.168.14.0/24`
- PC6: `192.168.14.3`
- PC7: `192.168.14.2`
- Router18:
  - Gbit0/0: `192.168.14.1`
  - Serial0/0/0: `10.0.1.1`

**CASA 6** - Red: `192.168.15.0/24`
- PC8: `192.168.15.2`
- Laptop2: `192.168.15.3`
- Router19:
  - Gbit0/0: `192.168.15.1`
  - Serial0/0/0: `10.0.1.5`

**CASA 7** - Red: `192.168.16.0/24`
- Laptop3: `192.168.16.2`
- PC9: `192.168.16.3`
- Router20:
  - Gbit0/0: `192.168.16.1`
  - Serial0/0/0: `10.0.1.9`

**CASA 8** - Red: `192.168.17.0/24`
- PC10: `192.168.17.2`
- PC11: `192.168.17.3`
- Router21:
  - Gbit0/0: `192.168.17.1`
  - Serial0/0/0: `10.0.1.13`

---

## Routers de Interconexión

**Router22**
- Serial0/1/0: `10.0.0.21`
- Serial0/1/1: `10.0.0.2`
- Serial0/2/0: `10.0.0.6`
- Serial0/2/1: `10.0.0.17`

**Router7**
- Serial0/1/0: `10.0.0.18`
- Serial0/1/1: `10.0.0.25`
- Serial0/2/0: `10.0.0.14`
- Serial0/2/1: `10.0.0.10`

**Router8**
- Serial0/1/0: `10.0.2.1` (conexión WAN)
- Serial0/1/1: `10.0.0.26`
- Serial0/2/0: `10.0.0.22`

**Router9**
- Serial0/1/0: `10.0.2.2` (conexión WAN)
- Serial0/1/1: `10.0.1.18`
- Serial0/2/0: `10.0.1.22`

**Router0**
- Serial0/1/0: `10.0.1.25`
- Serial0/1/1: `10.0.1.17`
- Serial0/2/0: `10.0.1.2`
- Serial0/2/1: `10.0.1.6`

**Router23**
- Serial0/1/0: `10.0.1.21`
- Serial0/1/1: `10.0.1.10`
- Serial0/2/0: `10.0.1.14`
- Serial0/2/1: `10.0.1.26`

**Cloud**
-a router 9 y 8 a traves de serial 0 y 1 del cloud

---

## Resumen de Configuración

- Cada casa tiene una red LAN con su router.
- Los routers domésticos están conectados a routers intermedios para cada ciudad.
- Las ciudades están interconectadas por routers centrales (Router8 y Router9) mediante una **nube WAN (10.0.2.0/24)**.
- Direccionamiento jerarquizado:
  - **10.0.0.0/24** → conexiones seriales de Ciudad A
  - **10.0.1.0/24** → conexiones seriales de Ciudad B
  - **10.0.2.0/24** → enlace entre ciudades
- Todas las comunicaciones están enrutadas estáticamente mediante comandos `ip route`.

---
