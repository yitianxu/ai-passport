<p align="right"><a href="README.zh_CN.md">简体中文</a> · <strong>English</strong></p>

# FoloToy Voice Memo — Mac flash package

Download `FoloToy-Voice-Memo-Mac.zip`, extract it, and launch
`Flash-Voice-Memo.command`. Keep the device connected throughout flashing.
The launcher uses the existing `~/folotoy-flash-env` Python environment and
requires esptool 4.12.0. It checks the firmware SHA-256, then checks for an
ESP32-C3 with 8 MB Flash at `/dev/cu.usbmodem14301` before writing.
No unique device MAC address is embedded in this package. Disconnect other
USB serial devices before starting; if the port changes the launcher stops.
If macOS blocks launching the script, report that message; do not disable
system protections.

This is the complete refresh workflow authorized for this device: it replaces
firmware and can reset old NVS settings. It does not perform whole-chip erase.
Do not use this package for an upgrade that must preserve existing data.

The offline application provides eight recording slots, up to four seconds
each. UP/DOWN selects; click OK plays; hold OK records into an empty slot;
click OK stops and saves. Hold DOWN requests deletion; click OK confirms and
other input cancels. The UI starts at VOICE / POCKET.

Build: PASS (ESP-IDF 5.5.3). Host tests: PASS, including interrupted-save and
actual record/playback boundary tests plus ASan/UBSan. Device tests: NOT RUN.
Flashing, screen rendering, microphone/speaker quality and physical power-loss
recovery still require on-device checks.

Firmware SHA-256:
`f435734c800b0b51bef047f3fc15f2c6fe8813d75e617e8ef72a1e7f6ed56388`.
See `SHA256SUMS` for the ZIP checksum. License texts are inside the package.
