# 🛡️ SOC-Lab

![Estado](https://img.shields.io/badge/Estado-En%20construcción-yellow)
![SIEM](https://img.shields.io/badge/SIEM-Wazuh-blue)
![Firewall](https://img.shields.io/badge/Firewall-OPNsense-orange)
![IDS/IPS](https://img.shields.io/badge/IDS%2FIPS-Suricata-red)
![SO](https://img.shields.io/badge/SO-Windows%20%7C%20Linux-green)
![Virtualización](https://img.shields.io/badge/Virtualización-VMware-lightgrey)

---

# 📖 Descripción

Este proyecto documenta la implementación de un laboratorio **SOC (Security Operations Center)** virtualizado, diseñado para practicar el monitoreo, detección, análisis y respuesta ante incidentes de seguridad.

El entorno utiliza **Wazuh** como plataforma SIEM/XDR, **OPNsense** como firewall y gateway de la red, **Suricata** como IDS/IPS, **Windows Server 2022** con Active Directory, **Windows 10** como endpoint monitoreado y **Kali Linux** para realizar pruebas de seguridad controladas.

Todo el proceso de instalación, configuración, integración y ejecución de los laboratorios será documentado paso a paso.

---

# 🎯 Objetivos

* Construir un entorno SOC virtualizado desde cero.
* Implementar OPNsense como firewall, router y servidor DHCP.
* Implementar Suricata para la detección y prevención de amenazas de red.
* Implementar Wazuh como plataforma SIEM/XDR.
* Configurar un entorno de Active Directory.
* Recopilar y analizar eventos de seguridad de los endpoints.
* Utilizar Sysmon para obtener telemetría detallada de Windows.
* Simular actividad maliciosa de forma controlada desde Kali Linux.
* Detectar y analizar alertas de seguridad.
* Practicar procesos de triage e investigación de incidentes.
* Documentar las configuraciones y laboratorios realizados.

---

# 🏗️ Arquitectura del laboratorio

| Máquina / Componente | Sistema             | Función                               |
| -------------------- | ------------------- | ------------------------------------- |
| Wazuh Server         | Ubuntu Server       | SIEM / XDR                            |
| Firewall             | OPNsense            | Firewall, Router y DHCP               |
| IDS/IPS              | Suricata            | Detección y prevención de intrusiones |
| Servidor             | Windows Server 2022 | Active Directory y DNS                |
| Cliente              | Windows 10          | Endpoint monitoreado                  |
| Telemetría           | Sysmon              | Registro avanzado de eventos          |
| Atacante             | Kali Linux          | Simulación controlada de ataques      |

---

# 🌐 Topología

```text
                         Internet
                            │
                      VMnet8 (NAT)
                            │
                     ┌──────▼──────┐
                     │   OPNsense  │
                     │ Firewall    │
                     │ Router/DHCP │
                     │ + Suricata  │
                     └──────┬──────┘
                            │
                      VMnet2 (LAN)
                            │
                   192.168.100.0/24
                            │
          ┌─────────────────┼─────────────────┐
          │                 │                 │
          ▼                 ▼                 ▼
     Wazuh Server      Windows Server      Windows 10
     Ubuntu Server         2022            + Sysmon
                                                  │
                                             Kali Linux
```

---

# 🛠️ Tecnologías y herramientas

* VMware Workstation Pro
* OPNsense
* Suricata
* Wazuh
* Ubuntu Server
* Windows Server 2022
* Active Directory
* Windows 10
* Sysmon
* Kali Linux

---

# 📂 Estructura del proyecto

```text
SOC-Lab/
│
├── documentacion/
│   ├── red/
│   ├── opnsense/
│   ├── wazuh/
│   ├── active-directory/
│   ├── sysmon/
│   └── suricata/
│
├── laboratorios/
├── capturas/
├── diagramas/
├── recursos/
│
├── LICENSE
└── README.md
```

---

# 🚀 Estado del proyecto

* [x] Creación del repositorio
* [x] Organización inicial del proyecto
* [ ] Configuración de la red virtual
* [ ] Instalación y configuración de OPNsense
* [ ] Configuración del servicio DHCP
* [ ] Configuración de Suricata IDS/IPS
* [ ] Instalación de Wazuh
* [ ] Configuración de Active Directory
* [ ] Instalación y configuración de Sysmon
* [ ] Integración de endpoints con Wazuh
* [ ] Integración de eventos de red
* [ ] Desarrollo de laboratorios de detección
* [ ] Investigación y documentación de incidentes

---

# 👨‍💻 Autor

**Leonardo Paulino**

Estudiante de Seguridad Informática interesado en **SOC, SIEM, Blue Team y Respuesta a Incidentes**.
