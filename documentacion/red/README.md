# 🌐 Configuración de la Red

Esta sección documenta la configuración de red utilizada para conectar los diferentes componentes del laboratorio SOC.

## Objetivo

Crear una red virtual aislada donde OPNsense actúe como gateway, firewall y servidor DHCP para los dispositivos internos.

## Diseño de red

La infraestructura utilizará dos redes virtuales:

### VMnet8 — WAN

Se utilizará como interfaz WAN de OPNsense para proporcionar acceso a Internet mediante NAT de VMware.

### VMnet2 — LAN

Se utilizará como red interna del laboratorio SOC.

El servicio DHCP de VMware estará deshabilitado en esta red, ya que OPNsense será el encargado de asignar las direcciones IP.

## Esquema de direccionamiento

```text
Red LAN:       192.168.100.0/24
Gateway:       192.168.100.1
Servidor DHCP: OPNsense
```

## Componentes conectados

* Wazuh Server
* Windows Server 2022
* Windows 10
* Kali Linux

## Verificación

Durante la implementación se realizarán pruebas de:

* Asignación de direcciones IP.
* Comunicación entre los dispositivos.
* Acceso al gateway.
* Resolución DNS.
* Acceso a Internet.

## Evidencias

Las capturas correspondientes a esta configuración se almacenarán en:

```text
capturas/red/
```

