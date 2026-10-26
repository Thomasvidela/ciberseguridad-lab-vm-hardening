# Laboratorio de Despliegue y Hardening de Máquina Virtual (Ubuntu Desktop)

Este repositorio documenta la configuración inicial, aislamiento y aseguramiento básico (*hardening*) de una máquina virtual sobre Oracle VirtualBox, destinada a entornos de laboratorio de ciberseguridad.

---

## 🛠️ Especificaciones del Entorno

* **Hipervisor:** Oracle VM VirtualBox
* **Sistema Operativo Guest:** Ubuntu Desktop 26.04 LTS (x86_64)
* **Recursos asignados:**
  * **vCPU:** 2 núcleos
  * **RAM:** 4096 MB (4 GB)
  * **Memoria de video:** 128 MB (Controlador VBoxSVGA)
  * **Disco Virtual:** 25 GB (Almacenamiento dinámico)
  * **Red:** Modo NAT (Aislamiento básico del host y red externa)

---

## 📋 Justificación de Decisiones Técnicas

1. **Elección del Sistema Operativo (Ubuntu Desktop):** Proporciona un entorno Linux robusto, seguro y ampliamente utilizado en auditorías y laboratorios de ciberseguridad.
2. **Dimensionamiento de Recursos:** Se asignaron 4 GB de RAM y 2 vCPUs para garantizar estabilidad durante la descompresión de paquetes y el uso de herramientas de análisis sin degradar el rendimiento de la máquina anfitriona.
3. **Controlador Gráfico (VBoxSVGA):** Se seleccionó el controlador nativo de VirtualBox con 128 MB de VRAM para evitar incompatibilidades del kernel con drivers genéricos (`vmwgfx`) y permitir un escalado visual fluido.
4. **Aislamiento de Red (NAT):** Se estableció el adaptador en modo NAT para permitir salida a internet (descarga de paquetes y parches) evitando que la máquina virtual sea accesible directamente desde la red local o que exponga puertos hacia el exterior.
5. **Generación de Snapshot:** Se creó una instantánea limpia una vez asegurado el sistema, permitiendo restablecer el entorno base ante cualquier fallo o ejecución de pruebas destructivas.

---

## 🚀 Pasos Realizados

### 1. Creación e Instalación de la VM
* Configuración manual del entorno en VirtualBox deshabilitando la instalación desatendida para tener control del particionado y credenciales.
* Instalación del sistema base con creación del usuario de trabajo principal.
* Desmontaje de la imagen ISO tras el reinicio para asegurar el arranque desde el disco duro virtual.

### 2. Hardening Básico del Sistema
Una vez iniciado el sistema operativo, se ejecutaron las siguientes tareas de aseguramiento desde la terminal:

* **Actualización del sistema y dependencias:**
  ```bash
  sudo apt update && sudo apt upgrade -y
