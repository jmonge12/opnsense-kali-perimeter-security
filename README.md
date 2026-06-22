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


### 🖥️ FASE 1: CONFIGURACIÓN E IMPLEMENTACIÓN

#### [Evidencia 1: Topología de Red en VirtualBox]
> *Espacio reservado para verificar los dos adaptadores de OPNsense (Puente y Solo Anfitrión).*
[Por favor, subí la Captura 1 aquí]

---

#### [Evidencia 2: Consola de OPNsense]
> *Espacio reservado para verificar la asignación correcta de las IPs en WAN y LAN desde la CLI.*
[Por favor, subí la Captura 2 aquí]

---

#### [Evidencia 3: Dashboard Principal Web GUI]
> *Espacio reservado para verificar el ingreso exitoso a la administración desde Kali Linux.*
[Por favor, subí la Captura 3 aquí]

---

### 🧪 FASE 2: PRUEBAS DE CONCEPTO Y POLÍTICAS

#### [Evidencia 4: Prueba de Conectividad Exitosa (Paso A)]
> *Espacio reservado para verificar el ping exitoso de Kali a internet tras añadir el gateway.*
[Por favor, subí la Captura 4 aquí]

---

#### [Evidencia 5: Política de Seguridad / Regla de Bloqueo (Paso B)]
> *Espacio reservado para verificar la regla conmutada a 'Block' en la interfaz LAN.*
[Por favor, subí la Captura 5 aquí]

---

#### [Evidencia 6: Evidencia de Auditoría y Logs en Live View (Paso C)]
> *Espacio reservado para verificar las trazas con la 'X' roja interceptando el tráfico de Kali.*
[Por favor, subí la Captura 6 aquí]


---

