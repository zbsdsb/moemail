# MoeMail Font Refresh Implementation Plan

> **For agentic workers:** REQUIRED: Use superpowers:subagent-driven-development (if subagents available) or superpowers:executing-plans to implement this plan. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** 将 MoeMail 从整站像素字体调整为高可读的产品级无衬线字体体系。

**Architecture:** 保留本地 `zpix` 字体资源，但将其从全站默认字体降级为可选品牌字体。通过修改 Tailwind 默认 `sans` 和布局层 `body` 类名，统一收敛首页与后台三栏页的阅读体验，并只对首页大标题做轻量字距优化。

**Tech Stack:** Next.js 15, Tailwind CSS, `next/font/local`

**Spec:** `specs/2026-03-24-font-refresh-design.md`

---

## File Structure

- Modify: `app/fonts.ts` - 定义正文与品牌字体变量。
- Modify: `tailwind.config.ts` - 将 `fontFamily.sans` 切换到正文系统字体栈。
- Modify: `app/[locale]/layout.tsx` - 移除整站 `font-zpix` 默认类。
- Modify: `app/[locale]/page.tsx` - 微调首页标题字距，适配新字体。

## Chunk 1: 字体接入与全站默认字体

- [ ] 在 `app/fonts.ts` 中补充正文系统字体变量，保留 `zpix` 变量。
- [ ] 在 `tailwind.config.ts` 中把 `fontFamily.sans` 改为正文系统字体栈。
- [ ] 在 `app/[locale]/layout.tsx` 中移除 `font-zpix` 的全站应用。

## Chunk 2: 标题层级微调

- [ ] 调整 `app/[locale]/page.tsx` 首页主标题和副标题字距，使新字体看起来更稳。

## Chunk 3: 验证

- [ ] 运行 `npm run lint`。
- [ ] 运行 `npm run build`。
- [ ] 通过浏览器检查首页与邮箱三栏页的视觉效果。
