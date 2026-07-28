# Configuración de la Red

La configuración de la red constituye la base del laboratorio **SOC-Lab**. En esta fase se prepara la infraestructura virtual que permitirá la comunicación entre todos los sistemas del entorno, utilizando **FortiGate** como dispositivo central para el enrutamiento, el filtrado del tráfico y la asignación de direcciones IP.

---

## Arquitectura de la Red

| Componente | Configuración |
|------------|---------------|
| Plataforma de virtualización | VMware Workstation |
| Red externa (WAN) | VMnet8 (NAT) |
| Red interna (LAN) | VMnet2 (Host-Only) |
| Rango de red | 192.168.100.0/24 |
| Máscara de subred | 255.255.255.0 |
| Gateway predeterminado | 192.168.100.1 |
| Servidor DHCP | FortiGate |
| DHCP de VMware | Deshabilitado |

---

## Diseño de la Infraestructura

```
                              Internet
                                  │
                           VMnet8 (NAT)
                                  │
                          ┌────────────────┐
                          │   FortiGate    │
                          │ Gateway · DHCP │
                          └───────┬────────┘
                                  │
                      VMnet2 (Host-Only / LAN)
                                  │
          ┌────────────┬────────────┬────────────┬────────────┐
          │            │            │            │
      Wazuh Server  Windows Server  Windows 10  Kali Linux
```

---

## Direccionamiento IP

| Dispositivo | Sistema Operativo | Dirección IP | Función |
|--------------|-------------------|--------------|---------|
| FortiGate | FortiOS | 192.168.100.1 | Gateway, Firewall y DHCP |
| Wazuh Server | Ubuntu Server | 192.168.100.10 | SIEM / XDR |
| Windows Server | Windows Server 2022 | 192.168.100.20 | Active Directory y DNS |
| Cliente | Windows 10 | DHCP | Endpoint monitoreado |
| Atacante | Kali Linux | DHCP | Simulación de ataques |

---

## Evidencias

Las siguientes capturas documentan la configuración inicial de la infraestructura de red.

### VMnet8 (NAT)



---

### VMnet2 (Host-Only)



---

### DHCP de VMware deshabilitado



---

## Resultado

La infraestructura de red quedó preparada correctamente, estableciendo una red interna aislada para el laboratorio y una conexión controlada a Internet mediante FortiGate. Esta configuración servirá como base para la instalación y configuración del resto de los componentes del proyecto.
