# TinyPad

**A tiny, lightweight text editor for Windows.**

TinyPad is a native Windows text editor developed by **Tiny's**, built with a simple philosophy:

> Software shouldn't consume more resources than the job requires.

Designed to be lightweight, responsive, and minimal, TinyPad aims to deliver a straightforward text-editing experience without unnecessary overhead.

---

## ✨ Features

- Native Windows application: no browser engine, no runtime, no installer.
- Minimal, distraction-free interface.
- **AMOLED black** dark theme (true `#000000`), with light and "follow Windows" modes.
- Tab-based document editing. Middle-click a tab to close it.
- Find, Replace, Replace All and Go To Line.
- Undo and redo, with a memory cap so history can't grow without limit.
- Word wrap and zoom.
- Status bar with line and column, character count, line endings and encoding.
- Opens files by double-click, drag-and-drop or the recent files list.
- Handles UTF-8, UTF-8 with BOM, UTF-16 LE and UTF-16 BE, and keeps your original line endings (CRLF or LF) when saving.
- Lightweight, single-file executable.
- Custom document format: `.tny`.
- Designed with resource efficiency in mind.

## 📸 Screenshots


<img width="1920" height="1080" alt="Screenshot 2026-11-22 091227" src="https://github.com/user-attachments/assets/5c3ba273-304a-4631-9072-529a06fe9396" />
<img width="1920" height="1080" alt="Screenshot 2026-11-22 091651" src="https://github.com/user-attachments/assets/5617ee13-ec2a-40d3-af51-ade868410bac" />




## ⚡ Performance

Current development benchmarks:

| Metric | Result |
|---|---:|
| Executable size | 235 KB |
| RAM usage (empty document) | ~5 MB |
| RAM usage (large test document) | ~8 MB |

*Measurements are from the development environment and may vary depending on Windows, hardware, and measurement method.*

### How it stays small

- Text lives in a piece table, so editing a large file doesn't copy it.
- Files are loaded through memory mapping.
- Only the lines visible on screen are laid out and drawn.
- Nothing runs in the background. The window repaints only when something changes, so an idle TinyPad uses no CPU.
- The C++ runtime is linked in statically, so there is nothing to install next to the exe.

## 🛠️ Built With

- C++17
- Win32 API
- Direct2D / DirectWrite
- Microsoft Visual C++
- CMake

## 💻 Installation

1. Download the latest TinyPad release.
2. Extract the executable.
3. Run `TinyPad.exe`.
4. Start editing.

No complicated setup required.

**Optional:** to open `.tny` files with a double-click, move `TinyPad.exe` to a permanent folder (for example `C:\Apps\TinyPad`), then choose **File > Set as Default for .tny Files**. This only changes your own user settings and needs no administrator rights. If you move the exe later, run that menu item again.

> **Windows SmartScreen:** TinyPad isn't code-signed yet, so Windows may show "Windows protected your PC" the first time. Click **More info**, then **Run anyway**.

## ⌨️ Shortcuts

| Action | Shortcut |
|---|---|
| New tab | `Ctrl+T` |
| Open / Save / Save As | `Ctrl+O` / `Ctrl+S` / `Ctrl+Shift+S` |
| Close tab | `Ctrl+W` |
| Next / previous tab | `Ctrl+Tab` / `Ctrl+Shift+Tab` |
| Undo / Redo | `Ctrl+Z` / `Ctrl+Y` |
| Find / Find next / Find previous | `Ctrl+F` / `F3` / `Shift+F3` |
| Replace | `Ctrl+H` |
| Go to line | `Ctrl+G` |
| Zoom in / out / reset | `Ctrl++` / `Ctrl+-` / `Ctrl+0` (or `Ctrl` + mouse wheel) |

## 🔨 Building from Source

You need Visual Studio with the C++ desktop workload and CMake.

1. Open a **Developer Command Prompt for Visual Studio**.
2. Go to the project folder and run:

```
cmake -S . -B build
cmake --build build --config Release --target TinyPad
```

3. The executable is at `build\Release\TinyPad.exe`.

The unit tests (`test_buffer`, `test_undo`, `test_file_io`) use `assert`, so build and run them in Debug:

```
cmake --build build --config Debug
build\Debug\test_buffer.exe
build\Debug\test_undo.exe
build\Debug\test_file_io.exe
```

Want a different file extension? Change the single line in `doc_ext.h` and rebuild.

## 🚧 Development Status

**TinyPad is currently in Alpha.**

Features, performance, and stability are actively being improved. Bugs and unexpected behavior are possible.

Feedback and bug reports are welcome.

## 🎯 Project Philosophy

TinyPad is built around three principles:

- **Lightweight:** Minimize memory and CPU consumption.
- **Simplicity:** Keep the interface clean and functional.
- **Efficiency:** Avoid unnecessary background activity and resource usage.

## 👥 Developed By

**Tiny's**

Small footprint. Big ambitions.

---

*TinyPad — Project #001 by Tiny's.*
