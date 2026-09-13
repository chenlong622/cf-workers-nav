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

1. 登录 [Cloudflare](https://www.cloudflare.com):
   - 创建workers，复制仓库里workers.js的代码，然后点击部署

2. 创建KV存储:
   - 新建一个名为CARD_ORDER的KV存储，用于存储数据

3. 添加环境变量:
   - ADMIN_PASSWORD，管理员登录密码
   - JWT_SECRET，用于加密 Token，输入点随机字符串即可 （如果是老版本更新的请一定要添加，否则会出错）

4. 绑定KV命名空间
   - 变量名称为CARD_ORDER，KV选择之前创建好的CARD_ORDER

5. 添加域名

</details>

## 近期更新

<details>
<summary>点击查看/隐藏更新日志</summary>

### 2026/09/13
- ✅ 支持Chrome / Edge 导出的书签HTML
- ✅ 优化页面渲染、站内搜索及事件交互，去除内嵌脚本
### 2025/12/10
- ✅ UI重构
### 2025/06/3
- ✅ 支持隐藏分类
- ✅ 数据格式调整，兼容原有数据，为了防止万一请提前备份数据
### 2025/05/09
- ✅ 调整登录UI，支持偏好保存（默认搜索及主题）
- ✅ 增加搜索本站
- ✅ 同步作者修复备份数据认证问题
### 2025/04/25
**在原项目基础上做了以下调整**
- ✅稍微调整UI，优化移动端显示
- ✅卡片增加简介和自定义icon，增加卡片编辑功能
- ✅分类支持改名和顺序调整
- ✅增加导出数据
- ✅token调整为JWT
- ✅数据去掉links，只保留categories，减少数据量
- ✅其他一些调整

</details>

## 🙏 致谢

特别感谢 **[Cloudflare](https://www.cloudflare.com/)** 、 **[Tailwind CSS](https://tailwindcss.com/)** 、 **[hmhm2022](https://github.com/hmhm2022)**、 **[xinac](https://api.xinac.net/)**。
