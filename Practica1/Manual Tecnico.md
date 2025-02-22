# Redes1_1S_2025_201712620
# Luis Andres Calvo Arreaga
# Manual Técnico - Práctica 1 (Redes de Computadoras)

## **1. Introducción**
Este documento detalla la configuración y pruebas realizadas para la implementación de una red local en **Cisco Packet Tracer** siguiendo los requerimientos de la práctica.

## **2. Topología de la Red**
Se configuró una LAN utilizando **dos switches de capa 2 (modelo 2960)** y **30 computadoras distribuidas en 5 departamentos**:

- **Switch 1 (prod)**: Producción Creativa (Arquitectura y Urbanismo, Diseño Gráfico y Publicidad).
- **Switch 2 (admon)**: Administración y Gestión de Proyectos (Renderizado, Recepción, Alta Dirección).

## **3. Tabla de Direcciones IP**
| Dispositivo         | Dirección IP     |  Departamento                   |
|---------------------|------------------|---------------------------------|
| AU-PC1             | 192.168.20.10    | Arquitectura y Urbanismo         |
| AU-PC2             | 192.168.20.11    | Arquitectura y Urbanismo         |
| AU-PC3             | 192.168.20.12    | Arquitectura y Urbanismo         |
| AU-PC4             | 192.168.20.13    | Arquitectura y Urbanismo         |
| AU-PC5             | 192.168.20.14    | Arquitectura y Urbanismo         |
| AU-PC6             | 192.168.20.15    | Arquitectura y Urbanismo         |
| AU-PC7             | 192.168.20.16    | Arquitectura y Urbanismo         |
| AU-PC8             | 192.168.20.17    | Arquitectura y Urbanismo         |
| AU-Laptop1         | 192.168.20.18    | Arquitectura y Urbanismo         |
| AU-Laptop2         | 192.168.20.19    | Arquitectura y Urbanismo         |
| DG-PC1             | 192.168.20.20    | Diseño Gráfico y Publicidad      |
| DG-PC2             | 192.168.20.21    | Diseño Gráfico y Publicidad      |
| DG-PC3             | 192.168.20.22    | Diseño Gráfico y Publicidad      |
| DG-PC4             | 192.168.20.23    | Diseño Gráfico y Publicidad      |
| DG-Laptop1         | 192.168.20.24    | Diseño Gráfico y Publicidad      |
| DG-Laptop2         | 192.168.20.25    | Diseño Gráfico y Publicidad      |
| RM-PC1             | 192.168.20.30    | Renderizado y Modelado 3D        |
| RM-PC2             | 192.168.20.31    | Renderizado y Modelado 3D        |
| RM-PC3             | 192.168.20.32    | Renderizado y Modelado 3D        |
| RM-PC4             | 192.168.20.33    | Renderizado y Modelado 3D        |
| RM-Laptop1         | 192.168.20.34    | Renderizado y Modelado 3D        |
| RM-Laptop2         | 192.168.20.35    | Renderizado y Modelado 3D        |
| RA-PC1             | 192.168.20.40    | Recepción y Administración       |
| RA-PC2             | 192.168.20.41    | Recepción y Administración       |
| RA-Laptop1         | 192.168.20.42    | Recepción y Administración       |
| RA-Laptop2         | 192.168.20.43    | Recepción y Administración       |
| AD-PC1             | 192.168.20.50    | Alta Dirección                   |
| AD-PC2             | 192.168.20.51    | Alta Dirección                   |
| AD-Laptop1         | 192.168.20.52    | Alta Dirección                   |
| AD-Laptop2         | 192.168.20.53    | Alta Dirección                   |

Nota: **XX** corresponde a los últimos dos dígitos del carnet del estudiante.

## **4. Configuración de los Switches**

### **4.1 Configuración del Switch 1 (`prod`)**
```bash
enable
configure terminal
hostname prod
enable secret TU_CARNET
exit
write memory
```

### **4.2 Configuración del Switch 2 (`admon`)**
```bash
enable
configure terminal
hostname admon
enable secret TU_CARNET
exit
write memory
```

## **5. Configuración de PCs**
En cada PC se configuró manualmente la dirección IP y la máscara de subred:

- **IP:** 192.168.XX.X
- **Máscara de subred:** 255.255.255.0

## **6. Pruebas de Conectividad**

### **6.1 Prueba de Ping**
Para validar la conectividad, se realizaron pings entre computadoras de diferentes áreas:

Ejemplo:
```bash
ping 192.168.20.20
ping 192.168.20.30
ping 192.168.20.40
```

## **7. Captura de Paquetes (Modo Simulación)**
Se utilizó el **Modo Simulación** de Packet Tracer para capturar paquetes **ARP** e **ICMP** y verificar el tráfico de la red.

### **7.1 Captura de Configuración de las VPCs**
- **Captura 1:** Configuración de IP en la VPC del área de Arquitectura y Urbanismo.
  ![image](https://github.com/user-attachments/assets/a321f216-cd0c-4338-a710-c2a15115160d)

- **Captura 2:** Configuración de IP en la VPC del área de Diseño Gráfico y Publicidad.
![image](https://github.com/user-attachments/assets/5e59f21a-4c2d-4836-9b8d-30b07dd51f41)

- **Captura 3:** Configuración de IP en la VPC del área de Renderizado y Modelado 3D.
![image](https://github.com/user-attachments/assets/4aa9b519-6c2b-4150-ad3b-13dd6e24126a)

- **Captura 4:** Configuración de IP en la VPC del área de Recepción y Administración.
  ![image](https://github.com/user-attachments/assets/812cc736-aa15-4de1-86c5-1e72641922ee)

- **Captura 5:** Configuración de IP en la VPC del área de Alta Dirección.
  ![image](https://github.com/user-attachments/assets/216a87d1-39bf-4763-9e52-cf9a51616307)


### **7.2 Captura de pings entre hosts**
- **Captura 6:** Ping entre un host del área de Arquitectura y Urbanismo y un host del área de Diseño Gráfico y Publicidad.
  ![image](https://github.com/user-attachments/assets/0aaf0189-31a6-418c-a1a0-ba2b6542ea44)

- **Captura 7:** Ping entre un host del área de Diseño Gráfico y Publicidad y un host del área de Renderizado y Modelado 3D.
  ![image](https://github.com/user-attachments/assets/225ebbc6-064a-45bc-a3e7-1841f859a363)

- **Captura 8:** Ping entre un host del área de Renderizado y Modelado 3D y un host del área de Recepción y Administración.
  ![image](https://github.com/user-attachments/assets/42a6d693-7fb1-4d33-bf73-e7736cdf7460)

- **Captura 9:** Ping entre un host del área de Recepción y Administración y un host del área de Alta Dirección.
![image](https://github.com/user-attachments/assets/2210515c-b5cc-449f-aa0d-9b245270090c)

- **Captura 10:** Ping entre un host del área de Alta Dirección y un host del área de Arquitectura y Urbanismo.
  ![image](https://github.com/user-attachments/assets/153a0f9d-0630-49ce-9727-f2daa2e637d0)


### **7.3 Captura de pantalla de la demostración de la captura de un paquete ARP y un ICMP en el modo Simulación.**
- **Captura 10:**
  ![image](https://github.com/user-attachments/assets/8054dc6e-9e29-4ebb-b2be-dfcf7c7131db)



## **8. Conclusión**
Se logró implementar exitosamente la red cumpliendo con los requerimientos:
- Configuración de switches con hostname y clave.
- Asignación de direcciones IP estáticas.
- Pruebas de conectividad exitosas.
- Análisis de tráfico con el modo simulación.



