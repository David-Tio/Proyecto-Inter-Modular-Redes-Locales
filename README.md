# Proyecto Intermodular - Redes Locales
### Inmobiliaria Chamartín
**Alumno:** David Tío Vallejo  
**Módulo:** Redes Locales (0225)  
**Fecha:** 2026

---

## Descripción del proyecto

Diseño e implementación de la red informática para la Inmobiliaria Chamartín, 
una oficina situada en el centro de Madrid con 15 trabajadores distribuidos 
en varios departamentos. La red está segmentada mediante 8 VLANs para 
mejorar la seguridad, el rendimiento y la organización del tráfico.

---

## Estructura de la red

| VLAN | Nombre | Red | Gateway |
|------|--------|-----|---------|
| 10 | Recepción | 192.168.10.0/24 | 192.168.10.1 |
| 20 | RR.HH. | 192.168.20.0/24 | 192.168.20.1 |
| 30 | Administración | 192.168.30.0/24 | 192.168.30.1 |
| 40 | Producción | 192.168.40.0/24 | 192.168.40.1 |
| 50 | Marketing | 192.168.50.0/24 | 192.168.50.1 |
| 60 | Dirección | 192.168.60.0/24 | 192.168.60.1 |
| 70 | Zona Común (Guests) | 192.168.70.0/24 | 192.168.70.1 |
| 80 | Servidores | 192.168.80.0/24 | 192.168.80.1 |

---

## Dispositivos utilizados

- 1x Router Cisco 2911
- 1x Switch Capa 3 Cisco 3560 (switch central)
- 6x Switches Capa 2 Cisco 2960 (uno por departamento)
- 1x Access Point (VLAN 70 - Zona Común)
- 2x Servidores (VLAN 80)
- 13x PCs
- 6x Impresoras

---

## Servicios de red

- **DHCP:** Configurado en el switch central para todas las VLANs excepto la 70
- **Inter-VLAN routing:** Gestionado por el switch de capa 3
- **ACL:** BLOQUEO_VLAN70 para aislar la zona de invitados
- **NAT:** Configurado en el router para salida a internet
- **Compartición de archivos:** Mediante los servidores de la VLAN 80
- **Compartición de impresoras:** Una impresora por departamento con IP estática

---

## Contenido del repositorio

- `documentacion.docx` → Documentación completa del proyecto
- `presentacion.pptx` → Presentación del proyecto
- `red.pkt` → Simulación en Cisco Packet Tracer

---

## Simulación

La red ha sido simulada completamente en **Cisco Packet Tracer**, verificando:
- Comunicación entre todas las VLANs internas
- Aislamiento correcto de la VLAN 70
- Asignación automática de IPs por DHCP
- Inter-VLAN routing funcionando correctamente
