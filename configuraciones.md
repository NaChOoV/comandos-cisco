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
➢ int s*/* \
➢ ip address “ip del gateway” “mascara de red” \
➢ no shutdown \
➢ clock rate 1000000 \

### Ingresar IP’s a tabla de rutas:
➢ ip route “ip a enrutar” “ip de próximo salto” \ 
➢ show ip route \
