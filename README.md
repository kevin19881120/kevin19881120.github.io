# 个人主页使用说明

这套文件可以直接传到 GitHub Pages，免费获得一个 `用户名.github.io` 的网址。

## 一、先改成本人的信息

用记事本或 VS Code 打开 `index.html`，把所有占位内容替换掉（用编辑器的「查找」功能搜「你的」能快速定位）：

| 位置 | 现在的内容 | 改成 |
|---|---|---|
| 第 7 行 `<title>` | 你的名字 | 你的真实姓名 |
| 第 8 行 description | 你的名字 + 介绍 | 你的姓名和一句话简介 |
| 导航 `.brand` | 你的名字 | 你的名字或昵称 |
| `.name` / 头像 `YN` | 你的名字 / YN | 你的名字 / 姓名首字母 |
| `.title` | 前端开发者... | 你的真实身份和方向 |
| `.intro` | 用一两句话介绍... | 你的自我介绍 |
| `.socials` 里的链接 | GitHub/邮箱等占位 | 你的真实主页链接，没有就删掉那条 |
| 关于 / 技能 / 作品 | 示例文字和项目 | 你自己的经历和项目 |
| `.contact` 邮箱 | your@email.com | 你的真实邮箱 |

配色、字号、动画都在 `style.css` 里，想调整可以搜索 `:root` 里的变量（比如把 `--primary` 换成你喜欢的颜色）。

## 二、本地预览

在这个文件夹里双击 `index.html`，用浏览器打开就能看效果。改完文件刷新即可。

## 三、上传到 GitHub Pages

1. 注册 GitHub：打开 github.com → Sign up，用邮箱注册并验证。
2. 新建仓库：点右上角 `+` → New repository。
   - Repository name 填 `你的用户名.github.io`（必须和你的用户名完全一致，比如 `zhangsan.github.io`）
   - 选 **Public**
   - 勾选 Add a README file
   - 点 Create repository
3. 上传文件：进入仓库 → Add file → Upload files，把本文件夹里的 `index.html`、`style.css`、`script.js` 三个文件拖进去（README.md 可不传）→ Commit changes。
4. 开启 Pages：仓库顶部 Settings → 左侧 Pages → Build and deployment 里 Source 选 `Deploy from a branch` → Branch 选 `main`、目录选 `/ (root)` → Save。
5. 等待 1–2 分钟，访问 `https://你的用户名.github.io`，就能看到你的主页了。

以后更新：再进仓库上传/修改文件并 Commit，网站会自动更新。

## 四、绑定自己的 .com 域名（可选）

1. 仓库 Settings → Pages → Custom domain，填入 `yourname.com`，点 Save。
2. 到域名注册商的 DNS 解析页添加记录：

   | 主机记录 | 类型 | 记录值 |
   |---|---|---|
   | @ | A | 185.199.108.153 |
   | @ | A | 185.199.109.153 |
   | @ | A | 185.199.110.153 |
   | @ | A | 185.199.111.153 |
   | www | CNAME | 你的用户名.github.io |

3. 等解析生效后，回到 Pages 设置勾选 **Enforce HTTPS**。

## 五、注意事项

- 首页文件名必须是 `index.html`，且放在仓库根目录，否则会 404。
- GitHub Pages 只支持静态页面，不能运行后端程序；留言功能可用第三方服务。
- 源码是公开的，不要把密码、密钥写进文件里。
- 国内访问 `.github.io` 速度可能不稳定；如果访客主要在国内，可考虑把同样的文件传到 Cloudflare Pages 或 Vercel。
