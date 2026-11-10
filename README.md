# im

IM Prototype Designs Via: Qdd

**原型设计 · PROTOTYPE v1.0.1** —— 两个部分：可交互原型 + 产品基线，均为单文件、无外部依赖。

## 文件结构

| 文件 | 角色 | 说明 |
|---|---|---|
| `index.html` | 入口框架页 | 在「原型」与「产品基线」之间切换；解析旧深链并转发给原型页 |
| `proto.html` | 原型 | 界面与交互本体，CSS 与脚本内联 |
| `rule.html` | 产品基线 | 版本记录、页面清单、功能清单、交互与视觉规范、团队协作条款 |

规则文本的唯一载体是 `rule.html`。原型页只放界面与提示文案，不承载规则说明。

## 静态部署

本仓库是纯静态站点，根路径返回 `index.html`，可部署到任意静态托管：

- **Cloudflare Workers**：`https://im.arthems.workers.dev/`，推送 main 后即时生效
- **GitHub Pages**：仓库已内置 Actions 工作流（`.github/workflows/deploy.yml`）。在 Settings → Pages 中将 Source 设为 **GitHub Actions** 后，每次 push 到 main 自动部署，访问 `https://rmagsky.github.io/im/`

## 原型简介

- 4 个一级 Tab：对话 / 联系人 / 社区 / 我的，共 52 个页面
- 完整交互：iOS 软键盘、消息长按菜单（置顶 / 引用 / 转发 / 多选 / 复制 / 删除）、多选转发与删除、好友分组管理、个人资料、深浅色主题、字号调节
- 响应式：桌面端显示手机外框 + 评审侧栏，宽度 ≤900px 自动全屏

页面清单、交互口径与验收标准见 `rule.html` 第 1、2 章。

`rule.html` 与 `index.html` 的版式取自 Stripe 文档系统：白色画布、冷白侧栏、深海军蓝文字、单一 indigo 强调色、发丝线分层。原型页 `proto.html` 保留产品自身的界面语言，不套用文档版式。

## 深链评审

基于 hash 路由，静态部署后深链同样可用。经入口页中转与直达原型页两种写法都有效：

- 经入口页：`index.html#p=chat&id=c2`
- 直达原型页：`proto.html#p=chat&id=c2`
- 群详情：`#p=groupInfo&id=c1`
- 外观：`#p=appearance`
- 文章详情：`#p=post&id=p1`
- 带主题与软键盘：`#p=chat&id=c2&t=dark&kbd=1`

## 团队协作

参与原型更新的所有人按 `rule.html` 第 4 章执行：拉取上游 → 检查新提交 → 合并 → 处理冲突 → 上传，五步不跳步；提交前过 4.6 的六项检查清单；禁止事项见 4.7。
