# Claude 防封助手 · 客户下载

| 平台 | 下载 | 状态 |
| --- | --- | --- |
| Windows x64 | [单文件 EXE](https://github.com/zxc123aa/claude-assistant-downloads/releases/download/v1.3.28-windows/ClaudeAssistant-Windows-x64-1.3.28.exe) | 1.3.28 离线授权版 |
| Linux x64 | [AppImage](https://github.com/zxc123aa/claude-assistant-downloads/releases/download/v1.3.27-beta.1-linux/ClaudeAssistant-Linux-x86_64-1.3.27-beta.1.AppImage) · [tar.gz](https://github.com/zxc123aa/claude-assistant-downloads/releases/download/v1.3.27-beta.1-linux/ClaudeAssistant-Linux-x64-1.3.27-beta.1.tar.gz) | 1.3.27-beta.1 测试版 |
| macOS 苹果芯片 / Intel | 暂未提供 | 等待新版安装包 |

Windows 下载后直接双击运行。Linux 请选择其中一种格式：AppImage 赋予执行权限后运行，tar.gz 解压后运行 `claude-assistant`。详细要求见对应发布页附件中的使用说明。

## Windows 1.3.28 更新

- 改进部分电脑的机器码读取，原机有效旧激活码继续使用。
- 清理改为后台运行，支持取消和超时停止。
- 只检查明确目录，不进行全盘扫描或自动搜索项目目录；目标超过安全容量或文件数量上限时保留原数据并提示未完成。

[Windows 发布说明](https://github.com/zxc123aa/claude-assistant-downloads/releases/tag/v1.3.28-windows)。Mac 和 Linux 的 1.3.28 安装包尚未提供，表格中的平台版本请分别确认。

## 激活与续期

1. 打开软件，复制机器码，发给销售。
2. 领取绑定本机的激活码，粘贴后点击“激活并进入”。
3. 已激活的原机升级可继续读取有效旧授权；续期在“设置 → 更新激活码 / 续期”填写新码。

激活采用离线机器绑定，不要求连接授权服务器。换电脑、换系统或更换系统用户，请联系销售处理。保持系统时间准确；Linux 限时授权需要可正常解锁的系统密钥环。

## 使用

清理前请保存工作并关闭相关浏览器，核对界面的清理范围。IP 监测需保持软件运行，最小化后继续，完全退出后停止。允许系统通知，并检查勿扰设置；使用 TUN 规则模式时，让助手和浏览器的出站规则一致。IP 监测用于环境排查，不能保证账号不被封禁。

[Claude 使用指南](https://www.yuque.com/yushigejue-uwo3g/nx5aap/ob2rp1yd373s9unm?singleDoc#)

Linux 当前为测试版，系统要求与使用说明见 [Linux 发布页](https://github.com/zxc123aa/claude-assistant-downloads/releases/tag/v1.3.27-beta.1-linux)。

请下载对应平台的客户端附件。文件校验值见对应发布页的 `SHA256SUMS.txt`。
