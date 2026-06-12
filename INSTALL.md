# Guía de instalación — n52te en Windows 11

Esta guía explica cómo instalar el software del **Belkin / Razer n52te** con el instalador `Instalar-n52te.exe`.

## 📋 Antes de empezar

- **Windows 11 o Windows 10 (64 bits).**
- Necesitarás **permisos de administrador** (el instalador los pide solo).
- Ten el **n52te conectado** por USB (no es imprescindible para instalar, pero sí para probarlo al final).

## 🚀 Instalación paso a paso

### 1. Descarga el instalador
Desde la pestaña **[Releases](../../releases/latest)** del repositorio, descarga **`Instalar-n52te.exe`**.

### 2. Ejecútalo
Haz doble clic en `Instalar-n52te.exe`.

### 3. Aviso de SmartScreen (normal)
Como es software gratuito sin firma digital de pago, Windows puede mostrar **"Windows protegió tu PC"**:

> Pulsa **Más información** → **Ejecutar de todas formas**.

### 4. Acepta el control de cuentas (UAC)
Windows pedirá permiso de administrador (hace falta para instalar el driver). Pulsa **Sí**.

### 5. Pulsa "Instalar"
En la ventana del instalador, pulsa **Instalar**. El proceso:
1. Limpia restos de drivers antiguos de Belkin.
2. Instala el driver **Interception**.
3. Copia el editor y el remapeador a `C:\Program Files\n52te`.
4. Crea accesos directos en el Escritorio y el menú Inicio.
5. Deja el n52te listo.

### 6. Reinicia si te lo pide
La **primera vez** que se instala el driver, Windows necesita **reiniciar** para activarlo. Si el instalador te lo indica, pulsa **Reiniciar ahora** (o reinicia cuando quieras). Si el driver ya estaba activo, no hace falta reiniciar.

## 🎮 Primer uso

1. Abre **Editor n52te** (acceso directo en el Escritorio).
2. Haz clic en un botón del dibujo del keypad (o pulsa **Identificar** y aprieta un botón físico del n52te).
3. Elige qué hace el botón (una tecla, una combinación, un texto o abrir un programa) y pulsa **Asignar a este botón**.
4. **Para probarlo, haz clic FUERA del editor** (mientras el editor está delante, el n52te escribe en crudo) y pulsa el botón en el n52te.
5. Marca **"Iniciar el remapeador con Windows"** si quieres que funcione siempre, sin abrir nada.

> 💡 Tu teclado normal **no se ve afectado** en ningún momento: solo se remapean las teclas del n52te.

## 🔄 Desinstalar

1. **Quitar el inicio automático**: abre el Editor y desmarca *"Iniciar el remapeador con Windows"*.
2. **Borrar los archivos**: elimina la carpeta `C:\Program Files\n52te` y los accesos directos.
3. **(Opcional) Quitar el driver Interception**: abre PowerShell **como administrador** y ejecuta:
   ```powershell
   & "C:\Program Files\n52te\install-interception.exe" /uninstall
   ```
   Luego reinicia. (Si ya borraste la carpeta, descarga Interception desde su [repositorio oficial](https://github.com/oblitum/Interception) para desinstalarlo.)

## 🆘 Problemas frecuentes

| Síntoma | Solución |
|---|---|
| El editor dice *"el remapeador no está abierto"* | Abre el acceso directo **Remapeador n52te**, o marca *"Iniciar con Windows"* y reinicia. |
| Asigné una tecla y no cambia | Recuerda hacer clic **fuera** del editor antes de probar el botón. |
| *"Acceso denegado"* al guardar | No debería pasar (la config va a `%ProgramData%`). Si ocurre, ejecuta el editor como administrador una vez. |
| El n52te no aparece | Comprueba que esté conectado y que el driver cargó: reinicia tras la instalación. |
| El teclado se comportó raro al instalar | Reinicia el equipo; el estado se reinicia limpio. |

## ❓ ¿Necesito desactivar la Integridad de memoria?

**No.** El driver Interception que usa este proyecto es compatible con la Integridad de memoria (HVCI) de Windows 11, a diferencia del driver original de Belkin de 2008. No tienes que desactivar ninguna protección.

---

<sub>Hecho por <b>INFOMALENA</b> · Software Development</sub>
