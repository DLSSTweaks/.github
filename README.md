# 🎮 DLSSTweaks

Wrapper DLL tool that can force **DLAA** onto DLSS-supported titles, along with tweaking scaling ratios and DLSS presets.

---

## 🔗 Get the Latest Release

* [📦 View All Releases](https://github.com/DLSSTweaks/.github/releases)

---

## ✨ DLSS 4.5 Update

**DLSS 2nd-generation Transformer models** can now be enabled via **Preset L** and **Preset M**.

To use them:

1. Ensure your game includes **DLSS v310.5.0** or newer.
2. Open your DLSSTweaks configuration.
3. Navigate to the **DLSSPresets** section.
4. Set the desired preset to **L** or **M**.

If DLSSTweaks has been useful, consider supporting future development. Thank you!

---

## 🚀 Setup

Most games can have DLSSTweaks applied in just a few steps.

### 1. Download

Download the latest release ZIP and extract it next to the game's main executable.

> **Note:** The executable may be located inside subfolders. For Unreal Engine games, it is often named:
>
> ```text
> GameName-Win64-Shipping.exe
> ```

### 2. Run the Configuration Tool

Launch:

```text
DLSSTweaksConfig.exe
```

If required, the tool will automatically prompt you to enable the NVIDIA signature override needed for DLSSTweaks to load.

### 3. Configure Tweaks

Choose the settings you want to apply.

For example:

* Enable **ForceDLAA** to replace DLSS with DLAA.
* Adjust custom scaling ratios.
* Override DLSS presets.
* Configure advanced options.

Hover over any setting inside the tool to view additional information.

### 4. Save & Launch

Save your configuration and start the game.

If DLSSTweaks loads successfully, a log file should appear:

```text
dlsstweaks.log
```

next to the game's executable.

---

## ⚠️ Compatibility Note

Some newer games that ship with **DLSS v3.8+** may not support the default loading method.

In these cases, one of the alternative wrapper filenames listed below may work instead.

Games originally released with **DLSS 3.7 or older** generally continue to work correctly even when manually updated to newer DLSS versions.

---

## 🛠 Automatic Installation

The DLSSTweaksConfig tool can automatically select the correct wrapper filename.

1. Extract DLSSTweaks somewhere outside the game folder.
2. Run `DLSSTweaksConfig.exe`.
3. Select **Copy to Game Folder**.
4. Choose the game directory.

The tool will automatically detect compatible wrapper names and install the required files.

---

# 🔧 Advanced Setup

## Alternate DLL Wrapper Filenames

DLSSTweaks supports multiple wrapper filenames.

Depending on the game, one of these may successfully load the mod:

```text
XInput1_3.dll
XInput1_4.dll
XInput9_1_0.dll
dxgi.dll
XAPOFX1_5.dll
X3DAudio1_7.dll
winmm.dll
```

### Recommended Wrappers

The following generally have the highest success rate:

```text
dxgi.dll
winmm.dll
XInput1_3.dll
XInput1_4.dll
```

If a game fails to work with any supported filename, please report it so compatibility can be improved.

---

## nvngx.dll Wrapping

Renaming the wrapper DLL to:

```text
nvngx.dll
```

allows DLSSTweaks to wrap the DLSS module directly.

This method previously provided the highest compatibility with older games, but NVIDIA's removal of the signature override means results may vary on newer titles.

### Requirements

A registry modification is required to disable NVIDIA's signature verification for the wrapped DLL.

The configuration tool can automatically apply this change.

Alternatively, run:

```text
EnableNvidiaSigOverride.reg
```

and approve all prompts.

To remove the modification later:

```text
DisableNvidiaSigOverride.reg
```

---

## ⚠️ Online Games Warning

Using the `nvngx.dll` wrapping method is **not recommended for online games**.

The code-hooking techniques used are similar to methods employed by some game modifications and may be detected by anti-cheat software.

Use at your own risk.

---

# 🗑 Uninstalling

To remove DLSSTweaks:

1. Delete all DLSSTweaks files.
2. Remove the wrapper DLL (`dxgi.dll`, `winmm.dll`, etc.).
3. If global NVIDIA settings were modified, restore defaults through:

```text
NVIDIA Control Panel
→ Manage 3D Settings
→ Restore
```

---

# 📋 Troubleshooting

| Issue                   | Solution                                        |
| ----------------------- | ----------------------------------------------- |
| DLSSTweaks not loading  | Try a different wrapper filename                |
| No log file generated   | Verify files are next to the game executable    |
| Game crashes on startup | Remove custom presets and test defaults         |
| DLAA not activating     | Confirm the game supports DLSS                  |
| Settings ignored        | Check the configuration file and wrapper method |

---

# ⚠️ Disclaimer

DLSSTweaks is provided for personal customization and experimentation.

Always back up original game files before making modifications.

The developers are not responsible for data loss, game instability, anti-cheat actions, or other issues resulting from the use of this software.

---

# ❤️ Support Development

If you find DLSSTweaks useful, consider supporting future development and testing efforts.

Your support helps maintain compatibility with new DLSS releases and upcoming games.

---

# 📜 Distribution

Please do **not** re-upload DLSSTweaks to other websites.

Linking to the official project page is appreciated so users can always download the latest version.
