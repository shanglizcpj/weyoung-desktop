# 未央 WeYoung 桌面版

面向 Windows 的中文 AI 桌面客户端，连接 [未央中转站](https://weyoung.space)。使用自己的账号登录，直接选择已有 API 密钥和模型，在桌面窗口中聊天、阅读项目、编写代码和处理文件。

## 下载 v1.0.5

**[下载完整离线安装包（推荐）](https://github.com/shanglizcpj/weyoung-desktop/releases/download/v1.0.5/Weyoung-Desktop-1.0.5-Setup-x64.exe)** · [安装包 SHA-256](https://github.com/shanglizcpj/weyoung-desktop/releases/download/v1.0.5/Weyoung-Desktop-1.0.5-Setup-x64.exe.sha256)

**[下载 Windows x64 便携 ZIP](https://github.com/shanglizcpj/weyoung-desktop/releases/download/v1.0.5/Weyoung-Desktop-1.0.5-win-x64.zip)** · [便携包 SHA-256](https://github.com/shanglizcpj/weyoung-desktop/releases/download/v1.0.5/Weyoung-Desktop-1.0.5-win-x64.zip.sha256) · [本次更新](https://github.com/shanglizcpj/weyoung-desktop/releases/tag/v1.0.5)

安装包约 278.5 MiB，便携 ZIP 约 429.2 MiB，安装后约 1.01 GiB。安装程序可选择位置、创建桌面和开始菜单快捷方式、提供卸载入口；安装无需联网下载组件。便携版需完整解压后双击 **Weyoung.exe**，不要只复制 EXE。无需单独安装 Node、Git 或 Docker。

本仓库发布软件包和用户说明。GitHub 自动生成的 Source code 压缩包不是可运行软件。

## v1.0.5：项目目录与启动更新提醒

- 项目文件夹右键或点击 **⋯ → 在资源管理器中打开**，直接打开对应的本地文件夹。
- 每次打开客户端自动在后台检查更新；发现新版才弹窗，可下载或选择“稍后再说”。断网或已是最新版时不打断使用；不会自动安装。
- 创建文件夹、文件读写以及常见 Bash/PowerShell 文件操作自动执行，增加多行文本写入的识别。运行 .cmd/.bat、脚本或程序仍需确认；可以主动选择逐次确认。
- 权限规则在本机处理，不增加额外的模型审批请求。继续保留附件、账号、模型及目录设置功能。

## 文件和图片附件（1.0.4 起）

- 输入框左下角点击 **＋ 附件** 多选文件，也可以拖拽文件到窗口，或在输入框 **Ctrl+V 粘贴截图**。
- 发送前显示文件名、大小和图片缩略图；点击图片可放大，点击 × 移除。支持只发附件。
- 无需手工把文件放进工作文件夹：普通文件会自动保存副本供模型读取，图片直接随消息提交给模型。
- 已发送附件随对话保留；重启后可预览图片，迁移应用数据时附件一起复制，删除对话清理副本并保留原件。
- 发送启动失败保留待发附件；切换对话、退出账号或关闭程序会清理尚未发送的附件。

每条消息最多 **8 个文件**，单个 **20 MB**，总计 **50 MB**。图片支持 **PNG、JPG/JPEG**，发送时自动缩小；图片识别需要所选模型和中转接口支持视觉输入。Office 等文档的读取能力取决于运行环境中可用的解析工具。点击发送后，图片及模型读取的文件内容会通过所选中转站提交处理；本功能不是独立的云端文件存储服务。

## 开始使用

1. 安装到当前电脑有空间且可写的位置，或完整解压便携包。盘符、用户名、中文及空格路径均可按实际电脑选择。
2. 打开未央，点击“登录并开始”。账号窗口里的 **weyoung.space ↗** 可在浏览器注册登录、设置 API Key 和查询余额。
3. 登录自己的中转站账号，选择已有密钥和模型，无需手填接口或复制密钥。开启两步验证的账号需要验证码。
4. 左侧新建文件夹或打开已有项目；在输入框输入消息或添加附件。Enter 发送，Shift+Enter 换行，“停止”中断任务。
5. 右键或“⋯”管理项目与对话；搜索框按项目名、路径及对话标题搜索。

默认“常规操作自动”会处理常见 Bash、PowerShell 目录操作和文件读写。**实际运行代码文件、项目程序、测试任务和无法判定的命令仍会询问用户**。模型提问仍需回答。首次项目访问确认保留，也可以切换为逐次确认工具。项目目录是工作目录，文件访问权限与当前 Windows 账号一致。

## 保存位置与升级

“应用设置”可分别设置生成文件的默认目录，以及聊天、附件和应用数据目录。默认跟随软件目录；不可写时使用当前用户应用数据目录，无固定盘符要求。已选项目使用自己的目录。迁移数据先复制再切换，旧目录保留，项目文件独立管理。

每次启动在后台查询最新正式版，无需登录；发现新版后会在空闲且其他弹窗关闭时提醒。账号界面的 **检查更新** 也可随时手动重试。发现新版本后，点击下载，在浏览器取得安装包。请关闭未央，再安装到原目录，保留账号、聊天、附件、项目文件及自定义路径；无需先卸载旧版。软件不会强制退出正在进行的任务或后台静默升级。

升级前请关闭软件并备份应用数据及项目。卸载只删除程序拥有的文件，保留个人数据；更换安装目录不会自动搬迁旧数据。自定义绝对路径换电脑后应重新检查。

[所有历史版本](https://github.com/shanglizcpj/weyoung-desktop/releases) · [v1.0.4](https://github.com/shanglizcpj/weyoung-desktop/releases/tag/v1.0.4) · [v1.0.3](https://github.com/shanglizcpj/weyoung-desktop/releases/tag/v1.0.3) · [v1.0.2](https://github.com/shanglizcpj/weyoung-desktop/releases/tag/v1.0.2) · [v1.0.1](https://github.com/shanglizcpj/weyoung-desktop/releases/tag/v1.0.1) · [v1.0.0](https://github.com/shanglizcpj/weyoung-desktop/releases/tag/v1.0.0)

## 兼容性与验证

支持 Windows 10/11 x64。安装和程序启动可离线完成；账号登录和模型对话需要联网，并使用自己的中转站额度。Python、Java 等项目专用环境需按任务准备。

本版本通过 65 项自动化检查，验证了文件夹路径和账号归属、后台更新去重、离线启动、弹窗延后和关闭、常规多行写入及脚本运行确认；附件、聊天、迁移和窗口布局回归通过。完整安装、从 1.0.4 升级、覆盖安装、运行中禁止替换及卸载保留数据均已测试。模型测试使用真实 Windows 运行核心和本地模拟接口，不消耗真实账号额度；具体模型的视觉及文件能力仍取决于所选服务。

保留 v1.0.3 的鼠标显示兼容处理、账号更新入口及代码运行确认。若遇到启动时的 WINWORD.EXE 报错，可使用 [Word 启动诊断工具](https://github.com/shanglizcpj/weyoung-desktop/releases/download/v1.0.3/Weyoung-Word-Startup-Diagnostics.zip) 采集报告；该问题需结合报错电脑的报告判断原因。

密码不保存，模型密钥不传给界面；登录令牌由本机目录权限保护，当前不是加密存储。对外分享请使用 Releases 中的干净包，不要分享自己使用后的 data 文件夹。删除对话后，核心日志仍可能保存处理过的内容。

软件尚未进行发行者代码签名。请从本仓库 Releases 下载并核对校验值。

## 校验下载文件

安装包 SHA-256：

```text
50c3567ad64d4dd7c3e3aaee3a87eee123a117aada06e8c61f3570e35f5e2c83
```

便携 ZIP SHA-256：

```text
ea3c7014085d6e0bd2e6f9e0b6c2187d97cfe3217da9e44869861451810b6abf
```

在文件所在目录运行 PowerShell：

```powershell
Get-FileHash .\Weyoung-Desktop-1.0.5-Setup-x64.exe -Algorithm SHA256
Get-FileHash .\Weyoung-Desktop-1.0.5-win-x64.zip -Algorithm SHA256
```

## 第三方组件

包含 Electron 44.7.0、未修改的官方 Claude Code Windows 核心 2.1.296 及 Portable Git 2.56.0.2。相关许可保留在包内 THIRD_PARTY.md 及组件目录；安装器使用 [NSIS](https://nsis.sourceforge.io/)。客户端为独立产品，并非 Anthropic 官方应用；Claude Code 使用适用其[官方条款](https://code.claude.com/docs/en/legal-and-compliance)，各组件依其自身许可提供。

## 问题反馈

请在 [Issues](https://github.com/shanglizcpj/weyoung-desktop/issues) 中描述系统和软件版本、操作步骤及错误提示。提交截图和日志前请去掉密码、API Key、登录令牌及私人项目内容。
