# 🛡️ Escape the Backrooms - Speedrun Anti-Cheat & LiveSplit Component

![Version](https://img.shields.io/badge/version-1.0.0-blue.svg)
![LiveSplit](https://img.shields.io/badge/LiveSplit-Compatible-brightgreen.svg)
![Game](https://img.shields.io/badge/Game-Escape%20the%20Backrooms-yellow.svg)

---

# 🇬🇧 English

A community-built component integrated directly into **LiveSplit** designed to ensure competitive integrity, detect unauthorized modifications, and automatically validate **Escape the Backrooms** speedruns in a lightweight and transparent way.

## 📋 Key Features

* **Native LiveSplit Integration:** Runs directly inside your LiveSplit layout with no need for heavy external background software.
* **File Integrity Verification:** Checks SHA-256 hashes of the game's executables and `.pak` files to ensure no advantage mods, hitbox alterations, or map edits are present.
* **External Process & Injection Detection:** Monitors in real-time for prohibited tools (Cheat Engine, speedhacks, DLL injectors, unauthorized macros, etc.).
* **Config Validation (`Engine.ini` / `GameUserSettings.ini`):** Verifies that engine and graphical parameters stay within leaderboard rules (e.g., preventing full fog/darkness removal or illegal FOV tweaks).
* **Cryptographic Run Log:** Generates a unique verification signature/hash at the end of the run that moderators can easily validate.
* **Zero Performance Impact:** Built in optimized C# to ensure zero impact on FPS or frametimes during gameplay.

## 🚀 Installation

1. Download the latest `.dll` release from the [Releases](https://github.com/Giovapro7YT/AnticheatETB/releases) tab.
2. Move `AnticheatETB.dll` into the `Components` folder inside your **LiveSplit** directory (e.g., `C:\LiveSplit\Components\`).
3. Open **LiveSplit**, right-click on it, and select **Edit Layout...**
4. Click the **`+`** button -> **Other** (or *Control*) -> select **AnticheatETB**.
5. Make sure the component is active before starting your run attempt.

## ⚙️ How It Works & Status Indicators

During a run, the component displays a live status indicator on your LiveSplit layout (and records it in the session logs):

* 🟢 **VALID / CLEAN:** The game and environment comply with all rules. The run is eligible for leaderboard verification.
* 🟡 **WARNING:** A minor anomaly or config change was detected during the session (requires manual moderator review).
* 🔴 **FLAGGED / INVALID:** A prohibited modification, memory alteration, or corrupted/modified game file was detected.

### Privacy & Data Collection
Out of respect for runners' privacy, this anti-cheat **does not collect any personal data**. It only reads:
* File hashes within the *Escape the Backrooms* installation directory.
* Specific game process memory pointers (game state, version, basic parameters).
* Active processes strictly related to debugging, memory editing, or prohibited automation tools.

## 📜 Moderation Requirements (Speedrun.com)

For a run to be accepted using this tool:
1. The component must remain visible on the LiveSplit layout throughout the entire VOD recording (or display the final verification hash at the end of the run).
2. Do not close, remove, or restart the component mid-run.
3. In the event of a false positive, reach out to the moderation team and attach the generated log file located at `[Log Path, e.g., LiveSplit/Logs/]`.

## 🛠️ Building from Source

1. Clone this repository:
   ```bash
   git clone https://github.com/Giovapro7YT/AnticheatETB.git
   ```
2. Open the `.sln` solution in **Visual Studio 2022**.
3. Ensure `LiveSplit.Core.dll` is properly referenced in the project dependencies.
4. Build in **Release** mode (`x64` / `Any CPU`).

## 🤝 Credits & Contact

* **Developed by:** Giovapro7YT
* **Community:** https://discord.com/invite/6HSRuuxGqr
* **Bug Reports / False Positives:** Open an *Issue* in this repository or message me on Discord (`giovapro7ytoficial`).

*This project is an independent community tool created to support the Escape the Backrooms speedrunning scene and is not officially affiliated with Fancy Games.*

---
---

# 🇪🇸 Español

Un componente comunitario integrado directamente en **LiveSplit** diseñado para garantizar la integridad competitiva, detectar modificaciones no autorizadas y validar runs de **Escape the Backrooms** de forma ligera, automática y transparente.

## 📋 Características Principales

* **Integración Nativa en LiveSplit:** Funciona directamente dentro de tu layout sin necesidad de ejecutar programas externos pesados en segundo plano.
* **Verificación de Integridad de Archivos:** Comprueba los hashes (SHA-256) de los ejecutables y archivos `.pak` del juego para asegurar que no hay mods de ventaja, cambios de hitboxes o modificaciones en los mapas.
* **Detección de Inyección y Procesos Externos:** Monitorea en tiempo real el uso de herramientas prohibidas (Cheat Engine, modificadores de velocidad/Speedhack, inyectores de DLL, macros no permitidas, etc.).
* **Validación de Configuración (`Engine.ini` / `GameUserSettings.ini`):** Verifica que los parámetros gráficos y del motor no excedan los límites permitidos por las reglas de la leaderboard (ej. eliminación total de niebla/oscuridad o modificaciones de FOV ilegales).
* **Registro Criptográfico de la Run (Run Log):** Genera una firma/código de verificación único al finalizar la partida que los moderadores pueden comprobar fácilmente.
* **Cero Impacto en el Rendimiento:** Diseñado en C# optimizado para no afectar los FPS ni el frametime durante la partida.

## 🚀 Instalación

1. Descarga la última versión del archivo `.dll` desde la sección de [Releases](https://github.com/Giovapro7YT/AnticheatETB/releases).
2. Mueve el archivo `AnticheatETB.dll` a la carpeta `Components` dentro del directorio donde tienes instalado **LiveSplit** (ej. `C:\LiveSplit\Components\`).
3. Abre **LiveSplit**, haz clic derecho sobre él y selecciona **Edit Layout...**
4. Haz clic en el botón **`+`** -> **Other** (o *Control*) -> selecciona **[Nombre de tu Anti-Cheat]**.
5. Asegúrate de que el componente esté activo antes de iniciar tu intento.

## ⚙️ Cómo Funciona y Estados del Indicador

Durante la run, el componente mostrará un estado visual en tu layout de LiveSplit (y lo guardará en los logs internos):

* 🟢 **VALID / CLEAN:** El juego y el entorno cumplen con todas las normativas. La run es elegible para verificación.
* 🟡 **WARNING:** Se detectó una anomalía menor o un cambio de configuración durante la sesión (requiere revisión manual).
* 🔴 **FLAGGED / INVALID:** Se detectó una modificación prohibida, alteración de memoria o archivo corrupto.

### Privacidad y Recopilación de Datos
Por respeto a la privacidad de los corredores, este anti-cheat **no recopila información personal**. Únicamente lee:
* Hashes de los archivos del directorio de *Escape the Backrooms*.
* Punteros específicos de memoria del proceso del juego (estado de partida, versión, parámetros básicos).
* Procesos activos estrictamente relacionados con herramientas de depuración, edición de memoria o automatización prohibida.

## 📜 Requisitos para Moderación (Speedrun.com)

Para que una run sea aceptada utilizando esta herramienta:
1. El componente debe ser visible en el layout de LiveSplit durante toda la grabación del VOD (o mostrar el código de verificación al final de la run).
2. No se debe cerrar, quitar ni reiniciar el componente a mitad de una partida válida.
3. En caso de falso positivo, contacta con el equipo de moderación adjuntando el archivo de log generado en `[Ruta del Log, ej. LiveSplit/Logs/]`.

## 🛠️ Compilación desde el Código Fuente

1. Clona este repositorio:
   ```bash
   git clone https://github.com/Giovapro7YT/AnticheatETB.git
   ```
2. Abre la solución `.sln` en **Visual Studio 2022**.
3. Asegúrate de tener referenciada la librería `LiveSplit.Core.dll` en las dependencias del proyecto.
4. Compila en modo **Release** (`x64` / `Any CPU`).

## 🤝 Créditos y Contacto

* **Desarrollado por:** Giovapro7YT
* **Comunidad:** https://discord.com/invite/6HSRuuxGqr
* **Reportar Bugs / Falsos Positivos:** Abre un *Issue* en este repositorio o contáctame vía Discord (`Giovapro7YT`).

*Este proyecto es una herramienta independiente creada para apoyar la escena competitiva de Escape the Backrooms y no está afiliada oficialmente con Fancy Games.*
