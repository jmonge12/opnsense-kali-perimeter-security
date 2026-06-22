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

> ![Evidencia 1: Configuración de adaptadores de red en VirtualBox](https://github.com/jmonge12/opnsense-kali-perimeter-security/blob/082877509499cd76ce4b850a50b07967cf558085/Topologia%20de%20red.png)
---

#### [Evidencia 2: Consola de OPNsense]

> ![Evidencia 2: Consola de OPNsense](https://github.com/jmonge12/opnsense-kali-perimeter-security/blob/381acc9121fb849646d09d626ccc9aa961afc03a/consola%20de%20OPNSense.png)
---

#### [Evidencia 3: Dashboard Principal Web GUI]

> ![Evidencia 3: Dashboard Principal Web GUI](https://github.com/jmonge12/opnsense-kali-perimeter-security/blob/ec3103bd9588ae258e676e522be2aa0c208c28bb/Dashboard%20Principal%20Web%20GUI.png)
---

### 🧪 FASE 2: PRUEBAS DE CONCEPTO Y POLÍTICAS

#### [Evidencia 4: Prueba de Conectividad Exitosa (Paso A)]

> ![Evidencia 4: Prueba de Conectividad Exitosa](https://github.com/jmonge12/opnsense-kali-perimeter-security/blob/44ffc6f3217168623127c8f28797e009ae5b2ffc/Prueba%20de%20Conectividad%20Exitosa.png)

---

#### [Evidencia 5: Política de Seguridad / Regla de Bloqueo (Paso B)]

> ![Evidencia 5: Política de Seguridad / Regla de Bloqueo](https://github.com/jmonge12/opnsense-kali-perimeter-security/blob/63379e75daec110a6dfdcf1d80fbea507093c467/Pol%C3%ADtica%20de%20Seguridad%20%20Regla%20de%20Bloqueo.png)
---

#### [Evidencia 6: Evidencia de Auditoría y Logs en Live View (Paso C)]

> ![Evidencia 6: Evidencia de Auditoría y Logs en Live View](https://github.com/jmonge12/opnsense-kali-perimeter-security/blob/c29389ffef8de5d407c588e5b0cd2f0bf239d9b5/Evidencia%20de%20Auditor%C3%ADa%20y%20Logs%20en%20Live%20View.png)


---

Para resumir el trabajo realizado en este laboratorio, las seis capturas de pantalla demuestran el proceso completo de principio a fin:

Fase de Montaje (Evidencias 1 a 3): Primero se ve cómo se separaron las redes en VirtualBox (dejando a Kali aislado en una red interna y a OPNsense conectando esa red con el mundo exterior). Luego, se muestra la consola negra del firewall con las IPs listas y el acceso exitoso al panel web desde el navegador de Kali para terminar de configurar el sistema.

Fase de Pruebas (Evidencias 4 a 6): Aquí se pasa a la acción. Primero se demuestra que el internet funcionaba bien en Kali (haciendo un ping exitoso a Google). Después, se ve el cambio drástico cuando activamos la regla de bloqueo (Block) en el firewall, y finalmente se muestra la prueba reina: la pantalla de logs en tiempo real llena de alertas rojas que confirman cómo el firewall detectó, frenó y rechazó el tráfico de Kali al instante.

