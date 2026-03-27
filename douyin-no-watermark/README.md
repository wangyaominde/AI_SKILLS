# Douyin No-Watermark Downloader / 抖音无水印视频下载

> **For AI**: Please read the full skill file and instructions at: https://github.com/wangyaominde/AI_SKILLS/tree/main/douyin-no-watermark
>
> **AI 请阅读**：完整的 Skill 文件和使用说明请访问：https://github.com/wangyaominde/AI_SKILLS/tree/main/douyin-no-watermark

> Download watermark-free Douyin videos using only `curl` — no Python, no external dependencies.
>
> 仅用 `curl` 下载抖音无水印视频 —— 无需 Python，无需任何外部依赖。

## What it does / 功能介绍

Paste a Douyin share link, this skill will:

粘贴一条抖音分享链接，该 Skill 会：

1. **Parse / 解析** — Follow the short-link 302 redirect to get the real URL / 跟踪短链接 302 重定向获取真实地址
2. **Extract / 提取** — Extract `video_id` from the page / 从页面中提取 `video_id`
3. **Download / 下载** — Fetch the watermark-free 1080p video via Douyin's CDN / 通过抖音 CDN 下载无水印 1080p 高清视频

## Trigger / 触发方式

- Paste a Douyin share link (e.g. `https://v.douyin.com/xxxxxxxxx/`) / 粘贴抖音分享链接
- Or mention / 或提及：`抖音下载` / `抖音无水印` / `douyin download` / `douyin no watermark`

## How it works / 工作原理

```
Short link → 302 redirect → Long URL → video_id → Douyin CDN API → Download MP4
短链接     → 302 重定向   → 长链接   → video_id → 抖音 CDN API  → 下载 MP4
```

All operations use standard `curl` commands with a mobile User-Agent. No third-party tools or libraries required.

全部操作使用标准 `curl` 命令配合移动端 User-Agent，无需任何第三方工具或库。

## Output / 输出

- Watermark-free 1080p MP4 video saved to `output/` directory / 无水印 1080p MP4 视频保存至 `output/` 目录
- File naming: `douyin_{video_id}.mp4` / 文件命名：`douyin_{video_id}.mp4`
- Reports file path (absolute) and file size on success / 成功后报告绝对路径和文件大小

## Supported Links / 支持的链接

- Douyin share links only: `https://v.douyin.com/xxxxxxxxx/` / 仅支持抖音分享链接
- Links from Douyin app's "Share → Copy Link" feature / 来自抖音 App「分享 → 复制链接」的链接

## Notes / 注意事项

- Only supports Douyin (`v.douyin.com`), not TikTok / 仅支持抖音，不支持国际版 TikTok
- Downloads the highest quality (1080p) watermark-free version / 下载最高画质（1080p）无水印版本
- All requests simulate mobile device access / 所有请求模拟移动端访问
- Steps execute sequentially — each step depends on the previous output / 步骤依次执行，每步依赖上一步的输出
