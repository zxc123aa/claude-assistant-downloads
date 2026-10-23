# Linux 1.3.27：旧授权、重启、续期与密钥环实测

2026-10-23，在 Ubuntu 26.04 LTS x64 / WSL2 / WSLg X11 中，用实际发行安装包完成 **21 项界面与 GNOME Keyring 检查，全部通过**。本轮只补充验收证据和说明，已发布客户端二进制没有更改。

## 测试方式

创建独立 Linux 用户、HOME、配置目录、授权目录、私有 D-Bus 会话及真实 GNOME Keyring。图形显示使用 WSLg，并非完整 GNOME 桌面或独立虚拟机。应用始终以普通用户运行。

使用原签发密钥按现有 CLA1 格式生成专用测试码，先在已发布的 1.3.22-beta.1 客户端通过界面激活，再由 1.3.27-beta.1 读取原授权和加密时间记录。没有使用真实客户授权记录，也没有改公钥、改包、注入业务代码、启用调试接口或关闭 Chromium 沙箱。签发私钥没有传入 Linux。

## 已通过

| 场景 | 实际结果 |
| --- | --- |
| 旧版永久授权升级 | 新版直接读取，退出重开仍有效 |
| 旧版限时授权升级 | 新版读取原授权，并通过真实密钥环解密旧时间记录 |
| 旧码重新输入 | 新版界面接受同一份已在旧版使用的限时码 |
| 实际续期 | 界面从两天测试授权更新为十四天授权，保存的新码与显示期限一致 |
| 续期后重启 | 退出重开仍有效，无需再次激活 |
| 密钥环与会话重启 | 新 D-Bus 会话、重启密钥环服务并解锁后，原授权仍有效 |
| 密钥环锁定 | 取消解锁时保持未激活，原授权与加密时间记录未被改写 |
| 密钥环恢复 | 在真实 GNOME 密码对话框解锁后，重开客户端自动恢复授权，无需重输码 |
| 明文后端及损坏记录 | 拒绝 basic_text 后端及损坏的加密时间记录，没有静默降级 |
| AppImage | 实际 extract-and-run 运行，旧永久/限时授权、续期与续期后重启均通过 |

通过 Secret Service 条目元数据确认应用的 Safe Storage 条目存在；未读取或公开密钥环秘密内容。tar.gz 与 AppImage 的 SHA256 与公开附件一致，且两者内部 app.asar 完全一致。

“重启”覆盖退出重开客户端及重建测试 D-Bus/密钥环服务会话，**没有执行完整操作系统重启**。本次是旧版激活后的升级兼容实测，不是读取真实历史客户的授权资料。机器绑定继续生效，Windows 的激活码不能直接转给另一台 Linux/Mac 使用。

## 仍待验收

KWallet、其他发行版、完整原生 GNOME/KDE 登录和系统重启、真实浏览器清理与恢复、最小化后的跳 IP/断网系统通知、长时间监测、polkit 权限、FUSE 挂载及完整 Wayland 桌面。本报告不将这些项目标为通过。

## 下载与证据

[Linux 安装包和完整脱敏检查记录](https://github.com/zxc123aa/claude-assistant-downloads/releases/tag/v1.3.27-beta.1-linux) 的附件包含 `linux-license-validation.json`、`linux-verification.json`、`linux-license-renewal.png` 与 `SHA256SUMS.txt`。截图已遮盖测试机器码，不含激活码、密钥环密码、私钥或客户记录。

![AppImage 实际续期后重启，测试机器码已遮盖](https://github.com/zxc123aa/claude-assistant-downloads/releases/download/v1.3.27-beta.1-linux/linux-license-renewal.png)
