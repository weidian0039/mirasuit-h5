# MIRASUIT H5 Landing Page

**Live URL**: https://weidian0039.github.io/mirasuit-h5/

## Deploy

### Automatic (GitHub Actions)
Push to `main` → deployed automatically via GitHub Pages.
```
git checkout -b add-actions && git add .github/ && git commit -m "ci: add GitHub Pages deploy" && git push
```
Then enable GitHub Pages: Settings → Pages → Source: GitHub Actions

### Manual
```bash
npx serve . -p 8080
# or
python3 -m http.server 8080
```

## WeChat Cloud Functions Deploy

Cloud functions are in the `mirasuit-miniprogram/cloud-functions/` directory.

### Deploy Steps

**Step 1: WeChat DevTools**
1. Open WeChat DevTools
2. Open project: `mirasuit-miniprogram/`
3. Right-click each cloud function folder → "上传并部署"

**Step 2: Configure Environment Variables**
In 微信云开发控制台 → 环境 → 环境变量:
```
ANTHROPIC_API_KEY=sk-ant-...
OPENAI_API_KEY=sk-proj-...
REPLICATE_API_KEY=r8_...
```

**Step 3: Configure AppID**
In `mirasuit-miniprogram/project.config.json`:
```json
"appid": "YOUR_WECHAT_APP_ID"
```

**Step 4: Upload Miniprogram**
WeChat DevTools → Details → 上传 (体验版)

## Environment Variables Needed

| Variable | Description | Get from |
|----------|-------------|----------|
| `ANTHROPIC_API_KEY` | Claude API key | console.anthropic.com |
| `OPENAI_API_KEY` | DALL-E 3 key | platform.openai.com |
| `REPLICATE_API_KEY` | Video model key | replicate.com |
| `WECHAT_APP_ID` | WeChat App ID | developers.weixin.qq.com |
