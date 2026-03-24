# MoeMail Logo Wordmark Refine Implementation Plan

> **For agentic workers:** REQUIRED: Use superpowers:subagent-driven-development (if subagents available) or superpowers:executing-plans to implement this plan. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** 让 MoeMail 的品牌字样更精致克制，同时保持与整站清爽产品感一致。

**Architecture:** 仅修改两个品牌组件中的字样类名与交互细节，不改变图标结构与品牌色方向。使用本地静态预览页作为可视化验收入口，避免被 Cloudflare 运行时依赖阻断。

**Tech Stack:** Next.js 15, Tailwind CSS, 本地静态预览服务

**Spec:** `specs/2026-03-24-logo-wordmark-refine-design.md`

---

## File Structure

- Modify: `app/components/ui/logo.tsx` - 精修顶部导航 Logo 的品牌字样。
- Modify: `app/components/ui/brand-header.tsx` - 精修品牌头部的大号字样。
- Create: `.superpowers/brainstorm/logo-wordmark-preview-v1.html` - 本地可视预览页。

## Chunk 1: 品牌字样精修

- [ ] 先用文本断言确认目标类名尚未存在，作为红灯检查。
- [ ] 调整 `logo.tsx` 的字样字重、字距、渐变与 hover 节奏。
- [ ] 调整 `brand-header.tsx` 的大号字样与导航 Logo 保持同一气质。

## Chunk 2: 可视预览

- [ ] 生成本地静态预览页，展示导航场景与品牌头部场景。
- [ ] 启动本地静态服务，提供可访问的本地链接。

## Chunk 3: 验证

- [ ] 运行文本断言确认新类名已落地。
- [ ] 运行 `npm run lint`。
- [ ] 运行 `npm run build`。
