# AIC8800 Wi-Fi Driver para Linux Kernel 6.8+

Soy nuevo y es mi primer aporte, este repositorio contiene una versión funcional del driver para el chip Wi-Fi AIC8800 para Tenda_AIC8800DC, adaptada para ser compatible con kernels de Linux 6.8 y versiones posteriores.

## 🔧 Problema solucionado

Los drivers oficiales de AIC8800 presentan errores de compilación en kernels recientes debido a cambios en los headers del kernel (como `struct proc_ops`, entre otros). Este repositorio corrige esos errores y permite compilar e instalar el módulo correctamente.

## ✅ Probado en

- Linux Mint 22.1 Cinnamon con kernel `6.8.0-58-generic`
- Adaptador Wi-Fi Tenda AIC8800DC (AX300) con chip AIC8800
- Herramientas de compilación (`build-essential`, `linux-headers`, `git`)

## 🚀 Instrucciones de instalación

1. Descarga el repositorio
   ```bash
   git clone https://github.com/tu-usuario/aic8800-linux-driver.git

2. Abre la terminal en el archivo descargado y compilalo
   ```bash
   cd aic8800-linux-driver
   make

3. Instalalo
   ```bash
   sudo make install

4. Carga el módulo manualmente (solo la primera vez)
   ```bash
   sudo modprobe aic8800_fdrv

5. Verifica que esté cargado correctamente
   ```bash
   dmesg | grep aic

En caso de que el driver no inicie automáticamente puedes agregar el nombre del módulo al archivo:
```bash
echo "aic8800_fdrv" | sudo tee -a /etc/modules
```
## 🧠 Créditos: 
- Basado en el driver oficial de ASR Microelectronics
  
- Gracias a https://github.com/Z0mbl03 por su video que explicaba como instalar el driver y a https://github.com/DIGITALMAN7, ambos corrigieron el driver pero no me funcionó por el tema del kernel 6.8+

- Modificado por ElWichita94 para compatibilidad con Linux 6.8+

## 📜 Licencia
Este proyecto se publica con fines educativos y de compatibilidad. Respeta las licencias originales del código del fabricante.
