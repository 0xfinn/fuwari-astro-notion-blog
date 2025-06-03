🍥Fuwari Astro Notion Blog 
------------------------

A static blog template built with [Astro](https://astro.build).

[**🖥️ 在线预览 (Vercel)**](https://fuwari.vercel.app)&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;

> README version: `2025-06-01`

![Preview Image](https://raw.githubusercontent.com/saicaca/resource/main/fuwari/home.png)

### 项目介绍

Fuwari Astro Notion Blog 是一个基于 Astro 框架和 Notion API 的开源博客项目。原项目[**fuwari**](https://github.com/saicaca/fuwari)以markdown文件作为博客的页面展示源，由于本人习惯了用notion作为笔记软件，所以在原作者项目基础上加了notion，它允许用户通过 Notion 数据库来管理博客内容，并使用 Astro 框架来渲染和部署博客。这个项目非常适合希望使用 Notion 作为内容管理系统，同时享受 Astro 框架高性能和现代开发体验的用户。

### 必须

- Node.js <= 22
- pnpm <= 9

### 项目快速启动

#### 🚀 方法一

#### 克隆项目

首先，克隆项目到本地：

```
git clone https://github.com/0xfinn/fuwari-astro-notion-blog.git
cd fuwari-astro-notion-blog
```

#### 安装依赖

使用 pnpm 安装项目依赖：

```
pnpm install
```

#### 配置 Notion API

在 Notion 中创建一个集成并获取 API 密钥。然后在项目根目录下创建一个 `.env` 文件，并添加以下内容：

```
NOTION_API_KEY=your_notion_api_key
NOTION_DATABASE_IDS=your_notion_database_id
```

#### 启动开发服务器

运行开发服务器：

```
pnpm dev
```

现在，你可以通过浏览器访问 `http://localhost:4321` 来查看你的博客。

由于开发环境没有自动拉取notion内容，你需要手动拉取

```
node scripts/fetch-notion.js
```

或者

```
pnpm build
pnpm preview
```

#### GitHub workflow配置

根目录.github中需要改branches 和 VERCEL_DEPLOY_HOOK 两个参数，请自行搜索替换

#### 部署到Vercel

Todo



## ⚙️ 文章 Frontmatter

Notion文章需要有下面这些属性：

```
Name: My First Blog Post 								#该字段默认就有不用特殊设置
Published: 2023-09-09    								#发布时间 需要设置该字段
Description: This is my new Astro blog. #描述 需要设置该字段
Tags: [Foo, Bar]												#标签 需要设置该字段
Category: Front-end											#分类 需要设置该字段
Public: true														#是否公开显示 需要设置该字段
```

推荐复制该notion模板 [Notion_Template](https://notion.so/7875426197cf461698809def95960ebf) 


## 🧞 指令

下列指令均需要在项目根目录执行：

| Command                            | Action                                 |
| :--------------------------------- | :------------------------------------- |
| `pnpm install` 并 `pnpm add sharp` | 安装依赖                               |
| `pnpm dev`                         | 在 `localhost:4321` 启动本地开发服务器 |
| `pnpm build`                       | 构建网站至 `./dist/`                   |
| `pnpm preview`                     | 本地预览已构建的网站                   |
| `pnpm new-post <filename>`         | 创建新文章                             |
| `pnpm astro ...`                   | 执行 `astro add`, `astro check` 等指令 |
| `pnpm astro --help`                | 显示 Astro CLI 帮助                    |
