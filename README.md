# OperatingSystem_Networks
En el repo habrá información básica de comandos y redes para Linux  
On this repo you will find basic information for commands and networks on Linux

## Redes/Newtorks  
Para administrar y revisar las redes dentro de Linux se usan diversos comandos.  
Se debe considerar el número de interfaces de red y el uso o destinos que tendrá cada una.  

### IP
Para listar todas las interfaces, el nombre de cada una, el Gateway correspondiente  
>ip a
  
Se pueden agregar o borrar las rutas estáticas necesarias para la comunicación del equipo, esto solo funciona de manera temporal, al reiniciar el equipo se pierden las rutas a menos que se declaren en el archivo correspondiente de rutas
>ip route add [IP|segmento]/[bits submascara] via [IP del Gateway] dev [nombre de la interfaz]  
>ip route del [IP|segmento]/[bits submascara] via [IP del Gateway] dev [nombre de la interfaz]

### TCPDUMP
Existen múltiples variantes en la ejecución de éste comando para revisar en las interfaces o puertos de red  
Inicialmente podemos filtrar tráfico de red sobre una (ens222 para este ejemplo) o todas las interfaces (**any**)
>tcpdump -i [nombre de la interfaz]  
>tcpdump -i any  
>tcpdump -i ens222

Filtrado por **IP**  
>tcpdump host [IP]
>tcpdump host 10.100.100.25

Se puede realizar un filtrado sobre un **puerto**
>tcpdump port [número de puerto]  
>tcpdump port 8080  

Para realizar una combinación en los filtros añadiendo o descartando entre varios puertos o direcciones se puede hacer uso de **or, and y not** 
Realizando una combinación de interfaz y puerto  
>tcpdump -i ens123 and port 162  
