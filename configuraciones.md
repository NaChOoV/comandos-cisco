# Listas de comandos para configuracion

### Configurar switch
➢ enable \
➢ config t \
➢ hostname “nombre del host”  // cambiar el nombre del equipo \
➢ int vlan “n°” \
➢ ip address “nueva ip” “mascara de red” \
➢ no shut \
➢ “verificar conectividad con ping” \

➢ “ir a config t” \
➢ line vty “fa inicio” “fa final” \
➢ login local \
➢ exit \
➢ username “nuevo user” password “nueva contraseña” \
➢ enable secret “nueva contraseña” \
➢ ip default-gateway “ip de gateway” \
➢ “salir” \

### Configurar Router(Router a switch):
➢ “abrir consola”
➢ enable \
➢ config t \
➢ hostname “nombre del host” \
➢ int fa*/*(Puerto del router que está conectado al switch) \
➢ ip address “ip del gateway” “mascara de red” v
➢ no shut \
➢ exit \

➢ line vty “fa inicio” “fa final” \
➢ login local \
➢ exit \
➢ username “nuevo user” password “nueva contraseña” \
➢ enable secret “nueva contraseña” \
➢ “salir” \

### Configurar Router(Router a Router):
➢ enable \
➢ config t \
➢ hostname “nombre del host” \
➢ int s*/*/* o fa*/* \
➢ ip address “ip del gateway” “mascara de red” \
➢ clock rate 1000000 // 1Mb/s  para el DCE \
➢ no shut \

### Ingresar IP’s a tabla de rutas:
➢ ip route “ip a enrutar” “ip de próximo salto” \ 
➢ show ip route \

## Extras:

➢ no auto-summary // Evitar que se sumarice las ip \ 

#### Reiniciar router:
➢ erase startup-config // elimina configuracion de arranque \
➢ reload // recarga el sistema operativo para cargar nuevas configuraciones \


