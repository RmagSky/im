# im

IM Prototype Designs Via: Qdd

**原型设计 · PROTOTYPE v1.0.0** —— 单文件交互原型，无任何外部依赖。

## 静态部署

本仓库是一个纯静态站点，入口为根目录 `index.html`，可直接部署到任意静态托管：

- **GitHub Pages**：仓库已内置 Actions 工作流（`.github/workflows/deploy.yml`），在 Settings → Pages 中将 Source 设为 **GitHub Actions** 后，每次 push 到 main 即自动部署
- 部署后访问：`https://<用户名>.github.io/im/`

也可手动部署：将 `index.html` 上传至任意静态主机 / 对象存储 / Nginx 静态目录即可。

## 交互原型简介

- 4 个一级 Tab：对话 / 联系人 / 社区 / 我的，40+ 二级页面
- 完整交互：iOS 软键盘、消息长按 / 逐条与合并转发链路、好友分组管理、个人资料、深浅色主题
- 响应式：桌面端显示手机外框 + 评审侧栏，≤900px 自动全屏（手机即 APP 体验）

## 深链评审

基于 hash 路由，静态部署后深链同样可用，例如：

- 聊天页：`index.html#p=chat&id=c2`
- 群详情：`index.html#p=groupInfo&id=c1`
- 外观：`index.html#p=appearance`
- 文章详情：`index.html#p=post&id=p1`
