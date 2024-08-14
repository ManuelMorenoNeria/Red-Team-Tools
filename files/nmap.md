# NMAP
![image](https://github.com/user-attachments/assets/379adca4-3d9a-482b-9eb1-80a6bc979186)

Nmap (Network Mapper) es una herramienta de código abierto ampliamente utilizada en el sector de la cibersegurridad.

Entre sus funciones podemos encontrar:
- Escaneo y detección de puertos
- Escaneo y detección de Hosts
- Escaneo y detección de vulnerabilidades
- Escaneo y detección de versiones de aplicaciones y servicios
# Opciones de Uso de Nmap

## Descubrimiento y Especificación de Puertos

### Opciones de Especificación de Puertos

| Sintaxis | Ejemplo | Descripción |
| --- | --- | --- |
| `-p` | `nmap -p 23 172.16.1.1` | Escaneo de un puerto específico |
| `-p` | `nmap -p 23-100 172.16.1.1` | Escaneo de un rango de puertos específicos |
| `-p` | `nmap -pU:110,T:23-25,443 172.16.1.1` | Escaneo de diferentes tipos de puertos (UDP, TCP) |
| `-p-` | `nmap -p- 172.16.1.1` | Escaneo de todos los puertos |
| `-p` | `nmap -p smtp,https 172.16.1.1` | Escaneo de puertos especificando protocolos |
| `-F` | `nmap -F 172.16.1.1` | Escaneo rápido para mayor velocidad |
| `-p "*" ` | `nmap -p "*" ftp 172.16.1.1` | Escaneo de puertos usando nombres |
| `-r` | `nmap -r 172.16.1.1` | Escaneo secuencial de puertos |

## Descubrimiento de Host /172.16.1.1

| Switch/Sintaxis | Ejemplo | Descripción |
| --- | --- | --- |
| `-sL` | `nmap 172.16.1.1-5 -sL` | Lista los hosts sin escanear |
| `-sn` | `nmap 172.16.1.1/8 -sn` | Deshabilita el escaneo de puertos |
| `-Pn` | `nmap 172.16.1.1-8 -Pn` | Escanea puertos sin descubrimiento de hosts |
| `-PS` | `nmap 172.16.1.185 -PS22-25,80` | Descubrimiento TCP SYN en puertos especificados |
| `-PA` | `nmap 172.16.1.185 -PA22-25,80` | Descubrimiento TCP ACK en puertos especificados |
| `-PU` | `nmap 172.16.1.1-8 -PU53` | Descubrimiento UDP en puerto especificado |
| `-PR` | `nmap 172.16.1.1-1/8 -PR` | Descubrimiento ARP en red local |
| `-n` | `nmap 172.16.1.1 -n` | Sin resolución DNS |

## Tipos de Escaneo

| Switch/Sintaxis | Ejemplo | Descripción |
| --- | --- | --- |
| `-sS` | `nmap 172.16.1.1 -sS` | Escaneo de puertos TCP SYN |
| `-sT` | `nmap 172.16.1.1 -sT` | Escaneo de puertos TCP connect |
| `-sA` | `nmap 172.16.1.1 -sA` | Escaneo de puertos TCP ACK |
| `-sU` | `nmap 172.16.1.1 -sU` | Escaneo de puertos UDP |
| `-Sf` | `nmap -Sf 172.16.1.1` | Escaneo TCP FIN |
| `-sX` | `nmap -SX 172.16.1.1` | Escaneo XMAS |
| `-Sp` | `nmap -Sp 172.16.1.1` | Escaneo de Ping |
| `-SL` | `nmap -SL 172.16.1.1` | Listar hosts sin escanear |

## Detección de Versión

| Switch/Sintaxis | Ejemplo | Descripción |
| --- | --- | --- |
| `-sV` | `nmap 172.16.1.1 -sV` | Intenta encontrar la versión del servicio en el puerto |
| `-sV --version-intensity` | `nmap 172.16.1.1 -sV --version-intensity 6` | Nivel de intensidad de 0 a 9 |
| `-sV --version-all` | `nmap 172.16.1.1 -sV --version-all` | Ajusta nivel de intensidad a 9 |
| `-sV --version-light` | `nmap 172.16.1.1 -sV --version-light` | Modo ligero |
| `-A` | `nmap 172.16.1.1 -A` | Activa detección de SO, versión, scripts y traceroute |
| `-O` | `nmap 172.16.1.1 -O` | Detección remota de SO |

## Especificación de IP 172.16.1.1

| Comando | Descripción |
| --- | --- |
| `nmap 172.16.1.1` | Escaneo de una sola IP |
| `nmap 172.16.1.1 172.16.100.1` | Escaneo de IPs específicas |
| `nmap 172.16.1.1-254` | Escaneo de un rango de IPs |
| `nmap xyz.org` | Escaneo de un dominio |
| `nmap 10.1.1.0/8` | Escaneo usando notación CIDR |
| `nmap -iL scan.txt` | Escaneo de IPs desde un archivo |
| `nmap --exclude 172.16.1.1` | Excluye IPs especificadas del escaneo |

## Uso de Scripts NSE de Nmap

| Comando | Descripción |
| --- | --- |
| `nmap --script= test_script 172.16.1.0/24` | Ejecuta el script especificado contra la IP objetivo |
| `nmap --script-update-db` | Agrega nuevos scripts |
| `nmap -sV -sC` | Uso de scripts predeterminados seguros para escaneo |
| `nmap --script-help="Test Script"` | Obtiene ayuda para un script |

## Prueba de Firewall

| Comando | Descripción |
| --- | --- |
| `nmap -f [172.16.1.1]` | Escaneo de paquetes fragmentados |
| `nmap --mtu [MTU] [172.16.1.1]` | Especifica MTU |
| `nmap -sI [zombie] [172.16.1.1]` | Escaneo con zombie ocioso |
| `nmap --source-port [port] [172.16.1.1]` | Especifica manualmente el puerto de origen |
| `nmap --data-length [size] [172.16.1.1]` | Agrega datos aleatorios |
| `nmap --randomize-hosts [172.16.1.1]` | Aleatoriza el orden de escaneo |
| `nmap --badsum [172.16.1.1]` | Usa un checksum incorrecto |

## Formatos de Salida de Nmap

| Comando | Descripción |
| --- | --- |
| `nmap -oN scan.txt 172.16.1.1` | Salida normal por defecto |
| `nmap -oX scanr.xml 172.16.1.1` | Salida en formato XML |
| `nmap -oG grep.txt 172.16.1.1` | Salida en formato grepable |
| `nmap -oA 172.16.1.1` | Salida en todos los formatos |

## Opciones de Escaneo

| Sintaxis | Descripción |
| --- | --- |
| `nmap -sP 172.16.1.1` | Solo escaneo de ping |
| `nmap -PU 172.16.1.1` | Escaneo de ping UDP |
| `nmap -PE 172.16.1.1` | Ping ICMP echo |
| `nmap -PO 172.16.1.1` | Ping de protocolo IP |
| `nmap -PR 172.16.1.1` | Ping ARP |
| `nmap -Pn 172.16.1.1` | Escaneo sin ping |
| `nmap --traceroute 172.16.1.1` | Traceroute |

## Opciones de Tiempo de Nmap

| Sintaxis | Descripción |
| --- | --- |
| `nmap -T0 172.16.1.1` | Escaneo más lento |
| `nmap -T1 172.16.1.1` | Escaneo cauteloso para evitar IDS |
| `nmap -T2 172.16.1.1` | Escaneo a tiempo moderado |
| `nmap -T3 172.16.1.1` | Escaneo por defecto |
| `nmap -T4 172.16.1.1` | Escaneo agresivo |
| `nmap -T5 172.16.1.1` | Escaneo muy agresivo |

