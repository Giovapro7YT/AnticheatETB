<div align="center">

# 🛡️ Escape the Backrooms - Speedrun Anti-Cheat & LiveSplit Component

![Version](https://img.shields.io/badge/version-1.0.0-blue.svg)
![LiveSplit](https://img.shields.io/badge/LiveSplit-Compatible-brightgreen.svg)
![Game](https://img.shields.io/badge/Game-Escape%20the%20Backrooms-yellow.svg)

**Select Language / Selecciona tu idioma:**  
[🇬🇧 English](#-english) • [🇪🇸 Español](#-español)

</div>

---

## 🇬🇧 English

A community-built component integrated directly into **LiveSplit** designed to ensure competitive integrity, detect unauthorized modifications, and automatically validate **Escape the Backrooms** speedruns in a lightweight and transparent way.

### 📋 Key Features

* **Native LiveSplit Integration:** Runs directly inside your LiveSplit layout with no need for heavy external background software.
* **File Integrity Verification:** Checks SHA-256 hashes of the game's executables and `.pak` files to ensure no advantage mods, hitbox alterations, or map edits are present.
* **External Process & Injection Detection:** Monitors in real-time for prohibited tools (Cheat Engine, speedhacks, DLL injectors, unauthorized macros, etc.).
* **Config Validation (`Engine.ini` / `GameUserSettings.ini`):** Verifies that engine and graphical parameters stay within leaderboard rules (e.g., preventing full fog/darkness removal or illegal FOV tweaks).
* **Cryptographic Run Log:** Generates a unique verification signature/hash at the end of the run that moderators can easily validate.
* **Zero Performance Impact:** Built in optimized C# to ensure zero impact on FPS or frametimes during gameplay.

### 🚀 Installation

1. Download the latest `.dll` release from the [Releases](https://github.com/YOUR_USERNAME/YOUR_REPO/releases) tab.
2. Move `[FileName].dll` into the `Components` folder inside your **LiveSplit** directory (e.g., `C:\LiveSplit\Components\`).
3. Open **LiveSplit**, right-click on it, and select **Edit Layout...**
4. Click the **`+`** button -> **Other** (or *Control*) -> select **[Your Anti-Cheat Name]**.
5. Make sure the component is active before starting your run attempt.

### ⚙️ How It Works & Status Indicators

During a run, the component displays a live status indicator on your LiveSplit layout (and records it in the session logs):

* 🟢 **VALID / CLEAN:** The game and environment comply with all rules. The run is eligible for leaderboard verification.
* 🟡 **WARNING:** A minor anomaly or config change was detected during the session (requires manual moderator review).
* 🔴 **FLAGGED / INVALID:** A prohibited modification, memory alteration, or corrupted/modified game file was detected.

**Privacy & Data Collection:**  
Out of respect for runners' privacy, this anti-cheat **does not collect any personal data**. It only reads file hashes within the *Escape the Backrooms* installation directory, specific game process memory pointers (game state, version, basic parameters), and active processes strictly related to debugging, memory editing, or prohibited automation tools.

### 📜 Moderation Requirements (Speedrun.com)

1. The component must remain visible on the LiveSplit layout throughout the entire VOD recording (or display the final verification hash at the end of the run).
2. Do not close, remove, or restart the component mid-run.
3. In the event of a false positive, reach out to the moderation team and attach the generated log file located at `[Log Path, e.g., LiveSplit/Logs/]`.

### 🛠️ Building from Source

1. Clone this repository:
   ```bash
   git clone [https://github.com/YOUR_USERNAME/YOUR_REPO.git](https://github.com/YOUR_USERNAME/YOUR_REPO.git)
