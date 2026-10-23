# Claude 防封助手 · 下载

此仓库用于分发客户端安装包和使用说明。产品源码在独立的私人仓库维护，此处不包含发码后台、签发私钥、客户数据库或客户激活码。

## 下载与版本状态

请在 [Releases 下载页](https://github.com/zxc123aa/claude-assistant-downloads/releases) 下载附件中的客户端文件。GitHub 自动生成的 “Source code” 压缩包只包含本下载仓库的公开说明，不是产品源码，也不是安装包。

| 平台 | 版本与状态 |
| --- | --- |
| Windows x64 | [1.3.27 单文件便携版](https://github.com/zxc123aa/claude-assistant-downloads/releases/tag/v1.3.27-windows) |
| Linux x64 | [1.3.27-beta.1 测试版](https://github.com/zxc123aa/claude-assistant-downloads/releases/tag/v1.3.27-beta.1-linux)，AppImage / tar.gz |
| macOS 苹果芯片 | 等待合作者交付新版安装包 |
| macOS Intel | 等待合作者交付新版安装包 |

各平台的实测范围、系统要求及待验证项目以对应 Release 说明为准。没有附件的平台表示暂未提供下载。

Linux 1.3.27 已补充旧版授权升级、续期、应用及密钥环会话重启、锁定与解锁恢复的实际验收：21 项通过，覆盖 tar.gz 与 AppImage extract-and-run。详见 [Linux 授权与密钥环实测](LINUX_LICENSE_VALIDATION.md)；KWallet、完整系统重启及其他待验收项目仍单独标注。

## 使用

Windows 下载 EXE 后直接运行。Linux 下载 AppImage 或 tar.gz；AppImage 需要执行权限，tar.gz 解压后运行 `claude-assistant`，无需安装 Node.js。

启动后复制机器码，联系销售领取绑定本机的激活码。有效旧码在原电脑、原系统用户下继续使用；机器绑定仍生效，换电脑或换系统需要重新处理授权。

IP 监测需要保持程序运行，最小化后继续工作，完全退出后停止。请允许系统通知，并检查勿扰设置；TUN 规则模式下，本助手与浏览器的出站规则应一致。IP 监测不能证明封号原因，也不能保证账号不被封禁。

使用指南：[Claude 指南](https://www.yuque.com/yushigejue-uwo3g/nx5aap/ob2rp1yd373s9unm?singleDoc#)。

下载后可用 Release 附件中的 `SHA256SUMS.txt` 核对文件完整性。
