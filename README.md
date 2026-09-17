# 美国西岸之旅 · 实时行程助手

一个移动端优先的单页旅行助手，所有数据来自 `travel-data.json`。

## 页面功能

- **此刻模块**：根据当前时间自动显示下一个行程点，一键导航
- **今日路线**：当天行程点用虚线串联，支持多目的地导航
- **每日行程**：横向日期选择，展开查看全天安排
- **种草的打卡地**：从小红书等渠道收集的打卡地卡片
- **预订与购票**：已确认的餐厅、门票
- **航班行程**：国际 + 国内航班一览
- **旅行准备清单**：分类勾选，状态自动保存
- **JSON 编辑器**：页面底部 ⚙️ 按钮可直接编辑数据

## 本地预览

```bash
# 方式一：用 Python 启动本地服务器
python3 -m http.server 8080

# 方式二：直接用浏览器打开 index.html（部分浏览器 fetch JSON 会受限，建议用服务器）
```

打开 http://localhost:8080 即可预览。

## 部署到 GitHub + Cloudflare Pages

### 1. 创建 GitHub 仓库

1. 登录 https://github.com
2. 点击右上角 **+ → New repository**
3. 仓库名填写 `us-west-trip`（或任意名称）
4. 选择 **Public**
5. 点击 **Create repository**

### 2. 上传文件

在仓库页面：

1. 点击 **Add file → Upload files**
2. 上传以下文件：
   - `index.html`
   - `travel-data.json`
   - `README.md`
3. 点击 **Commit changes**

### 3. 连接 Cloudflare Pages

1. 登录 https://dash.cloudflare.com
2. 进入 **Pages → Create a project**
3. 选择 **Connect to Git**
4. 选择刚才创建的 GitHub 仓库
5. 框架预设选择 **None**
6. 点击 **Save and Deploy**

部署完成后，Cloudflare 会给你一个 `.pages.dev` 结尾的网址，可以直接分享给朋友。

## 更新数据

### 方式一：直接改 GitHub 上的 JSON（推荐）

1. 打开 GitHub 仓库
2. 点击 `travel-data.json`
3. 点右上角铅笔图标 ✏️ 编辑
4. 修改后点 **Commit changes**
5. Cloudflare 会自动重新部署，约 1-2 分钟后刷新网页即可

### 方式二：用网页编辑器

1. 打开部署好的网页
2. 点右下角 **⚙️ 设置** 按钮
3. 编辑 JSON 内容
4. 点 **下载 JSON** 保存到本地
5. 上传到 GitHub 替换原文件

## 隐私提醒

请自行检查 `travel-data.json` 中是否包含敏感信息，如：

- 护照号
- 信用卡号
- 酒店确认号
- 真实姓名全拼
- 座位号

本模板默认不包含以上信息，但后续编辑时请留意。

## 文件说明

| 文件 | 作用 |
|------|------|
| `index.html` | 网页主体，包含 HTML/CSS/JS |
| `travel-data.json` | 所有行程数据 |
| `README.md` | 本说明文档 |
