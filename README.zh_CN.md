<p align="right"><strong>简体中文</strong> · <a href="README.md">English</a></p>

# FoloToy 语音备忘 — Mac 刷写包

下载 `FoloToy-Voice-Memo-Mac.zip`，解压后启动
`Flash-Voice-Memo.command`。刷写期间保持设备连接。
脚本使用已建立的 `~/folotoy-flash-env` Python 环境，要求 esptool 4.12.0。
先校验固件 SHA-256，再检查 `/dev/cu.usbmodem14301` 对应的设备是
ESP32-C3、8 MB Flash，最后执行刷写。包中不包含唯一设备 MAC 地址。
开始前断开其他 USB 串口设备；端口变更时脚本会停止。
如果 macOS 阻止启动，请反馈提示，不要关闭系统保护。

这是已获授权的不保留旧数据的完整刷新流程：替换固件，可能重置旧 NVS 设置，
不执行整片擦除。需要保留旧数据的升级不要使用此包。

离线应用含八个录音槽，每条最长四秒。上/下选择，短按 OK 回放，长按 OK
在空槽录音，录音时按 OK 停止保存。长按下请求删除，短按 OK 确认，
其他操作取消。启动界面为 VOICE / POCKET。

Build：PASS（ESP-IDF 5.5.3）。Host tests：PASS，含保存中断、真实录放函数
边界测试和 ASan/UBSan。Device tests：NOT RUN。
刷写、屏幕显示、麦克风与扬声器音质、真实断电恢复仍需实机检查。

固件 SHA-256：
`f435734c800b0b51bef047f3fc15f2c6fe8813d75e617e8ef72a1e7f6ed56388`。
ZIP 校验值见 `SHA256SUMS`，许可文本位于压缩包中。
