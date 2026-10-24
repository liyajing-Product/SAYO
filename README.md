# SAYO·职言

**职场万象，言有回响。** 一个帮助用户在重要职场沟通前理清情况、准备表达并练习对话的前端产品。

[在线体验](https://sayo-eight.vercel.app/) · [Vercel 项目](https://vercel.com/keke17/sayo)

## 当前版本

- 两种沟通场景：任务冲突、要求不明确。
- 六步流程：说说情况 → 确认要点 → 准备表达 → 沟通对练 → 回看反馈 → 带走提纲。
- 页面过渡、场景切换保留滚动位置、聊天正在输入动画。
- 参考表达、对话回看、反馈与提纲复制、下载及本地保存。
- 自包含 HTML/CSS/JavaScript/SVG 与内嵌头像，无 npm 依赖、无需构建。

**当前对话由前端预设规则生成，真实 AI 和后台接口尚未接入。** 本地记录存储于浏览器 localStorage。

## 项目文件

| 文件 | 用途 |
| --- | --- |
| `index.html` | 完整可编辑前端源码和静态入口，与已发布 Vercel 版本一致 |
| `vercel.json` | 无构建静态部署配置 |
| `DESIGN.md` | 设计规范与改版说明 |
| `BACKEND-INTEGRATION.md` | AI 回复接口、请求结构和替换位置 |
| `DEPLOYMENT.md` | 当前 Vercel 地址及部署记录 |
| `THIRD-PARTY-NOTICES.md` | 第三方标识与素材说明 |
| `LICENSE` | 原创代码的 MIT 许可证 |
| `gitignore.txt` | 本地 Git 忽略模板，使用前改名为 `.gitignore` |

为便于 GitHub 下载和静态托管，原交付包的 `dist/index.html` 放在本仓库根目录，网页内容保持一致。

## 本地预览

下载仓库后双击 `index.html`，或在仓库目录运行：

```bash
python3 -m http.server 5189
```

然后打开 http://localhost:5189/ 。

## Vercel 部署

在 Vercel 导入本仓库，Framework Preset 选择 **Other**，根目录为仓库根目录，无安装及构建命令，输出目录为 `.`。仓库中的 `vercel.json` 已提供对应设置。

当前线上项目最初通过静态文件上传发布。GitHub 仓库创建本身不会自动把它连接到现有 Vercel 项目；需要在 Vercel 项目的 Git 设置中连接本仓库，才能让后续 push 触发自动部署。

## 后台接入

组员可以先阅读 [后台接入说明](BACKEND-INTEGRATION.md)，将规则回复替换为服务端 AI 请求，并保留现有等待状态和错误恢复交互。API Key 放在服务器环境变量中。

## 许可

原创代码使用 MIT 许可证。豆包等第三方名称、头像及标识权利见 [第三方素材说明](THIRD-PARTY-NOTICES.md)。
