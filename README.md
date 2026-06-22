# Laboratorio de Seguridad Perimetral: Despliegue y Configuración de Firewall OPNsense con Kali Linux

## 📝 Descripción del Proyecto
Este proyecto documenta el diseño, la implementación y la validación de un entorno de red seguro utilizando el firewall de código abierto **OPNsense** como sistema de prevención y mitigación de riesgos perimetrales. A través de este laboratorio, se aisló una máquina de auditoría (**Kali Linux**) dentro de un segmento de red controlado (LAN) para inspeccionar, auditar y filtrar todo su tráfico entrante y saliente hacia la red externa (WAN), aplicando políticas de seguridad basadas en el filtrado de paquetes en tiempo real.

---

## 🛠️ Requisitos del Entorno e Infraestructura
* **Hipervisor:** VirtualBox
* **Firewall:** OPNsense 26.1.6 (Basado en FreeBSD)
* **Sistema de Auditoría:** Kali Linux
* **Topología de Red Virtual:**
  * **Interfaz WAN (OPNsense):** Configurada en modo *Adaptador Puente* para simular la salida perimetral directa a Internet.
  * **Interfaz LAN (OPNsense y Kali):** Configurada en modo *Adaptador solo anfitrión (Host-Only)*, aislando por completo el tráfico local bajo el control exclusivo del firewall.

---

## ⚙️ Configuración e Implementación Step-by-Step

### 1. Arquitectura de Red en el Hipervisor
Se configuraron las interfaces de red de los sistemas virtuales asegurando la separación física y lógica de las zonas (WAN y LAN) antes de inicializar los sistemas operativos.

![1. Configuración de Adaptadores de Red en VirtualBox](AQUÍ_VA_TU_CAPTURA_1_DE_VIRTUALBOX)

### 2. Inicialización y Asignación de Interfaces en OPNsense
Al arrancar el sistema operativo del firewall, se mapearon correctamente las interfaces físicas virtuales de FreeBSD (`em0` para la WAN y `em1` para la LAN), logrando el direccionamiento automático e interno en segmentos totalmente independientes.

![2. Consola de OPNsense con Direccionamiento IP](AQUÍ_VA_TU_CAPTURA_2_DE_CONSOLA_OPNSENSE)

### 3. Acceso al Panel de Administración (Web GUI)
Conectando el entorno gráfico desde la zona segura local (LAN), se logró ingresar a la interfaz web de OPNsense para llevar a cabo el asistente técnico inicial (*Deployment Wizard*), donde se establecieron los parámetros de optimización para redes estándar e individuales.

![3. Dashboard Principal de OPNsense en Firefox](AQUÍ_VA_TU_CAPTURA_3_DE_DASHBOARD)

---

## 🧪 Validación de Enrutamiento y Pruebas de Concepto

### Paso A: Verificación de Conectividad y NAT (Tráfico Permitido)
Dado que la red *Host-Only* carece de una ruta de salida predeterminada automática, se procedió a inyectar manualmente el gateway apuntando directamente a la IP de la interfaz LAN del firewall. Una vez establecido, se verificó la navegación exitosa hacia el exterior.

```bash
# Inyección manual del gateway por defecto en Kali Linux
sudo ip route add default via 192.168.56.103 dev eth0

# Validación de conectividad (ICMP) hacia Internet
ping -c 4 8.8.8.8
