# http-traffic-analysis
HTTP Traffic Analysis with tcpdump and Wireshark (SOC Lab)
# HTTP Traffic Analysis - Suspicious Activity Detection

## Description (English)
In this lab, HTTP network traffic was analyzed to identify potentially suspicious activity on a web server.

## Descripción (Español)
En este laboratorio se analizó tráfico HTTP con el objetivo de identificar actividad potencialmente sospechosa en un servidor web.

---

## Scenario / Escenario
- Kali Linux → Traffic generation / Generación de tráfico  
- Metasploitable → Web server / Servidor web  
- tcpdump → Traffic capture / Captura de tráfico  
- Wireshark → Packet analysis / Análisis de paquetes  

---

## Methodology / Metodología

Traffic was captured using tcpdump:

tcpdump -i eth0 port 80 -w http_lab.pcap

Then analyzed in Wireshark using the filter:

http.request

---

## Analysis / Análisis

Multiple HTTP GET requests were identified from:

- Source: 192.168.93.128 (Kali)
- Destination: 192.168.93.130 (Server)

Example:

GET /shell.php HTTP/1.1

---

## Findings / Hallazgos

The request to `/shell.php` is considered suspicious.

Este tipo de endpoint suele estar asociado a:
- webshells
- accesos no autorizados
- mecanismos de persistencia

---

## Interpretation / Interpretación

This behavior may indicate:
- Web exploitation attempts  
- Unauthorized access attempts  
- Reconnaissance activity  

Este comportamiento puede indicar:
- intentos de explotación web  
- acceso a archivos maliciosos  
- reconocimiento del sistema  

---

## Tools Used / Herramientas utilizadas
- tcpdump  
- Wireshark  
- curl  
- Linux  

---

## Conclusion / Conclusión



Network traffic analysis allows early detection of suspicious activity.

El análisis de tráfico de red permite detectar actividad sospechosa en etapas tempranas, siendo una tarea clave dentro de un SOC.
