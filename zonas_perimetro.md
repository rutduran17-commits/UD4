## Práctica 1 · Perímetro y zonas

### 1. Tabla de ubicación. 

| Servicio | Zona | Justificación |
|-----------|------|--------------|
Web corporativa pública | DMZ | Se comunica con internet, así que se necesita aislarla en la DMZ |
Servidor de correo |  |  |
Pasarela VPN  |   |   |
Proxy (saliente e inverso)  |   |   |
HMI de planta y carpeta de planos |   |   |
Autoridad de certificación (srv-ca)  |   |   |
Servidor de copias de seguridad |    |    |
Portátiles de ingenieros y operarios  |  | |
Wi-Fi de invitados  |    |   |  
Servidor de registros y monitorización |  |  |


### 2. Tabla de flujos.

| Origen -> destino | ¿Permitido? | Ejemplo concreto |
|--------------------|-----------|---------------|
Internet → DMZ |   |  | 
Internet → LAN |   |  | 
DMZ → LAN  |    |    |  
LAN → DMZ   |   |  |
LAN → Internet  |   |   |


### 3. Un diagrama de la red

```mermaid
flowchart LR
    Internet --> FW1[Cortafuegos] --> DMZ --> FW2[Cortafuegos] --> LAN
```
### 4. Una pregunta de reflexión 

si cae el servidor web, ¿qué puede hacer el atacante en tu diseño y qué se lo impide?




