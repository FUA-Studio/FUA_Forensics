# FUA Forensics · FUA 取证工具

<p align="center">
  <img src="assets/logo.png" alt="FUA Forensics" width="120">
</p>

<p align="center">
  <sub>由 <b>FUA速传</b> 出品 · <b>FUA Studio</b> 开发</sub><br>
  <img alt="platform" src="https://img.shields.io/badge/platform-Windows-0078D6?logo=windows&logoColor=white">
  <img alt="license" src="https://img.shields.io/badge/license-GPL--3.0-blue">
  <img alt="version" src="https://img.shields.io/badge/version-1.3.3-success">
</p>

## 中文

**FUA 取证工具**是一款单文件 Windows 桌面工具：一键采集 40 项主机信息、生成健康结论与故障清单，
导出 Markdown / TXT / CSV，并可上传到 **FUA 取证网盘**，返回 `记录ID + 授权码` 用于事后取回。
无安装、无命令行参数、无后台驻留、无遥测。

### 功能

| 模块 | 说明 |
| --- | --- |
| 快速取证 | 机型/主板/BIOS、CPU、内存、显卡、磁盘与分区、激活状态、系统版本、网络配置、蓝屏与 Minidump、事件日志计数、开机时长等 40 项 |
| 故障检测 | 日志严重/错误、应用崩溃、蓝屏、C 盘空间、磁盘健康、网卡、电池、激活状态 → 健康 / 需关注 / 需处理 三档结论与建议 |
| 文件转移 | 任意文件或文件夹（自动 zip）上传，支持案件备注 |
| 实时监测 | 20 项指标（CPU/内存/网络/磁盘/GPU 等），2 秒刷新，仅本页可见时采样 |
| 取回凭据 | 记录ID + 授权码常驻显示，历史记录本机保存，重启可查 |

### 使用

1. 下载 `FUA取证工具.exe`（Windows 32 位，64 位系统可直接运行）。
2. 双击打开 → 点「开始取证 F5」→ 结果 1 秒内出现（首次启动会预热采集一次）。
3. 勾选导出格式，点「导出并上传」；上传成功后记下 **记录ID 与授权码**。
4. 取回：`GET /api/forensic/report?recordId=…&authCode=…`（转移包用 `/transfer`）。

> 建议以管理员身份运行，以读取完整事件日志与磁盘健康信息。

### 隐私

仅采集系统与硬件配置、事件日志计数，不读取个人文件或浏览记录；只有手动点击上传时才会联网。
上传记录只保存在本机 `%APPDATA%\FUA取证工具\records.json`。

### 许可

GPL-3.0，详见 [LICENSE](LICENSE)。

## English

**FUA Forensics** is a single-file Windows desktop tool for host evidence collection: it gathers
40 system facts, runs a health check with actionable findings, exports Markdown / TXT / CSV, and
uploads the report to the FUA Forensic Vault, returning a `recordId` + `authCode` pair for retrieval.
No installer, no CLI flags, no background service, no telemetry.

### Features

- **Collection** — model/mainboard/BIOS, CPU, memory, GPU, disks and partitions, activation,
  OS build, network config, blue screens and minidumps, event-log counters, uptime (40 items).
- **Health check** — log severity, app crashes, BSODs, system-drive space, disk health, NIC,
  battery, activation → verdict of *Healthy / Needs attention / Needs action*, with advice.
- **File transfer** — any file or folder (zipped automatically), optional case remark.
- **Live monitor** — 20 metrics (CPU, memory, network, disk, GPU…), 2 s refresh, sampled only
  while the page is visible.
- **Credentials** — record ID and auth code are shown inline, kept in a local history file.

### Usage

1. Download `FUA取证工具.exe` (32-bit; runs on 64-bit Windows).
2. Launch → press **F5** → results in about a second (a warm-up sample runs on first start).
3. Pick export formats, click **Export & Upload**, then keep the **record ID** and **auth code**.
4. Retrieve with `GET /api/forensic/report?recordId=…&authCode=…` (`/transfer` for bundles).

Running as administrator is recommended for complete event-log and disk-health data.

### Privacy

Only system/hardware configuration and event-log counters are read — never personal files or
browsing history. Network access happens only when you click upload. The local upload history
lives in `%APPDATA%\FUA取证工具\records.json`.

### License

GPL-3.0 — see [LICENSE](LICENSE).

---

<p align="center"><sub>© 2026 FUA Studio · FUA速传</sub></p>
