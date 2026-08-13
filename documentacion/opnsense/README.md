# 🧱 OPNsense

Esta sección documenta la instalación y configuración de OPNsense dentro del laboratorio SOC.

## Objetivo

Implementar OPNsense como dispositivo principal de seguridad y conectividad de la red del laboratorio.

OPNsense realizará las funciones de:

* Firewall.
* Router.
* Gateway.
* Servidor DHCP.
* Control del tráfico entre la red interna e Internet.

Posteriormente se integrará Suricata para proporcionar capacidades IDS/IPS.

## Interfaces de red

OPNsense utilizará dos interfaces:

```text
WAN → VMnet8 (NAT)
LAN → VMnet2 (Red interna SOC)
```

La interfaz LAN utilizará:

```text
IP: 192.168.100.1
Máscara: /24
```

## DHCP

OPNsense será el servidor DHCP de la red interna.

Los clientes del laboratorio podrán obtener automáticamente:

* Dirección IP.
* Gateway.
* Servidor DNS.

## Firewall

Se configurarán reglas para controlar el tráfico entre los dispositivos internos y la red externa.

## Suricata IDS/IPS

Una vez completada la configuración inicial de OPNsense, se configurará Suricata para detectar actividad sospechosa y generar alertas de seguridad.

## Evidencias

Las capturas correspondientes a la instalación y configuración se almacenarán en:

```text
capturas/opnsense/
```
