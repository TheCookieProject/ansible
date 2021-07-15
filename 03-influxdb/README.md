## Influxdb 

### Despligue de VM db

Para despleegar una maquina vm en DO y utilizar los volumenes declarados en el ejemplo:

url: https://github.com/thecookieproject/terraform/tree/main/01-vm 


### Vars 

```
path_idb:

  - /mnt/kvol/meta # j2 variable [1] y directios! 
  - /mnt/kvol/data # j2 variable [2]
  - /mnt/kvol/wal  # j2 variable [3]

```

Contiene las variables para crear directorios y configurar 'path' en j2 template. 

### j2 template

Configuración básica, por defecto en: `/etc/lib/influxdb`

Configuración en volumen: 

```
[meta]
  #dir = "/var/lib/influxdb/meta"
  # /mnt/kvol -> volume en DO 
  dir = "{{ path_idb[0] }}"

[data]
  #dir = "/var/lib/influxdb/data"
  dir = "{{ path_idb[1] }}"
  engine = "tsm1"
  #wal-dir = "/var/lib/influxdb/wal"
  wal-dir = "{{ path_idb[2] }}"

```

:wq!
