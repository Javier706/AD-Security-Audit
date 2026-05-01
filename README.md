# Auditoría de Seguridad en Active Directory – Vectores de Ataque y Movimiento Lateral

## 📌 Descripción
Auditoría interna simulada en un entorno Windows Server 2022 / Windows 10 siguiendo MITRE ATT&CK. Se explotaron configuraciones por defecto para demostrar riesgos reales.

## 🔍 Técnicas ejecutadas (MITRE ATT&CK)
| TID | Técnica | Herramienta |
|-----|---------|--------------|
| T1557.001 | LLMNR/NBT-NS Poisoning | Responder |
| T1557.001 | SMB Relay | ntlmrelayx |
| T1550.002 | Pass-the-Hash | wmiexec |
| T1110.003 | Password Spraying | crackmapexec |
| T1003 | OS Credential Dumping | crackmapexec + vss |
| T1557 (IPv6) | mitm6 + ntlmrelayx | mitm6 |

## 🛠️ Herramientas usadas
- Responder (poisoning)
- impacket suite (ntlmrelayx, wmiexec)
- crackmapexec
- mitm6
- John the Ripper (cracking de hashes)

## 📊 Resultados
- Captura de hashes NTLMv2 de usuarios (mperez, Administrator)
- Cracking exitoso con rockyou.txt
- Obtención de shell remota en PC-Julio mediante SMB relay
- Dump de SAM y NTDS.dit
- Movimiento lateral con pass-the-hash

## 🛡️ Mitigaciones recomendadas (basadas en MITRE)
- Deshabilitar LLMNR y NetBIOS
- Habilitar SMB Signing obligatorio
- Gestionar cuentas privilegiadas (Protected Users)
- Bloquear tráfico IPv6 no gestionado

## 📄 Informe completo
[Descargar PDF](Evaluacion_AD.pdf)
