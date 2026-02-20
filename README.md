# 🔥 Hyper AX Manager
### Ultimate Performance Plugin for AxManager

![Version](https://img.shields.io/badge/Version-v1.0.0-red?style=flat-square)
![Platform](https://img.shields.io/badge/Platform-AxManager-black?style=flat-square)
![Android](https://img.shields.io/badge/Android-5.0%2B-red?style=flat-square)
![Chipset](https://img.shields.io/badge/Chipset-Snapdragon%20%7C%20MediaTek-orange?style=flat-square)

---

## 📌 Description

**Hyper AX Manager** is a powerful AxManager Plugin Module designed to push your Android device to its absolute performance limits — without root access required.

Boost your CPU & GPU, free up RAM, bypass thermal throttling, optimize I/O speed, and turbocharge your network connection — all in one module with a sleek **Black/Red WebUI Dashboard**.

---

## ✨ Features

### ⚡ CPU Governor Tuning
- Performance profile → `schedutil` with aggressive boost
- Max Performance → `performance` governor locked to MAX frequency
- Per-core tuning (little + big + prime clusters)
- CPU input boost & sched boost enabled

### 🟠 GPU Frequency Lock
- Auto-detects **Adreno** (Snapdragon) and **Mali** (MediaTek)
- Performance mode → max GPU frequency, dynamic governor
- Max Performance → GPU hard locked to highest frequency
- Disables GPU throttling

### 🟢 RAM & ZRAM Optimizer
- ZRAM with `lz4` compression (fastest algorithm)
- ZRAM size: 50% RAM (Performance) / 75% RAM (Max)
- VM swappiness: 10 (Performance) / 0 (Max)
- Drop caches on profile switch
- Optimized dirty ratio & vfs cache pressure

### 🌡️ Thermal Throttle Bypass
- Raises CPU/SoC thermal limits to 95°C (Performance) / 125°C (Max)
- Disables MSM thermal throttling
- Targets CPU, SoC, and skin temperature zones
- Non-destructive — restores on uninstall

### 💾 I/O Scheduler Boost
- Performance → `mq-deadline` scheduler, 1024KB read-ahead
- Max Performance → `none` (blk-mq) scheduler, 2048KB read-ahead
- Increased queue depth (512 requests)
- Optimized for fastest storage throughput

### 🌐 Network TCP Optimizer
- TCP BBR congestion control (fastest available)
- 16MB TCP socket buffers
- TCP Fast Open enabled
- Optimized keepalive & window scaling
- Reduced idle latency

### 🖥️ WebUI Dashboard (Black/Red Theme)
- Real-time CPU frequency & governor monitor
- Real-time GPU frequency monitor (Adreno & Mali)
- RAM free memory display
- Profile switcher (Performance ↔ Max Performance)
- Live profile change log
- Auto-refresh every 5 seconds

---

## 📊 Profiles

| Feature | ⚡ Performance | 🔥 Max Performance |
|---|---|---|
| CPU Governor | `schedutil` + boost | `performance` locked MAX |
| GPU Mode | Dynamic max freq | Hard locked MAX |
| ZRAM Size | 50% of RAM | 75% of RAM |
| VM Swappiness | 10 | 0 |
| I/O Scheduler | `mq-deadline` | `none` (blk-mq) |
| Read-ahead | 1024 KB | 2048 KB |
| Thermal Limit | 95°C | 125°C |
| TCP | BBR optimized | BBR optimized |

---

## 📱 Compatibility

| | Supported |
|---|---|
| Android Version | 5.0+ (API 21+) |
| Snapdragon (Adreno GPU) | ✅ |
| MediaTek (Mali GPU) | ✅ |
| Root Required | ❌ No |
| AxManager Required | ✅ Yes |

---

## 📲 Installation

1. Download `hyper_ax_manager.zip`
2. Open **AxManager** app
3. Go to **Plugin** tab
4. Tap **Install / Flash** and select the ZIP
5. Wait for installation to complete
6. **Reboot** your device
7. Open **WebUI** in AxManager for the dashboard

---

## 🔧 Usage

### Action Button
Tap the **Action** button in AxManager Plugin tab to instantly toggle between:
- ⚡ **Performance** (Boost)
- 🔥 **Max Performance** (Extreme)

### WebUI Dashboard
Open the **WebUI** from AxManager to access:
- Live CPU/GPU frequency monitor
- Profile switcher buttons
- Real-time memory stats
- Profile change history log

### CLI (via AxManager Shell)
```sh
# Apply a profile
hyper-ax apply performance
hyper-ax apply max

# Check current profile
hyper-ax profile

# View device status (JSON)
hyper-ax status

# View logs
hyper-ax log

# Switch profile via CLI
hyper-profile toggle
hyper-profile performance
hyper-profile max
```

---

## 📁 Module Structure

```
hyper_ax_manager.zip
├── module.prop          — Module identity & metadata
├── customize.sh         — Installer (auto-detects chipset)
├── service.sh           — Boot service (auto-apply profile)
├── post-fs-data.sh      — Early boot init
├── action.sh            — Action button handler (profile toggle)
├── uninstall.sh         — Clean restore to stock settings
├── system/
│   └── bin/
│       ├── hyper-ax     — Core engine (all tweaks)
│       └── hyper-profile — Profile switcher CLI
└── webroot/
    └── index.html       — WebUI Dashboard
```

---

## 📝 Logs

Logs are saved automatically at:
```
/data/user_de/0/com.android.shell/axeron/plugins/hyper_ax_manager/logs/
├── service.log        — Boot service log
├── hyper-ax.log       — Core engine log (all write operations)
├── profile-switch.log — Profile change history
├── action.log         — Action button log
└── boot.log           — Early boot log
```

---

## 🔄 Uninstall

To remove the module:
1. Open **AxManager** → Plugin tab
2. Tap **Remove** on Hyper AX Manager
3. Reboot — all settings are automatically restored to stock defaults

---

## ⚠️ Disclaimer

- This module modifies kernel parameters at runtime
- All changes are **non-permanent** and restore on reboot or uninstall
- Use Max Performance mode with caution on devices with poor cooling
- The author is not responsible for any damage caused by misuse

---

## 👨‍💻 Credits

| | |
|---|---|
| Module | HyperAX Team |
| Platform | [AxManager](https://github.com/fahrez182/AxManager) by fahrez182 |
| BusyBox | Magisk Project |
| WebUI API | KernelSU WebUI |

---

## 📜 License

```
Copyright © 2025 HyperAX Team
Licensed under Apache License 2.0
```

---

<div align="center">
  <strong>🔥 Hyper AX Manager — Push Your Device to the Limit 🔥</strong>
</div>
