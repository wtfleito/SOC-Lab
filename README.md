# 🛡️ SOC-Lab

![Estado](https://img.shields.io/badge/Estado-En%20construcción-yellow)
![SIEM](https://img.shields.io/badge/SIEM-Wazuh-blue)
![Firewall](https://img.shields.io/badge/Firewall-OPNsense-orange)
![IDS/IPS](https://img.shields.io/badge/IDS%2FIPS-Suricata-red)
![SO](https://img.shields.io/badge/SO-Windows%20%7C%20Linux-green)
![Virtualización](https://img.shields.io/badge/Virtualización-VMware-lightgrey)

---

# 📖 Sobre el proyecto

SOC-Lab es un laboratorio de ciberseguridad virtualizado creado para simular un entorno de **Security Operations Center (SOC)**.

El laboratorio está orientado al monitoreo, detección, análisis e investigación de eventos de seguridad utilizando diferentes tecnologías de seguridad integradas dentro de una misma red.

El entorno cuenta con un firewall, un SIEM/XDR, un IDS/IPS, endpoints y una máquina utilizada para realizar pruebas de seguridad controladas.

---

# 🧰 Componentes del laboratorio

### 🛡️ OPNsense

Firewall y gateway principal de la red.

Se utiliza para:

- Controlar el tráfico de red.
- Gestionar la conectividad entre la red interna e Internet.
- Proporcionar DHCP.
- Generar y enviar registros de eventos.
- Integrarse con el sistema de monitoreo.

### 🔎 Wazuh

Plataforma principal de monitoreo y detección del laboratorio.

Se utiliza para:

- Recopilar eventos de seguridad.
- Monitorear endpoints.
- Analizar logs.
- Detectar actividad sospechosa.
- Generar alertas.
- Realizar investigación de eventos.

### 🚨 Suricata

Sistema IDS/IPS utilizado para analizar el tráfico de red.

Se utiliza para:

- Detectar actividad sospechosa.
- Identificar posibles ataques de red.
- Generar eventos de seguridad.
- Complementar la información obtenida por Wazuh.

### 💻 Windows 10

Endpoint utilizado para representar una estación de trabajo dentro del entorno.

Se utiliza para:

- Generar eventos de seguridad.
- Analizar actividad del sistema.
- Practicar detección de comportamientos sospechosos.
- Integrarse con Wazuh.

### 📊 Sysmon

Herramienta utilizada para obtener telemetría detallada de Windows.

Permite registrar diferentes actividades del sistema que pueden ser utilizadas durante la investigación de incidentes.

### ⚔️ Kali Linux

Máquina utilizada para realizar pruebas de seguridad controladas dentro del laboratorio.

Se utiliza para generar diferentes tipos de actividad que posteriormente pueden ser detectados y analizados desde el entorno SOC.

### 🐧 Ubuntu Server

Servidor utilizado para alojar los componentes principales de Wazuh.

---

# 🏗️ Arquitectura

El laboratorio se encuentra virtualizado mediante **VMware** y utiliza una red interna `192.168.100.0/24`.

```text
                         Internet
                            │
                      VMnet8 (NAT)
                            │
                     ┌──────▼──────┐
                     │   OPNsense  │
                     │ Firewall    │
                     │ Gateway     │
                     │ DHCP        │
                     │ + Suricata  │
                     └──────┬──────┘
                            │
                      VMnet2 (LAN)
                     192.168.100.0/24
                            │
          ┌─────────────────┼─────────────────┐
          │                 │                 │
          ▼                 ▼                 ▼
    Ubuntu Server       Windows 10        Kali Linux
       Wazuh             + Sysmon          Security
          │
          └───────────────┐
                          │
                     Monitoreo
                     y análisis
