## Base config 

 Contiene paquetes base y configuración de telegraf para monitoreo, requiere configurar vars en config.j2 


### Incluir variables 

 editar: /etc/ansible/hosts 

[hosts]
 IP_ADDDRES
 influxdbHost="var"
 influxdbName="var"

