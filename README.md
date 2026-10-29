## 📸 Evidencias del Proceso

### 1. Configuración de Hardware
Asignación de recursos moderados (2 vCPUs, memoria RAM optimizada y memoria de video dedicada con aceleración gráfica).

<p align="center">
  <img src="evidencia/cpu_config.png" alt="Configuración de CPU" width="85%">
</p>

<p align="center">
  <img src="evidencia/placa_base_config.png" alt="Configuración de Placa Base y Memoria RAM" width="85%">
</p>

<p align="center">
  <img src="evidencia/gpu_config.png" alt="Configuración de Pantalla y Video" width="85%">
</p>

---

### 2. Aislamiento de Red (Modo NAT)
Configuración previa al primer encendido estableciendo el adaptador en modo NAT para garantizar el aislamiento de la red física local.

<p align="center">
  <img src="evidencia/red_config.png" alt="Configuración de Red en Modo NAT" width="85%">
</p>

---

### 3. Despliegue del Sistema Operativo
Inicio y validación de la sesión en Ubuntu Desktop con el usuario de trabajo configurado.

<p align="center">
  <img src="evidencia/screen_2.png" alt="Sistema Operativo Instalado" width="85%">
</p>

---

### 4. Hardening Básico
Aplicación de medidas básicas de aseguramiento: actualización de repositorios y paquetes, auditoría de puertos/servicios y activación del firewall UFW.

<p align="center">
  <img src="evidencia/screen_1.png" alt="Hardening Básico y Firewall" width="85%">
</p>

---

### 5. Usuario sin privilegios

Creación de un usuario estándar (sin permisos de administrador) y listado de los usuarios del sistema.

<p align="center">
  <img src="evidencia/usuarios.png" alt="Creación y listado de usuarios" width="85%">
</p>

---

### 6. Actualización del sistema

Ejecución de `apt update` y `apt upgrade` sin errores, con confirmación de que no quedan paquetes pendientes.

<p align="center">
  <img src="evidencia/actualizacion.png" alt="Actualización de paquetes" width="85%">
</p>

---

### 7. Snapshot "Hardening Inicial"

Creación del punto de restauración en VirtualBox para preservar el estado limpio y seguro de la máquina, con el usuario estándar creado y el sistema actualizado.

<p align="center">
  <img src="evidencia/snapshoot.png" alt="Snapshot Hardening Inicial en VirtualBox" width="85%">
</p>
