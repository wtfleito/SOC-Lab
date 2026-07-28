# Configuración de la Red

La configuración de la red representa el primer paso en la implementación del laboratorio **SOC-Lab**. En esta fase se define la infraestructura que permitirá la comunicación entre todas las máquinas virtuales, estableciendo una red interna segura y una salida controlada a Internet mediante **FortiGate**.

---

## Información General

| Parámetro | Configuración |
|-----------|---------------|
| Plataforma de virtualización | VMware Workstation |
| Red externa (WAN) | VMnet8 (NAT) |
| Red interna (LAN) | VMnet2 (Host-Only) |
| Rango de red | 192.168.100.0/24 |
| Gateway | 192.168.100.1 |
| Servidor DHCP | FortiGate |
| DHCP de VMware | Deshabilitado |

---

## Direccionamiento IP

| Dispositivo | Dirección IP | Función |
|-------------|--------------|---------|
| FortiGate | 192.168.100.1 | Gateway, Firewall y DHCP |
| Wazuh Server | 192.168.100.10 | SIEM / XDR |
| Windows Server 2022 | 192.168.100.20 | Active Directory y DNS |
| Windows 10 | DHCP | Endpoint monitoreado |
| Kali Linux | DHCP | Simulación de ataques |

---

## Evidencias

Durante esta etapa se documentó la creación de las redes virtuales, la desactivación del servicio DHCP de VMware en la red interna y la validación de la infraestructura antes de iniciar la instalación de FortiGate.
