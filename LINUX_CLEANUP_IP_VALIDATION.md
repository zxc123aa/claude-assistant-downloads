# Linux 1.3.27：清理、最小化监测与通知实测

2026-10-23，两名独立子 Agent 使用未修改的公开 tar.gz、AppImage 实际操作界面：清理 12 项断言、监测 18 项断言通过。安装包、公钥及授权格式均未更改。

## 清理与授权

两种安装包分别实际点击默认清理：每次完成 10 项、跳过 2 项、失败 0 项。使用独立 Linux 用户、HOME、TMPDIR、私有 D-Bus 和真实 GNOME Keyring，图形显示为 WSLg。

在隔离用户中放入专用 Claude 配置、项目目录、缓存、Shell 记录和真实 SQLite 浏览器数据库。清理后目标文件及 Claude 来源行移除，无关站点数据保留；备份 manifest 和文件/数据库快照已创建。仅验证备份创建，未执行恢复；浏览器数据使用专用测试夹具，未验证真实浏览器运行与重开集成。

旧版 1.3.22 先通过真实界面激活原签名密钥签发的专用限时测试码，再由 1.3.27 清理。签名授权文件与 GNOME Safe Storage 条目保持不变，加密时间记录继续有效；退出重开无需再次激活。独立假发码数据库未变，Windows 真实客户数据库和受保护私钥文件另经摘要核对未变。未使用真实客户授权，私钥未传入 Linux。

## 最小化、跳 IP 和断网

两种安装包均在独立用户、HOME、私有 D-Bus、真实 GNOME Keyring 及私有挂载命名空间中运行。图形环境为 Xvfb + Openbox，通知服务为 dunst，X11 TCP 关闭。点击真实最小化按钮后，窗口为 Iconic、hidden、unmapped，主进程仍存活。

- 跳 IP：将专用监测历史设为 TEST-NET 地址，随后由真实 HTTPS 通用出口 `api.ipify.org` 连续两次采样确认变化。最小化期间确实出现 dunst 通知窗口，并保留实际截图。
- 断网：专用透明 CONNECT 代理仅拒绝测试客户端连接，不改宿主网络、不解密 TLS。连续三次失败弹出不可用通知，第四次不重复提醒，也不产生错误跳 IP 事件。
- 恢复：恢复真实 HTTPS 转发后监测恢复、错误清除；界面暂停后停止取样。退出重开后旧限时授权、加密时间记录与监测历史继续保留，无闪退。

上述跳 IP 是历史基线到真实出口观测的模拟，未实际切换 VPN 出口，未验证用户的 TUN 分流。通知已核实为真实可见 X11 窗口，不仅是日志或 D-Bus 调用。WSLg 的最小化状态无法严格确认，因此未将 WSLg 最小化记为通过；不代表 GNOME Shell、KDE、Wayland 或所有通知设置已验收。

## 证据与边界

此前 21 项旧授权、续期、重启和密钥环验收继续有效，见 [授权验收报告](LINUX_LICENSE_VALIDATION.md)。本轮是应用退出重开，未执行完整操作系统重启。KWallet、其他发行版、原生 GNOME/KDE 登录、完整 Wayland、长期监测、实际 VPN 切换、备份恢复、真实浏览器集成、polkit 与 FUSE 挂载仍待验收。

公开 [Linux Release](https://github.com/zxc123aa/claude-assistant-downloads/releases/tag/v1.3.27-beta.1-linux) 附件含 `linux-cleanup-ip-validation.json`、`linux-cleanup-complete.png`、`linux-minimized-ip-change.png`、`linux-minimized-outage.png` 与完整性校验。截图已脱敏，不含激活码、机器码、私钥或客户资料。两个安装包的字节与原发布版一致。
