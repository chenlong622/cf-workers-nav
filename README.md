<div align="center">
  <h1>cf-workers-nav  个人导航页</h1>
  <p>
    一个部署在CF上的轻量化导航页
    <br />
    <i>⚡ 轻松创建属于自己的导航主页</i>
  </p>
</div>

📋 轻松部署的个人导航页 

> 一个部署在CF上的轻量化导航页面。
> 集成了书签管理、图标自动获取、拖拽排序、私密链接保护等功能， Worker 单文件，方便部署。

## ✨ 主要特性

*   **⚡️ Serverless 架构**：完全运行在 Cloudflare Workers 上。
*   **💾 KV 存储**：数据存储在 Cloudflare KV 中。
*   **🎨 简洁的UI**：基于 Tailwind CSS，支持**深色模式**自动/手动切换，响应式设计适配 PC 与移动端。
*   **🖱️ 拖拽排序**：支持 PC 端鼠标拖拽和移动端长按拖拽来整理分类与卡片顺序。
*   **🔒 私密保护**：支持设置“私密链接”，仅在管理员登录后可见。
*   **📂 数据管理**：支持在线添加/编辑/删除链接，支持导入 Chrome / Edge 的 HTML 书签，支持 JSON 格式的数据导入/导出及自动备份。
*   **🔍 聚合搜索**：内置多款搜索引擎（Google, Bing, Baidu）及站内快捷搜索。

## 界面预览

### 浏览视图
| Card View | APP View |
|-|-|
| ![Desktop Preview](https://github.com/user-attachments/assets/3420ba4a-af78-4527-b502-eb2a5b3cd735)| ![APP View](https://github.com/user-attachments/assets/7ea6df52-e9da-4922-9f79-40bc40cf6f5e)|

### 编辑模式视图
| Card View | APP View |
|-|-|
| ![Edit Mode](https://github.com/user-attachments/assets/a49974cd-ed41-47c8-816e-177318b14895)| ![APP View](https://github.com/user-attachments/assets/3ef5bf17-67b5-43ea-9295-2404cb4cd5b9)|



## 部署方式

### 部署到Cloudflare

<details>
<summary>点击展开</summary>

#### 部署步骤

1. **登录 [Cloudflare](https://www.cloudflare.com)** 创建 Worker：
   - 复制仓库里 `workers.js` 的代码，粘贴进 Worker 编辑器，点击部署。

2. **创建 KV 存储**：
   - 新建一个名为 `CARD_ORDER` 的 KV 命名空间，用于存储数据。

3. **绑定 KV 命名空间**：
   - 在 Worker 的「设置 → 变量」中添加绑定，变量名称填 `CARD_ORDER`，绑定到上一步创建的 `CARD_ORDER` 命名空间。

4. **配置环境变量 / 设置**：
   - 必填与选填的各项配置见下方表格。

5. **添加域名**（可选）：
   - 若需自定义域名，在 Worker 的「设置 → 域和路由」中添加自定义域或用 `*.workers.dev` 子域。

<br/>

#### 环境变量说明

> 表中标记了「必填」与「可选」；未配置选填项时将使用默认值。

| 变量名 | 必填 | 说明 | 默认值 |
|---|---|---|---|
| `ADMIN_PASSWORD` | ✅ 必填 | 管理员登录密码，至少 **8 个字符** | 无 |
| `JWT_SECRET` | ✅ 必填 | 用于加密 Token 的密钥，建议为 **≥32 字符** 的随机字符串 | 无 |
| `DEFAULT_USER` | ⬜ 可选 | 默认用户标识，用于区分不同用户的数据 | `testUser` |
| `ALLOWED_ORIGINS` | ⬜ 可选 | 允许跨域访问的来源，多个用英文逗号分隔 | 空（不限制） |
| `ICON_API` | ⬜ 可选 | 图标API地址 |已内置xinac|
| `PREFER_ICON_API` | ⬜ 可选 | 是否优先使用图标API | `true` |

> **注意（老版本升级提醒）：**
> - 旧版本如果**未配置 `JWT_SECRET`**，或配置的 `JWT_SECRET` **小于 32 个字符**，必须重新配置一个 **≥32 字符** 的随机字符串，否则 Worker 会因配置校验失败（`JWT_SECRET 未配置或强度不足`）而无法正常工作。
> - 旧版本如果 **`ADMIN_PASSWORD` 小于 8 个字符**，请一并更新为**至少 8 个字符**的新密码，否则同样会触发配置校验失败。
> - 修改后需重新部署（或点击「保存并部署」）使配置生效。

</details>

## 🙏 致谢

特别感谢 **[Cloudflare](https://www.cloudflare.com/)** 、 **[Tailwind CSS](https://tailwindcss.com/)** 、 **[hmhm2022](https://github.com/hmhm2022)**、 **[xinac](https://api.xinac.net/)**。
