# Linux

### USB

lista dispositivos conectados a USB  
```console 
lsusb
```
Lista dispositivos conectados y su terminal asociado  
```console
ls -la /dev/serial/by-id/ 
```
Para USB-serie , añadir a /etc/udev/rules.d/99-com.rules  
SUBSYSTEM==“usb”, ATTR{idVendor}==“0483”, ATTR{idProduct}==“0011”, MODE="666"


### Network Manager
Configurar Red con Network-Manager
```console
nmcli con mod eth0 ipv4.addresses 192.168.2.20/24
nmcli con mod eth0 ipv4.gateway 192.168.2.1
nmcli con mod eth0 ipv4.dns “8.8.8.8”
nmcli con mod eth0 ipv4.method manual
```
-Cambiar ip con Network Manager
```console
nmcli device modify eth0 ipv4.address <ip_address>
```

#### Usando IFconfig
- Cambio IP
```console
sudo ifconfig eth0 1.1.13.97 netmask 255.255.0.0 broadcast 192.168.0.255
```
- Cambio Gateway
```console
sudo route add default gw 1.1.10.100
```

### Samba
Instalacion
```console
sudo apt install samba samba-common-bin
```
Archivo configuracion
```console
sudo nano \etc\samba\smb.conf
```
Ejemplo de configuracion
```console
comment = Proyectos Python
path = \home\pi\python
browseable = yes
writeable = yes
only guest = no
create mask = 0777
directory mask = 0777
public = yes
guest ok = yes
force user = pi
```

### Servidor de Hora  NTP
Instalar servicio de puesta en hora NTPdate  
servicio NTP : 1.1.254.178 (NAT de Miguel Nieto)  

Configurar en  
```console
sudo nano \etc\systemd\timesyncd.conf
```
Añadir
```
timedatectl set-ntp true
```
Reiniciar servicio
```console
sudo systemctl restart systemd-timesyncd.service
```
