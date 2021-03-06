# Commandos consola IOS (CISCO)
## Configuracion basica
### Inicio de sesion y seguridad
(config)#hostname

(config)#enable secret \<pass>

(config)#line console 0 //Accede conf. consola

(config-line)#password \<pass> 

(config)#logging synchronous // Para que los mensajes no corten los comandos

(config-line)#login //Setea la constraseña indicada anteriormente

(config)#line vty 0 4

(config)#banner motd # //Configura mensajes inicio de sesion
### Verificacion de configuracion
\#copy running-config startup-config //Guarda la configuracion

\#show running-config

\#show startup-config

\#show ip route

\#show interfaces

\#show ip interface brief

\#show vtp status

\#show spanning-tree

### Configuracion de interfaces

(config)#interface \<int>

(config-if)#ip address \<ip> \<mask>

(config-if)#no shutdown //Levanta el enlace


## Protocolos de enrutamiento

### RIP v1 

(config)# router rip 1

(config-router)# network \<ip red>  //si hay mas de una red se colocan todas, sin mascaras por ser protocolos con clase

(config-router)#passive-interface <interface/serial> //bloquea el broadcast hacia la interfaz/serial, para bloquear donde no hayan router

(config)# default-information originate // propagacion de ruta por defecto.  

#### RIP v2
(config)# router rip
(config-router)# version 2

### EIGRP

(config)#router eigrp \<numero>

(config-router)#network \<ip red> \<mask inv>
 
\#show ip eigrp neighbors

Nota: Mask Inv = 255.255.255.255 - Máscara - Ejemplo: 255.255.255.255 - 255.255.255.252 = 0.0.0.3

Nota 2: Métrica = (Bandwidth + Delay) * 256

### OSPF

(config)#router ospf \<id>

(config-router)#network \<ip red> \<mask inv> area \<id area>

(config-router) # router-id <ip mayor> //para designar el router identificador
 
 (config)#bandwith <valor ancho de banda> //configuracion ancho de banda

 (config int) #ip ospf cost <valor del costo>
 
 (config int) #ip ospf priority <valor>   //entre 0-255 , 0 no sera designado ni de respaldo
 
## Switch
(config)#ip routing //habilita enrutamiento capa 2

### Configuracion puertos
(config)#int \<int>

(config-if)#switchport mode \<access;trunk>

(config-if)#switchport acces vlan \<NºVlan>

(config-if)#switchport trunk encapsulation dot1q
### Configurar VLAN
(config)#vlan \<NºVlan>

(config-vlan)#name \<nombre>

### VTP Servidor
(config)#vtp domain \<dominio>

(config)#vtp version \<Nº>2
### VTP Cliente
(config)#vtp mode client

### STP
(config)#spanning-tree \<vlan> root \<primary;secondary>

(config)#spanning-tree mode rapid-pvst

(Config-if)#spanning-tree portfast 

### DHCP
(config)#ip dhcp excluded-address \<inicio> \<fin>

(config)#ip dhcp pool \<vlan> 

(config-dhcp)#network \<red> \<mask>

(config-dhcp)#default-router \<gateway>

(config-dhcp)#dns-server \<dns>

### HSRP - FHRP
(config-if)#standby \<NºGrupo> ip \<ip>

(config-if)#standby \<NºGrupo> priority \<Nº>

(config-if)#standby \<NºGrupo> preempt

### PortChannel
#### Para cada puerto
(config-if)#speed auto

(config-if)#duplex auto

(config-if)#mdix \<auto;full>

(config-if)#channel-group \<Nº> mode \<modo>
#### Para cada switch
(config)#interface port-channel \<Nº>

(config-if)#switchport trunk encapsulation dot1q

(config-if)#switchport mode trunk

### NAT
(config-if)#nat inside

(config-if)#nat outside

(config)#access-list \<Nºlista> permit \<ip-inside> \<mask-inv>

(config)#ip nat inside source list \<NºLista> \<interfaz-salida> overload









