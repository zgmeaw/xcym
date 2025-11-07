# 网站图片资源说明

## 必需的图片文件

请在 images 文件夹中准备以下图片：

### 基础图片
- logo.png - 网站图标和Logo
- og-image.jpg (1200x630px) - 社交媒体分享图片
- wx.jpg (300x300px) - 微信二维码

### 项目展示图片
- project1.jpg (800x600px) - ASP.NET医院管理系统截图
- project2.jpg (800x600px) - Python数据分析平台截图
- project3.jpg (800x600px) - 微信小程序商城截图

### 团队成员照片
- team1.jpg (400x400px) - 技术总监照片
- team2.jpg (400x400px) - 项目经理照片
- team3.jpg (400x400px) - 客户服务照片

### 演示视频
- video/sl1.mp4 - 项目演示视频1
- video/sl2.mp4 - 项目演示视频2

## 图片要求

1. 所有图片应当是高质量、清晰的
2. 图片大小应当经过优化，建议单个文件不超过200KB
3. 项目截图应当展示系统的主要界面
4. 团队成员照片建议使用正式的工作照
5. 二维码图片必须清晰可扫描

## 图片优化建议

1. 使用 [TinyPNG](https://tinypng.com/) 压缩图片
2. 确保图片分辨率符合要求
3. 使用渐进式JPEG格式
4. 添加适当的 alt 文本提升可访问性

## 文件夹结构

images/
├── favicon.png
├── og-image.jpg
├── wechat-qr.jpg
├── project1.jpg
├── project2.jpg
├── project3.jpg
├── team1.jpg
├── team2.jpg
└── team3.jpg

## 临时图片解决方案

在正式图片准备好之前，可以使用以下占位图片服务：

1. 项目截图：https://via.placeholder.com/800x600
2. 团队照片：https://via.placeholder.com/400x400
3. 二维码：https://via.placeholder.com/300x300

使用示例：

<!-- 项目截图示例 -->
<img src="https://via.placeholder.com/800x600/007bff/ffffff?text=项目截图" alt="项目截图">

<!-- 团队照片示例 -->
<img src="https://via.placeholder.com/400x400/007bff/ffffff?text=团队成员" alt="团队成员照片">

<!-- 二维码示例 -->
<img src="https://via.placeholder.com/300x300/07c160/ffffff?text=微信二维码" alt="微信二维码">

## 图片命名规范

1. 使用小写字母和数字
2. 单词之间使用连字符(-)分隔
3. 避免使用空格和特殊字符
4. 使用有意义的描述性名称

示例：
- 好的命名：hospital-management-system.jpg
- 不好的命名：IMG_1234.jpg

## 图片维护建议

1. 定期检查图片是否过期或需要更新
2. 保存原始高分辨率图片备份
3. 记录图片来源和版权信息
4. 为重要图片准备多个尺寸版本

## 图片性能优化

1. 使用 CDN 加速图片加载
2. 实现图片懒加载
3. 提供响应式图片
4. 使用适当的图片格式

示例代码：

<!-- 响应式图片示例 -->
<picture>
    <source media="(min-width: 800px)" srcset="project1-large.jpg">
    <source media="(min-width: 400px)" srcset="project1-medium.jpg">
    <img src="project1-small.jpg" alt="项目截图">
</picture>

<!-- 懒加载示例 -->
<img data-src="team1.jpg" alt="团队成员" loading="lazy">

## 图片备份建议

1. 本地备份
   - 保存原始高分辨率图片
   - 按项目和日期分类存储
   - 定期备份到外部存储设备

2. 云端备份
   - 使用云存储服务（如阿里云OSS、腾讯云COS）
   - 设置适当的访问权限
   - 定期检查备份状态

## 图片更新流程

1. 准备新图片
   - 按照尺寸要求制作
   - 进行图片优化
   - 检查文件名规范

2. 更新步骤
   - 备份原有图片
   - 上传新图片
   - 更新相关文档
   - 测试网站显示

3. 发布确认
   - 检查所有页面显示
   - 验证响应式效果
   - 确认加载速度
   - 更新版本记录

## 图片安全性建议

1. 访问控制
   - 限制直接访问图片目录
   - 设置适当的文件权限
   - 使用图片水印保护版权

2. 防盗链设置
   - 配置 Referer 验证
   - 使用签名 URL
   - 设置访问频率限制

3. 定期安全检查
   - 检查图片文件完整性
   - 监控异常访问
   - 更新安全策略

## 开发环境配置

1. 本地开发
   ```bash
   # 创建图片目录
   mkdir -p images/{original,compressed}
   
   # 设置权限
   chmod 755 images
   ```

2. 图片处理工具
   - ImageMagick：批量处理图片
   - TinyPNG：在线压缩
   - WebP Convert：转换为WebP格式

3. 开发建议
   - 使用版本控制管理图片
   - 建立图片资源清单
   - 保持文件命名一致性

## 问题排查指南

1. 图片无法显示
   - 检查文件路径
   - 验证文件权限
   - 确认文件完整性

2. 加载速度慢
   - 检查图片大小
   - 验证CDN配置
   - 优化压缩比例

3. 显示异常
   - 检查图片格式
   - 验证响应式设置
   - 测试不同设备