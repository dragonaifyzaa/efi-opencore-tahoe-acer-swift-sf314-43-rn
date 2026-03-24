# EFI Hackintosh macOS Tahoe  
**Acer Swift 3 SF314-43RN (Ryzen Platform)**

---

## 📌 Description
This EFI is configured for running **macOS Tahoe** on the **Acer Swift 3 SF314-43RN** (AMD Ryzen).  
Most hardware components are working properly, with a few important notes below.

---

## 💻 Laptop Specifications

| Component | Details |
|----------|--------|
| Model | Acer Swift 3 SF314-43RN |
| CPU | AMD Ryzen 5 5500U / Ryzen 7 5700U (Zen 2) |
| GPU | AMD Radeon Vega iGPU |
| RAM | 8GB / 16GB DDR4 (soldered) |
| Storage | NVMe SSD |
| Display | 14” FHD (1920x1080) IPS |
| Audio Codec | Realtek (AppleALC supported) |
| WiFi | Realtek (Unsupported in macOS) |
| Bluetooth | Supported (depends on module) |
| Trackpad | I2C |
| Keyboard | Standard Laptop Keyboard |
| USB Ports | USB 3.0 / USB-C |
| Battery | Supported |

---

## ⚠️ Important Notes
- **WiFi is NOT working (unsupported)**
- **Audio does NOT work out-of-the-box (requires patching)**

---

## ✅ Hardware Compatibility

| Component | Status | Notes |
|----------|--------|------|
| CPU & GPU | ✅ Working | Stable |
| Keyboard & Trackpad | ✅ Working | Fully functional |
| USB Ports | ✅ Working | Properly mapped |
| Battery | ✅ Working | Normal with auto cut charging |
| Sleep/Wake | ✅ Working | Stable |
| Audio | ⚠️ Partial | Requires OCLP patch |
| WiFi | ❌ Not Working | Unsupported |

---

## 📶 WiFi (Not Working)

The stock WiFi card is **not supported in macOS**.

### 💡 Recommended Solution:
- Replace the WiFi card with **Intel AX210**
- Use one of the following kexts:
  - `AirportItlwm.kext` (recommended)
  - or `itlwm.kext` + HeliPort

### ⚙️ Configuration:
- Add the kext to `EFI/OC/Kexts`
- Properly configure it in `config.plist`
- Use the latest version compatible with macOS Tahoe

---

## 🔊 Audio (Requires Patch)

- Layout ID used: **69** (same as Ventura)
- On macOS Tahoe:
  - Audio **does not work on first boot**

### 🛠️ Fix:
1. Download and install OCLP Mod:
   https://github.com/laobamac/OCLP-Mod
2. Run the patch using OCLP Mod
3. Reboot

After patching, audio will function normally.

---

## 🧩 Main Kexts Used

- Lilu.kext  
- VirtualSMC.kext  
- NootedRed.kext  
- AppleALC.kext  
- NVMeFix.kext  
- USBMap.kext  
- AMD Kernel Patches (configured in config.plist)

---

## 🚀 Usage

1. Copy the `EFI` folder to your EFI partition
2. Edit SMBIOS according to your system
3. Boot using OpenCore
4. After installation:
   - Apply audio patch using OCLP Mod
   - (Optional) Upgrade WiFi to Intel AX210

---

## ❗ Disclaimer
- Use at your own risk  
- Hardware may vary between units  
- Always backup your data before use  

---

## 🙌 Credits
- OpenCore Team  
- AMD OSx Community  
- itlwm Developers  
- OCLP Mod by laobamac  

---
