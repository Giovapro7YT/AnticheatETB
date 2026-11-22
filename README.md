# 🛡️ Escape the Backrooms - Speedrun Anti-Cheat & LiveSplit Component

![Version](https://img.shields.io/badge/version-1.0.0-blue.svg)
![LiveSplit](https://img.shields.io/badge/LiveSplit-Compatible-brightgreen.svg)
![Game](https://img.shields.io/badge/Game-Escape%20the%20Backrooms-yellow.svg)

Un componente oficial/comunitario integrado directamente en **LiveSplit** diseñado para garantizar la integridad competitiva, detectar modificaciones no autorizadas y validar runs de **Escape the Backrooms** de forma automática y transparente.

---

## 📋 Características Principales

* **Integración Nativa en LiveSplit:** Funciona directamente dentro de tu layout sin necesidad de ejecutar programas externos pesados en segundo plano.
* **Verificación de Integridad de Archivos:** Comprueba los hashes (SHA-256) de los ejecutables y archivos `.pak` del juego para asegurar que no hay mods de ventaja, cambios de hitboxes o modificaciones en los mapas.
* **Detección de Inyección y Procesos Externos:** Monitorea en tiempo real el uso de herramientas prohibidas (Cheat Engine, modificadores de velocidad/Speedhack, inyectores de DLL, etc.).
* **Validación de Configuración (`Engine.ini` / `GameUserSettings.ini`):** Verifica que los parámetros gráficos y de motor no excedan los límites permitidos por las reglas de la leaderboard (ej. eliminación total de niebla/oscuridad o modificaciones de FOV ilegales).
* **Registro Criptográfico de la Run (Run Log):** Genera una firma/código de verificación único al finalizar la partida que los moderadores pueden comprobar fácilmente.
* **Cero Impacto en el Rendimiento:** Diseñado en C# optimizado para no afectar los FPS ni el frametime durante la partida.

---

## 🚀 Instalación

1. Descarga la última versión del archivo `.dll` desde la sección de [Releases](https://github.com/TU_USUARIO/TU_REPO/releases).
2. Mueve el archivo `[NombreDelArchivo].dll` a la carpeta `Components` dentro del directorio donde tienes instalado **LiveSplit** (ej. `C:\LiveSplit\Components\`).
3. Abre **LiveSplit**, haz clic derecho sobre él y selecciona **Edit Layout...**
4. Haz clic en el botón **`+`** -> **Other** (o *Control*) -> selecciona **[Nombre de tu Anti-Cheat]**.
5. Asegúrate de que el componente esté activo antes de iniciar tu intento.

---

## ⚙️ Cómo Funciona y Estados del Indicador

Durante la run, el componente mostrará un estado visual en tu layout de LiveSplit (o en los logs internos):

* 🟢 **VALID / CLEAN:** El juego y el entorno cumplen con todas las normativas. La run es elegible para verificación.
* 🟡 **WARNING:** Se detectó una anomalía menor o un cambio de configuración durante la sesión (requiere revisión manual).
* 🔴 **FLAGGED / INVALID:** Se detectó una modificación prohibida, alteración de memoria o archivo corrupto.

### ¿Qué datos se recopilan?
Por respeto a la privacidad de los corredores, este anti-cheat **no recopila información personal**. Únicamente lee:
* Hashes de los archivos del directorio de *Escape the Backrooms*.
* Variables específicas de memoria del proceso del juego (estado de partida, versión, parámetros básicos).
* Lista de procesos activos relacionados con herramientas de depuración o alteración de memoria.

---

## 📜 Requisitos para Moderación (Speedrun.com)

Para que una run sea aceptada utilizando esta herramienta:
1. El componente debe ser visible en el layout de LiveSplit durante toda la grabación del VOD (o mostrar el código de verificación al final de la run).
2. No se debe cerrar ni reiniciar el componente a mitad de una partida válida.
3. En caso de falso positivo, contacta con el equipo de moderación adjuntando el archivo de log generado en `[Ruta del Log, ej. LiveSplit/Logs/]`.

---

## 🛠️ Compilación desde el Código Fuente (Para Desarrolladores)

Si deseas auditar el código o compilarlo por tu cuenta:

1. Clona este repositorio:
   ```bash
   git clone [https://github.com/TU_USUARIO/TU_REPO.git](https://github.com/TU_USUARIO/TU_REPO.git)
