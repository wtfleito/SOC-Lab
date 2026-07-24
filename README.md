# 🛡️ SOC-Lab

![Estado](https://img.shields.io/badge/Estado-En%20construcción-yellow)
![SIEM](https://img.shields.io/badge/SIEM-Wazuh-blue)
![Firewall](https://img.shields.io/badge/Firewall-FortiGate-red)
![SO](https://img.shields.io/badge/SO-Windows%20%7C%20Linux-green)
![Virtualización](https://img.shields.io/badge/Virtualización-VMware-lightgrey)

---

# 📖 Descripción

Este proyecto documenta la implementación de un laboratorio SOC (Security Operations Center) virtualizado para el monitoreo, detección, investigación y respuesta a incidentes de seguridad.

El laboratorio utiliza **Wazuh** como plataforma SIEM/XDR, **FortiGate** como firewall perimetral, **Windows Server 2022** con Active Directory, **Windows 10** como estación de trabajo y **Kali Linux** para realizar pruebas de seguridad controladas.

Todo el proceso de instalación, configuración, integración y pruebas será documentado paso a paso.

---

# 🎯 Objetivos

- Implementar un laboratorio SOC desde cero.
- Instalar y configurar Wazuh.
- Implementar FortiGate como firewall.
- Configurar Active Directory.
- Monitorear Windows Server y Windows 10.
- Detectar eventos mediante Sysmon.
- Simular ataques desde Kali Linux.
- Analizar alertas e investigar incidentes.
- Documentar todo el proceso.

---

# 🏗️ Arquitectura del laboratorio

| Máquina Virtual | Sistema Operativo | Función |
|----------------|-------------------|---------|
| Wazuh | Ubuntu Server | SIEM / XDR |
| Firewall | FortiGate | Firewall y seguridad perimetral |
| Servidor | Windows Server 2022 | Active Directory, DNS |
| Cliente | Windows 10 | Endpoint monitoreado |
| Atacante | Kali Linux | Simulación de ataques |

---

# 🌐 Topología

```text
                    Internet
                        │
                 Adaptador NAT
                        │
                 ┌─────────────┐
                 │ FortiGate   │
                 └──────┬──────┘
                        │
                Red Interna SOC
                        │
      ┌─────────┬──────────┬──────────┬─────────┐
      │         │          │          │
 Ubuntu      Windows    Windows     Kali
 Wazuh       Server      10         Linux
```

---

# 🛠️ Herramientas

- FortiGate
- Wazuh
- Windows Server 2022
- Windows 10
- Sysmon
- Kali Linux
- VMware Workstation Pro

---

# 📂 Estructura del proyecto

```
SOC-Lab/
│
├── documentacion/
├── diagramas/
├── capturas/
├── laboratorios/
├── recursos/
│
├── LICENSE
└── README.md
```

---

# 🚀 Estado del proyecto

- [x] Creación del repositorio
- [x] Organización de carpetas
- [ ] Diseño de la topología
- [ ] Instalación de FortiGate
- [ ] Instalación de Wazuh
- [ ] Configuración de Active Directory
- [ ] Instalación de Sysmon
- [ ] Integración de los agentes
- [ ] Desarrollo de laboratorios

---

# 👨‍💻 Autor

**Leonardo Paulino**

Estudiante de Seguridad Informática interesado en SOC, SIEM, Blue Team y Respuesta a Incidentes.
