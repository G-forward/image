---
title: OpenClaw本地部署详细教程
categories: 杂
tags: 
  - openclaw
  - 大模型
  - 教程
    cover: /img/openclaw封面.png
    mathjax: true
---

# 🚀 OpenClaw 本地部署超详细教程｜小白也能轻松搞定！

---

## 📌 前置准备

### 步骤 1：一键安装 OpenClaw

管理员身份打开 PowerShell，执行：

```powershell
iwr -useb https://openclaw.ai/install.ps1 | iex
```

---

### 步骤 2：自动安装 Node.js（如未安装）

![](C:/Users/Administrator/AppData/Roaming/Typora/typora-user-images/image-20260302233530498.png)

**图示说明**：
- 如果系统未安装 Node.js，安装脚本会自动调用 winget 安装
- 图中显示正在下载 Node.js v24.14.0（LTS 版本）
- 进度条显示下载进度（8.78 MB / 30.7 MB）
- 耐心等待安装完成即可

---

### 步骤 3：处理执行策略错误（如遇报错）

![](C:/Users/Administrator/AppData/Roaming/Typora/typora-user-images/image-20260302233710321.png)

**图示说明**：
- PowerShell 默认安全策略会阻止未签名脚本运行
- 红色报错信息：`UnauthorizedAccess` 表示权限不足
- 解决方法：运行以下命令放宽策略

```powershell
Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
```

执行后再重新运行安装命令即可✅

---

## 🖼️ 正式安装步骤图解

### 步骤 4：执行安装脚本

```powershell
iwr -useb https://openclaw.ai/install.ps1 | iex
```

![](C:/Users/Administrator/AppData/Roaming/Typora/typora-user-images/image-20260302231345628.png)

**图示说明**：
- 安装脚本成功执行界面
- 绿色文字表示环境检测通过（Windows 系统、Node.js v24.14.0）
- 显示 OpenClaw 安装成功，版本为 2026.3.1
- 底部提示 "Starting setup..." 进入配置向导

---

### 步骤 5：安全协议确认

![](C:/Users/Administrator/AppData/Roaming/Typora/typora-user-images/image-20260302231403976.png)

**图示说明**：
- 安全提示界面，说明 OpenClaw 默认是个人使用
- 多用户/共享使用需要额外的安全配置（如配对允许列表、权限隔离等）
- 底部红色文字询问是否理解并继续
- 选择 `Yes` 继续安装流程

---

### 步骤 6：选择 AI 模型提供商

![](C:/Users/Administrator/AppData/Roaming/Typora/typora-user-images/image-20260302231416515.png)

**图示说明**：
- 支持 20+ AI 服务商，包括 OpenAI、Anthropic、Google、通义千问 (Qwen) 等
- 根据你的需求选择对应的模型提供商
- 国内用户推荐选择 Qwen、MiniMax、Moonshot AI 等
- #### **注意：如果还没有 API Key，可以选择最后的 `Skip for now` 跳过，然后直接看第15步**

---

### 步骤 7：配置 Google 模型（示例）

![](C:/Users/Administrator/AppData/Roaming/Typora/typora-user-images/image-20260302231423973.png)

**图示说明**：
- 以 Google 为例，选择认证方式
- 可选 `Google Gemini API key`（直接填入密钥）
- 或 `Google Gemini CLI OAuth`（通过 OAuth 授权）
- 新手建议选择 API key 方式

---

### 步骤 8：选择 API Key 提供方式

![](C:/Users/ADMINI~1/AppData/Local/Temp/88d400f2-9400-460a-94e9-4a37c3745a85.png)

**图示说明**：
- 选择如何提供 API Key
- `Paste API key now`：直接粘贴密钥到配置中（推荐）
- `Use secret reference`：使用密钥引用（高级用法）

---

### 步骤 9：获取 API Key

![](C:/Users/ADMINI~1/AppData/Local/Temp/3b23dc35-c6d6-4847-ba87-acab22264d7c.png)

**图示说明**：
- 打开 Google AI Studio 或对应服务商官网
- 创建 API Key 并复制
- 回到 OpenClaw 配置界面粘贴

---

### 步骤 10：粘贴 API Key

![](C:/Users/ADMINI~1/AppData/Local/Temp/d5aafc54-96dd-4257-b46a-92886a12a89d.png)

**图示说明**：
- 在输入框中粘贴刚才复制的 API Key
- 光标闪烁处等待输入
- 粘贴后按 Enter 确认

---

### 步骤 11：选择具体模型

![](C:/Users/ADMINI~1/AppData/Local/Temp/2b1c30ea-e417-4b9f-81d8-281ece048f9d.png)

**图示说明**：
- 显示该 API Key 可使用的全部模型列表
- 支持搜索过滤（输入关键词快速定位）
- 上下键导航，Tab 选择，Enter 确认
- 图中显示 Google Gemini 系列模型（gemini-2.5-flash、gemini-3-pro-preview 等）

---

### 步骤 12：后续修改配置

![](C:/Users/Administrator/AppData/Roaming/Typora/typora-user-images/image-20260303000100208.png)

**图示说明**：
- 如需修改或增加模型，输入 `openclaw config` 命令
- 显示当前配置信息（模型、网关端口等）
- 选择 `Local (this machine)` 本地配置

---

### 步骤 13：选择配置项

![](C:/Users/Administrator/AppData/Roaming/Typora/typora-user-images/image-20260303000224838.png)

**图示说明**：
- 配置菜单选项：Workspace、Model、Web tools、Gateway 等
- 选择 `Model` 修改模型配置
- 后续操作与前面配置流程相同

---

### 步骤 14：完成配置

![](C:/Users/Administrator/AppData/Roaming/Typora/typora-user-images/image-20260303000321326.png)

**图示说明**：
- 最后一页选择 `Continue` 完成配置
- 配置会保存到本地配置文件
- 重启 OpenClaw 后生效

---

### 步骤 15：跳过模型配置（可选）

![](C:/Users/Administrator/AppData/Roaming/Typora/typora-user-images/image-20260302231423973.png)

**图示说明**：
- 没有 API Key 可选择 `Skip for now` 暂时跳过
- 后续可通过 `openclaw config` 命令修改
- 新手建议先跳过，熟悉后再配置

---

### 步骤 16：模型过滤选项

![](C:/Users/Administrator/AppData/Roaming/Typora/typora-user-images/image-20260302231430545.png)

**图示说明**：
- 可按服务商筛选模型（如 openai、anthropic、qwen 等）
- 新手建议选择 `All providers` 查看所有可用模型
- 后续可根据需要过滤

---

### 步骤 17：选择默认模型

![](C:/Users/Administrator/AppData/Roaming/Typora/typora-user-images/image-20260302231435306.png)

**图示说明**：
- 默认推荐 `anthropic/claude-opus-4-6`
- 新手直接选这个即可
- 可手动输入其他模型名称
- 列表显示各服务商的具体模型版本

---

### 步骤 18：选择通讯渠道

![](C:/Users/Administrator/AppData/Roaming/Typora/typora-user-images/image-20260302231441016.png)

**图示说明**：
- 支持 Telegram、WhatsApp、Discord、微信等 20+ 平台
- 新手建议选择 `Skip for now`
- 后续可通过 `openclaw channels add` 添加渠道

---

### 步骤 19：技能依赖安装

![](C:/Users/Administrator/AppData/Roaming/Typora/typora-user-images/image-20260302231449138.png)

**图示说明**：
- 可选安装扩展技能（GitHub、Notion、语音合成等）
- 按需勾选需要的技能
- 暂时不需要可选择 `Skip for now`

---

### 步骤 20：API 密钥配置

![](C:/Users/Administrator/AppData/Roaming/Typora/typora-user-images/image-20260302231454489.png)

**图示说明**：
- 若使用特定技能需填入对应 API 密钥
- 如 Google 地图、Notion、OpenAI 图像生成等
- 暂无需可全选 `No`，后续再配置

---

### 步骤 21：自动化钩子设置

![](C:/Users/Administrator/AppData/Roaming/Typora/typora-user-images/image-20260302231500373.png)

**图示说明**：
- Hooks 可实现自动化操作（如自动保存会话）
- 新手建议 `Skip for now`
- 熟悉后可根据需要启用

---

### 步骤 22：启动 Dashboard

![](C:/Users/Administrator/AppData/Roaming/Typora/typora-user-images/image-20260302231508709.png)

**图示说明**：
- 在 PowerShell 输入 `openclaw dashboard` 启动管理界面
- 系统会自动在浏览器中打开 Dashboard

---

### 步骤 23：OpenClaw 管理后台

![](C:/Users/Administrator/AppData/Roaming/Typora/typora-user-images/image-20260302231542521.png)

**图示说明**：
- 网页版控制台主界面
- 左侧菜单包含聊天、技能、会话、代理等模块
- 右上角显示版本号和连接状态

---

### 步骤 24：聊天界面

![](C:/Users/Administrator/AppData/Roaming/Typora/typora-user-images/image-20260302231646324.png)

**图示说明**：
- 最终聊天界面，如果之前设置了 API Key 就可直接与 AI 对话
- 底部输入框支持发送消息、粘贴图片
- 安装完成！🎉

---

## ⚠️ 常见问题

1. **权限错误**：确保用管理员身份运行 PowerShell
2. **网络问题**：安装脚本需访问 GitHub，可切换热点或使用代理
3. **端口占用**：若 8080 端口被占用，修改配置文件中的端口号
4. **Node.js 版本**：确保安装 22+ 版本，推荐使用 NVM 管理

---

## 🌟 进阶技巧

- 通过 `openclaw channels add` 添加微信/钉钉等企业渠道
- 使用 `openclaw skills` 管理自定义技能
- 配置 `MEMORY.md` 实现长期记忆功能
- 使用 `openclaw config` 随时修改配置

---

安装完成后，你就可以拥有专属的本地 AI 助手啦！有任何问题欢迎留言～ 💬

#OpenClaw #AI 部署 #本地大模型 #技术教程 #程序员日常
