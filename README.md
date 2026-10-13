# 未央 WeYoung 桌面版

## 当前下载：v1.0.9 MiniMax 请求兼容修复

修复客户端重复发送 JSON 请求头，导致 MiniMax 返回 HTTP 400 / 缺少 model 参数的问题。MiniMax-M3 的 Responses 接口已通过真实 Windows 核心连续两轮中文对话验证，保留此前的模型目录修复。

**v1.0.8 用户可在账号页点击“检查更新”。** 关闭未央后沿用原安装目录安装新版，账号、聊天和项目文件保留。账号页版本应显示 1.0.9。此次不处理 OpenCode 渠道问题。

连接 [未央中转站](https://weyoung.space) 的 Windows 中文 AI 客户端。用自己的账号登录，选择已有 API 密钥和模型，在桌面窗口聊天、阅读项目、编写代码和处理文件。

## API 接口支持

桌面版支持以下接口类型，账号页可选择：

| 接口类型 | 中转站端点 |
| --- | --- |
| Anthropic Messages | `/v1/messages` |
| OpenAI Responses | `/v1/responses` |
| OpenAI Chat Completions | `/v1/chat/completions` |
| Gemini 原生接口 | `/v1beta/models/{model}:streamGenerateContent` |

在 [未央中转站](https://weyoung.space) 创建 API Key 后，回到客户端账号页点击 **刷新列表** 即可获取。客户端展示账号下各分组密钥，停用、过期或额度用尽的密钥会显示原因。常见分组自动推荐接口；未知分组保留在列表中，可手动选择接口类型。无需复制 API Key 或填写 URL。

接口协议与模型厂商不是一回事：同一厂商可能由中转站开放不同协议，请按密钥所属分组的实际能力选择。出现 404/405 或不支持的模型时，可检查接口类型；客户端不会自动轮流发起模型请求。某个接口出现在选择框中，不代表该分组一定已开放它。Antigravity 分组的 Messages/Gemini 使用站点对应前缀。

原有对话继续使用原来的接口；切换模型、密钥或接口后开始新对话。三种新增协议经本机转换后仍由原生核心执行工具和权限判断。支持文本、流式输出、图片与函数工具调用；视觉、工具调用、上下文容量和 Auto 是否可用取决于所选模型与中转接口。

**OpenAI Responses 当前可使用自动接受编辑和手动确认；原生 Auto 分类器需要 stop_sequences，而 Responses 无此参数，所以该组合暂不支持，遇到时保留拒绝结果。**

目前单次转换请求最多申请 8,192 个输出 token；不自动探测模型上下文上限。暂不支持这些协议的全部专用功能，如音视频、Realtime/WebSocket、服务端内置工具及专用结构化输出。Gemini 思考签名与 Responses 加密推理上下文缓存在本机会话内以便续聊；无法转换的能力会明确报错。测试使用本地模拟接口和真实 Windows 核心，尚未逐一用站点真实额度验证所有分组。


报错和英文提醒在同一条消息中附中文说明，详见 [接口报错与提醒中文说明](接口报错说明.md)。

## 下载 v1.0.9

**[下载完整离线安装包（推荐）](https://github.com/shanglizcpj/weyoung-desktop/releases/download/v1.0.9/Weyoung-Desktop-1.0.9-Setup-x64.exe)** · [安装包校验值](https://github.com/shanglizcpj/weyoung-desktop/releases/download/v1.0.9/Weyoung-Desktop-1.0.9-Setup-x64.exe.sha256)

[下载 Windows x64 便携 ZIP](https://github.com/shanglizcpj/weyoung-desktop/releases/download/v1.0.9/Weyoung-Desktop-1.0.9-win-x64.zip) · [便携包校验值](https://github.com/shanglizcpj/weyoung-desktop/releases/download/v1.0.9/Weyoung-Desktop-1.0.9-win-x64.zip.sha256) · [更新记录](https://github.com/shanglizcpj/weyoung-desktop/releases/tag/v1.0.9)

安装包约 278.5 MiB，便携 ZIP 约 429.2 MiB，安装后约 1.01 GiB。安装程序可选择位置、创建桌面和开始菜单快捷方式，提供卸载入口。安装无需联网下载组件；无需单独安装 Node、Git 或 Docker。便携版完整解压后双击 **Weyoung.exe**，不要只复制 EXE。

本仓库提供软件包和用户说明；GitHub 自动生成的 Source code 压缩包不是可运行软件。

## 原生权限模式

v1.0.7 移除了未央自定义的命令审核规则，直接使用随包 Claude Code 核心的权限机制。输入框旁或“应用设置”中可选择：

| 模式 | 行为 |
| --- | --- |
| 自动接受编辑（默认） | 自动允许核心支持的项目文件修改和常见目录操作；其他操作遵循原生规则。 |
| Auto 自动审查 | 模型判断工具操作是否允许，也可能自动允许运行脚本和程序。需要中转站与模型兼容，可能增加请求及费用。 |
| 手动确认 | 核心判定需要许可时询问；原生只读操作仍可自动执行。 |

核心要求确认时，可允许本次或拒绝本次；核心提供权限建议时，可按显示范围记住权限或仅在当前会话接受编辑。模型问题仍需用户回答。原生允许和拒绝规则继续生效；Auto 审查失败或拒绝时保留核心结果，桌面端不自动放行。若中转站不支持 Auto，可切换为其他模式。

旧版“常规操作自动”会迁移为“自动接受编辑”；原逐次确认迁移为“手动确认”。不会自动替旧用户开启 Auto。用户选择会保存，重启后保留；当前会话模式与默认设置不同时会标明。权限确认不是操作系统文件沙箱，文件访问权限与当前 Windows 账号一致。

## 开始使用

1. 安装到电脑有空间且可写的位置，或完整解压便携包。支持不同盘符、用户名、中文及空格路径。
2. 点击“登录并开始”。账号界面的 **weyoung.space ↗** 可在浏览器注册、设置 API Key 和查询余额。
3. 登录自己的中转站账号，选择已有密钥和模型，无需手填接口或复制密钥。开启两步验证的账号需输入验证码。
4. 新建文件夹或打开电脑上的已有项目；首次访问会确认项目目录。输入消息或添加附件，Enter 发送，Shift+Enter 换行，“停止”中断任务。
5. 右键或“⋯”管理项目与对话；项目可在资源管理器中打开、重命名显示名称或移除，对话可重命名或删除。搜索框支持项目名、路径及对话标题。

## 文件和图片

点击 **＋ 附件** 多选文件，拖拽文件到窗口，或在输入框 **Ctrl+V 粘贴截图**。可在发送前预览、移除，也可只发附件。无需手工放入工作文件夹：普通文件保存副本供模型读取，图片直接随消息提交模型。

每条消息最多 **8 个文件**，单个 **20 MB**，合计 **50 MB**。图片支持 PNG、JPG/JPEG，发送时自动缩小，原件不变；图片识别需要所选模型和中转接口支持视觉输入。Office 等格式的读取取决于可用解析工具。发送后，图片及模型读取的文件内容会通过所选中转站处理。

附件随对话在本机保存，数据迁移时一起复制；删除对话会清理附件副本并保留原文件。发送启动失败保留待发附件，切换对话或退出会清理未发送附件。核心日志仍可能保留处理过的内容。

## 保存位置与升级

“应用设置”分别设置生成文件的默认目录，以及聊天、附件和应用数据目录。默认跟随软件目录；不可写时使用当前用户应用数据目录，无固定盘符要求。已选项目使用自己的工作目录。迁移数据先复制再切换，旧目录保留，项目文件独立管理。

每次启动在后台检查最新版，无需登录；发现新版时在空闲且其他弹窗关闭后提醒。账号界面也可手动 **检查更新**。点击下载后通过浏览器取得安装包，关闭未央并安装到原目录即可升级，无需先卸载。不会强制结束正在进行的任务，也不会后台自动安装。

升级前关闭软件并备份数据及项目。卸载只删除程序拥有的文件，保留个人数据。更换安装目录不会自动迁移旧数据；换电脑后需检查自定义绝对路径。

[所有历史版本](https://github.com/shanglizcpj/weyoung-desktop/releases) · [v1.0.7](https://github.com/shanglizcpj/weyoung-desktop/releases/tag/v1.0.7) · [v1.0.6](https://github.com/shanglizcpj/weyoung-desktop/releases/tag/v1.0.6) · [v1.0.5](https://github.com/shanglizcpj/weyoung-desktop/releases/tag/v1.0.5) · [v1.0.4](https://github.com/shanglizcpj/weyoung-desktop/releases/tag/v1.0.4) · [v1.0.3](https://github.com/shanglizcpj/weyoung-desktop/releases/tag/v1.0.3)

## 兼容性与验证

支持 Windows 10/11 x64。安装和启动可离线完成；账号登录和模型对话需要联网，并使用自己的中转站额度。Python、Java 等项目专用环境仍需自行准备。

本次通过 56 项协议、真实 Windows 核心、权限、停止/续聊、错误说明和更新检查回归；新增真实 HTTP 测试覆盖 Chat、Responses、Gemini 的请求头。另用真实账号完成 MiniMax-M3 两轮中文文本对话，其余分组和模型能力未逐一实测。Auto 下文本成功不代表 Responses 的原生工具审查分类器已兼容，见上方限制说明。

保留鼠标显示兼容修复。启动时若遇 WINWORD.EXE 报错，可使用 [Word 启动诊断工具](https://github.com/shanglizcpj/weyoung-desktop/releases/download/v1.0.3/Weyoung-Word-Startup-Diagnostics.zip) 采集报告。

密码不保存，模型密钥不传给界面；登录令牌由本机目录权限保护，目前不是加密存储。分享软件请使用 Releases 干净包，不要分享自己的 data 文件夹。软件尚未进行发行者代码签名。

## SHA-256 校验

安装包：

```text
f110b493045e450a916c5050bcee6b127471e1261e5babe27f0ebe918b98f886
```

便携 ZIP：

```text
bd3a447c25d5439650c0844b48da4761efe01a9129a4a4b7cfb36b16f8713492
```

在文件所在目录用 PowerShell 运行 Get-FileHash，算法选择 SHA256，与上述值比较。

## 第三方组件与反馈

包含 Electron 44.7.0、未修改的官方 Claude Code Windows 核心 2.1.296、Portable Git 2.56.0.2，安装器使用 [NSIS](https://nsis.sourceforge.io/)。许可保留在包内 THIRD_PARTY.md 和组件目录。未央是独立客户端，并非 Anthropic 官方应用；核心使用适用其[官方条款](https://code.claude.com/docs/en/legal-and-compliance)。权限行为随所捆绑核心版本变化，不保证覆盖终端的每项交互或云端服务。

反馈请到 [Issues](https://github.com/shanglizcpj/weyoung-desktop/issues)，注明系统、软件版本、步骤与错误提示。截图和日志请移除密码、密钥、令牌和私人项目内容。
