# Tamiya 田宫迷你四驱车产品目录网站

一个单页静态产品目录网站，收录田宫（Tamiya）1/32 迷你四驱车产品。支持产品检索、底盘筛选、规格对比与底盘百科查询。

数据抓取自田宫模型中国官网，整理日期：2026-09-03。

## 功能特性

- **产品目录**：296 款产品收录（含在售、限定版与停产型号），覆盖 VZ / MA / MS / AR / FM-A / Super-II / VS 等 17 种底盘
- **产品图片**：293 款产品引用官网真实图片，缺失自动回退为编号占位
- **多维检索**：关键词搜索（型号 / 车名 / 编号）+ 底盘类型、销售状态筛选 + 价格/编号排序
- **规格对比**：最多 4 款产品并排对比，含底盘、马达位置、齿轮比、尺寸、轮胎等 14 项参数
- **底盘百科**：17 种底盘的技术规格与特点卡片，可一键跳转查看同底盘全部产品
- **产品详情**：点击卡片查看完整规格，并可直达官网商品页

## 目录结构

```
├── index.html          # 单页应用（HTML + CSS + JS，无外部依赖）
├── README.md           # 项目说明
└── .gitignore          # Git 忽略规则
```

> 说明：产品图片为田宫官网远程链接（`tamiya.cn/wp-content/uploads/...`），页面加载时需联网获取。

## 本地预览

直接双击 `index.html` 用浏览器打开，或启动本地静态服务：

```bash
# Python
python -m http.server 8000

# Node
npx serve .
```

然后访问 `http://localhost:8000/`。

## 部署

本项目为纯静态站点，可部署到任意静态托管（GitHub Pages、Vercel、Netlify、Nginx 等），无需构建步骤。

### 使用 Git 推送远程服务器

```bash
# 1.（首次使用需配置身份）
git config --global user.name "你的名字"
git config --global user.email "你的邮箱"

# 2. 关联远程仓库（GitHub / Gitee / 自建 Git 服务器）
git remote add origin <你的远程仓库地址>

# 3. 推送
git branch -M main
git push -u origin main
```

### Nginx 示例

```nginx
server {
    listen 80;
    server_name your-domain.com;
    root /var/www/mini4wd;      # 上传 index.html 至此目录
    index index.html;
}
```

## 数据说明

- 数据来源：[田宫模型中国](https://tamiya.cn/mini4wd-cn/) 1/32 迷你四驱车分类，共 371 个列表条目
- 本目录收录其中的 296 款整车/套装产品，未收录页面 5–7 部分停产型号与配件类条目
- 价格为官网标注（美元 + 约合人民币），停产型号不显示价格
- 产品图片 URL 通过官网 Yoast sitemap（`product-sitemap*.xml`）精确配对，归属官网

## 免责声明

本项目为个人学习与兴趣用途的产品信息整理，数据与图片版权归田宫模型（Tamiya）及田宫模型中国所有。请勿用于商业用途。
