## Práctica 1 · Perímetro y zonas

### 1. Tabla de ubicación. 

| Servicio | Zona | Justificación |
|-----------|------|--------------|
Web corporativa pública | DMZ | Se comunica con internet, así que se necesita aislarla en la DMZ |
Servidor de correo | DMZ | Necesita intercambiar conexiones con internet, aislarla. |
Pasarela VPN  |  DMZ |  Como es la puerta de la lan hacia internet, aislarla. |
Proxy (saliente e inverso)  | DMZ  |  Ya que actúa como un puente entre muchas redes he inspecciona el tráfico para evitar las conexiones directas de la lan a internet. |
HMI de planta y carpeta de planos |  Zona crítica | Si caen en manos indeseadas comprometerá la producción.  |
Autoridad de certificación (srv-ca)  | Zona crítica  | Si es comprometida, suplantaría su identidad.   |
Servidor de copias de seguridad |   Zona crítica |  Al ser los datos, debe de mantenerse aislada y con acceso muy limitado.  |
Portátiles de ingenieros y operarios  | LAN | Ya que requieren conexión interna para trabajar. |
Wi-Fi de invitados  |   Zona propia | solo se conectarán a internet por lo que se controlará con una red de invitados.  |  
Servidor de registros y monitorización | Zona crítica | Al tener todos los registros, merece estar aislado, ya que no se pueden manipular.  |


### 2. Tabla de flujos.

| Origen -> destino | ¿Permitido? | Ejemplo concreto |
|--------------------|-----------|---------------|
Internet → DMZ | SI  |  | 
Internet → LAN |   NO |  | 
DMZ → LAN  |  NO a menos que sea necessario  |    |  
LAN → DMZ   | si  |  |
LAN → Internet  |   |   |


### 3. Un diagrama de la red

```mermaid
flowchart LR
    Internet --> FW1[Cortafuegos] --> DMZ --> FW2[Cortafuegos] --> LAN
```
### 4. Una pregunta de reflexión 

si cae el servidor web, ¿qué puede hacer el atacante en tu diseño y qué se lo impide?




