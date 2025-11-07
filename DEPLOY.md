# 网站部署指南

## 目录结构

```
project/
├── index.html          # 主页
├── about.html         # 关于我们
├── terms.html         # 服务条款
├── privacy.html       # 隐私政策
├── 404.html          # 错误页面
├── styles.css        # 样式文件
├── script.js         # JavaScript文件
├── robots.txt        # 搜索引擎爬虫规则
├── sitemap.xml       # 网站地图
└── images/           # 图片目录
    ├── favicon.png
    ├── og-image.jpg
    ├── wechat-qr.jpg
    ├── project1.jpg
    ├── project2.jpg
    ├── project3.jpg
    ├── team1.jpg
    ├── team2.jpg
    └── team3.jpg
```

## 部署前检查清单

### 1. 文件准备
- [ ] 所有HTML文件编码为UTF-8
- [ ] CSS和JavaScript文件已压缩
- [ ] 所有图片已优化压缩
- [ ] favicon.ico已准备
- [ ] 404页面已配置
- [ ] robots.txt已更新
- [ ] sitemap.xml已更新

### 2. 内容检查
- [ ] 所有链接可正常访问
- [ ] 图片显示正常
- [ ] 表单提交功能正常
- [ ] 微信二维码清晰可扫
- [ ] 联系方式准确无误
- [ ] 版权信息已更新

### 3. 性能优化
- [ ] 图片已启用懒加载
- [ ] 代码已压缩混淆
- [ ] 字体图标已优化
- [ ] 浏览器缓存已配置

## 部署步骤

### 1. 本地测试
```bash
# 使用Python启动本地服务器
python -m http.server 8000

# 或使用Node.js的http-server
npx http-server
```

### 2. 服务器配置
1. 安装必要软件
```bash
# 安装Nginx
sudo apt update
sudo apt install nginx

# 安装SSL证书
sudo apt install certbot
sudo apt install python3-certbot-nginx
```

2. Nginx配置示例
```nginx
server {
    listen 80;
    server_name your-domain.com;
    return 301 https://$server_name$request_uri;
}

server {
    listen 443 ssl http2;
    server_name your-domain.com;

    ssl_certificate /etc/letsencrypt/live/your-domain.com/fullchain.pem;
    ssl_certificate_key /etc/letsencrypt/live/your-domain.com/privkey.pem;

    root /var/www/html;
    index index.html;

    # 启用gzip压缩
    gzip on;
    gzip_types text/plain text/css application/json application/javascript text/xml application/xml application/xml+rss text/javascript;

    # 错误页面配置
    error_page 404 /404.html;
    location = /404.html {
        internal;
    }

    # 静态文件缓存
    location ~* \.(jpg|jpeg|png|gif|ico|css|js)$ {
        expires 30d;
        add_header Cache-Control "public, no-transform";
    }

    # 安全headers
    add_header X-Frame-Options "SAMEORIGIN";
    add_header X-XSS-Protection "1; mode=block";
    add_header X-Content-Type-Options "nosniff";
}
```

### 3. 文件上传
```bash
# 使用rsync上传文件
rsync -avz --delete ./ user@your-server:/var/www/html/

# 或使用scp
scp -r ./* user@your-server:/var/www/html/
```

### 4. 权限设置
```bash
# 设置目录权限
sudo chown -R www-data:www-data /var/www/html
sudo chmod -R 755 /var/www/html
```

## 上线后检查

### 1. 功能测试
- [ ] 所有页面可正常访问
- [ ] 移动端显示正常
- [ ] 表单提交功能正常
- [ ] 微信二维码可以扫描
- [ ] 所有链接可点击

### 2. 性能测试
- [ ] 使用 Google PageSpeed Insights 测试
- [ ] 检查页面加载时间
- [ ] 验证移动端性能
- [ ] 检查资源加载情况

### 3. SEO检查
- [ ] robots.txt 可访问
- [ ] sitemap.xml 可访问
- [ ] 元标签完整
- [ ] Open Graph 标签正确

## 维护说明

### 1. 日常维护
- 定期更新内容
- 检查服务器状态
- 更新SSL证书
- 备份网站数据

### 2. 问题排查
- 检查nginx错误日志
- 验证文件权限
- 测试数据库连接
- 监控服务器资源

### 3. 更新流程
1. 在测试环境进行更新
2. 备份当前生产环境
3. 部署更新
4. 验证功能
5. 回滚机制准备

## 联系方式

如遇到部署问题，请联系：
- 技术支持：your.email@example.com
- 微信：您的微信号
- QQ：您的QQ号 