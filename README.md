# 未央 WeYoung 桌面版

面向 Windows 的中文 AI 桌面客户端，连接 [未央中转站](https://weyoung.space)。登录自己的账号后，可直接选择账号已有的 API 密钥和模型，在桌面窗口中聊天、阅读项目、协助编写代码和处理文件。

## 下载

**[下载 Windows x64 便携版 v1.0.1](https://github.com/shanglizcpj/weyoung-desktop/releases/download/v1.0.1/Weyoung-Desktop-1.0.1-win-x64.zip)** · [查看 Releases](https://github.com/shanglizcpj/weyoung-desktop/releases/tag/v1.0.1) · [SHA-256 校验文件](https://github.com/shanglizcpj/weyoung-desktop/releases/download/v1.0.1/Weyoung-Desktop-1.0.1-win-x64.zip.sha256)

下载包约 **429 MiB**，完整解压后约 **1.01 GiB**。本仓库用于发布可下载的软件包和使用说明。

请下载 Releases 中的 **Weyoung-Desktop-1.0.1-win-x64.zip**。GitHub 自动生成的 “Source code” 压缩包只有仓库内容，不是可运行的软件。

## 快速开始

1. 将 ZIP 完整解压到可写目录，例如 **D:\Apps\Weyoung**。
2. 打开解压后的文件夹，双击 **Weyoung.exe**，即可进入桌面界面。
3. 点击“登录并开始”，输入自己的 weyoung.space 账号和密码；开启两步验证的账号还需输入验证码。
4. 选择账号已有的 **API 密钥** 和 **模型**，点击“使用此模型”。无需手动复制 API Key 或填写接口地址。
5. 直接输入消息开始对话。需要处理本地项目时，先通过顶部文件夹按钮选择项目目录。

无需单独安装 Node.js、Git 或 Docker。软件使用账号已有的模型权限与额度，模型调用费用及可用性以中转站为准。

> 请完整解压后运行。Weyoung.exe 需要同目录的运行文件，不能只复制一个 EXE，也不要直接从压缩包内启动。

## 系统要求

| 项目 | 要求 |
| --- | --- |
| 操作系统 | Windows 10 / 11，x64 |
| 网络 | 登录和模型调用需要联网 |
| 账号 | 可正常登录 weyoung.space，并有可用密钥、模型和额度 |
| 磁盘空间 | 建议预留至少 2 GB，另需为项目和对话数据预留空间 |
| 项目环境 | Python、Java 等项目运行环境按项目自身要求准备 |

## 常用功能

- 中文桌面界面，使用未央 WeYoung 图标。
- 账号登录、两步验证、密钥和模型选择。
- 流式回复、历史对话与继续会话。
- 选择本地项目，阅读、分析及修改项目文件。
- 工具操作确认，支持“允许此次操作”或“拒绝此次操作”。
- 点击“停止”中断当前任务。

输入框中 **Enter** 发送，**Shift + Enter** 换行。首次访问项目时会询问是否允许访问该目录；请确认目录后再开始。

## 数据保存和备份

账号状态、聊天记录、核心配置和应用临时文件保存在软件旁的 **data** 文件夹。将软件解压到 D 盘后，这些应用数据也保存在 D 盘。

移动或备份前请先关闭软件，再复制整个软件目录。账号密码不保存；登录令牌保存在本机并受 Windows 目录访问权限保护，当前不是加密存储。对外分享请使用 Releases 中的干净压缩包，不要分享自己使用后的 data 文件夹。

## 常见问题

### 这是安装程序吗？

这是便携版，无需安装向导。解压完整目录后双击 Weyoung.exe 即可；也可以为该 EXE 创建桌面快捷方式。

### 为什么找不到密钥或模型？

先登录中转站网页，确认当前账号已经创建可用密钥，并具有对应模型权限。客户端展示账号已有的密钥和模型，不会自动生成额度。

### 为什么模型请求失败？

检查网络、账号余额、密钥状态和模型可用性。若项目需要 Python 等工具，还需要准备项目自身的运行环境。可尝试停止当前任务、重新选择模型或重新登录。

### Windows 提示未知发布者怎么办？

当前版本尚未进行发行者代码签名。请确认下载地址属于本仓库 Releases，并按下方方法核对文件校验值。

## 文件校验

在 ZIP 所在目录打开 PowerShell，执行：

```powershell
Get-FileHash .\Weyoung-Desktop-1.0.1-win-x64.zip -Algorithm SHA256
```

v1.0.1 的 SHA-256：

```text
f8504340e8735911d4f9d93211851d718348bc0fde2dc012953c34ee1f1b1bc1
```

## 版本与验证范围

v1.0.1 更新了 Windows 程序、窗口、侧栏和欢迎页图标。已检查便携版启动、界面图片加载和小窗口布局。

已有功能验证覆盖模拟账号登录、密钥/模型选择、流式回复、文件写入允许/拒绝、停止以及会话恢复。联网模型兼容性仍取决于具体中转站服务和所选模型；发布测试未使用真实账号额度。下载包不包含发布者的账号或聊天记录。

## 第三方组件

运行包包含 Electron 44.7.0、未修改的官方 Claude Code Windows 核心 2.1.296 和 Portable Git 2.56.0.2；相关许可与声明保留在包内的 THIRD_PARTY.md 及组件目录中。

本客户端是独立产品，并非 Anthropic 官方应用。Claude Code 的使用适用其[官方条款](https://code.claude.com/docs/en/legal-and-compliance)，包括产品集成与凭据使用条件；各组件依其自身许可提供，仓库公开不意味着所有组件均采用开源许可。

## 问题反馈

请在 [Issues](https://github.com/shanglizcpj/weyoung-desktop/issues) 中描述系统版本、软件版本、操作步骤和错误提示。截图或日志中请去掉密码、API Key、登录令牌及私人项目内容。
