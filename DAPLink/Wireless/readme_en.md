# Wireless DAPLink Designs

[中文](./readme.md) | **English**

Three open-source wireless debugger designs based on the CMSIS-DAP protocol (all from ylj2000's oshwhub projects), in iteration order: esp32s3 → ch32v307 → **ch32v208 (recommended, newest design)**.

## Comparison

| Design | MCU | Cost | Wired speed | Wireless speed | Status |
|--------|-----|------|-------------|----------------|--------|
| [ch32v208](<./ch32v208/readme_en.md>) | CH32V208 (FS) / +CH32V305 (HS) | ~10 / 18 RMB | Far beyond J-Link V9 | Far beyond ST-LINK V2, 100m+ range | ✅ **Recommended** |
| [ch32v307](<./ch32v307/readme_en.md>) | CH32V307RCT6 + SX1281 | Under 100 RMB | ~98 KB/s | ~48 KB/s | Older |
| [esp32s3](<./esp32s3/readme_en.md>) | ESP32-S3 (WiFi) | ~30 RMB | ~95 KB/s | ~40-45 KB/s | Budget |

## Common features

- Master/slave ends identical in hardware & firmware; button pairing, plug-and-play (driver-free on Win10+)
- SWD + JTAG + virtual COM port, hardware/software reset
- All can switch to wired (USB) mode
