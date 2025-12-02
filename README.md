 新增功能

### 1. 图片上传 (Image Upload)
- **API端点**: `/api/upload-image`
- **支持格式**: 所有图片格式 (jpg, png, gif, webp等)
- **大小限制**: 5MB
- **存储方式**: 通过 Telegram Bot 上传到 Telegram 频道

### 2. 文件上传 (File Upload)
- **API端点**: `/api/upload-file`
- **支持格式**: 所有文件类型
- **大小限制**: 10MB
- **存储方式**: 通过 Telegram Bot 上传到 Telegram 频道

### 3. 文件下载
- **访问路径**: `/file/{id}`
- **功能**: 通过 Worker 代理从 Telegram 下载文件，避免暴露 Bot Token

## 环境变量配置

在 Cloudflare Workers 中需要配置以下环境变量：

```
TG_BOT_TOKEN=你的Telegram Bot Token
TG_CHAT_ID=你的Telegram频道ID
```

还需要绑定 KV 命名空间（变量名为 `C`）用于存储文件元数据。
