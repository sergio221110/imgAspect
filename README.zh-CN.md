# imgAspect

<img src="https://img.shields.io/badge/vanilla%20js-single%20file-8b5cf6" alt="single file badge" />
<img src="https://img.shields.io/badge/license-MIT-0ea5e9" alt="license badge" />
<img src="https://img.shields.io/badge/status-ready%20for%20github%20pages-22c55e" alt="status badge" />

一个纯前端、单文件的图片比例换算工具。它可以把设计稿图片拆分成多个分段，实时对比尺寸，并换算到目标宽度、百分比和 `rem`。

## 功能

- 支持点击、拖拽、粘贴上传图片
- 自动读取原始尺寸、比例和文件大小
- 支持设置目标宽度和 `rem` 基准
- 自动生成图片边界线，方便分段计算
- 可拖拽分割线，实时调整每一段数据
- 数据面板显示原始 `px`、换算 `px`、百分比和 `rem`
- 支持删除自定义分割线
- 支持裁切导出图片分段
- 深色 / 浅色主题切换

## 适合谁用

- 前端开发
- UI 还原
- 移动端适配
- 设计稿尺寸换算
- 需要把图片拆段做像素参考的人

## 核心公式

```text
scale = targetWidth / naturalWidth
convertedPx = originalPx × scale
percent = convertedPx / convertedDimension × 100
rem = convertedPx / remBase
```

## 本地运行

直接在浏览器中打开 `index.html` 即可使用，无需安装依赖。

## 在线演示

如果启用 GitHub Pages，这个项目可以作为静态页面直接发布，无需构建步骤。

## 截图

建议把运行中的界面截图放到这里，方便 GitHub 上快速浏览：

- `docs/screenshot-main.png`
- `docs/screenshot-dark.png`
- `docs/screenshot-light.png`

## 为什么这个仓库有价值

这个项目刻意保持轻量：

- 无运行时依赖
- 一个 HTML 文件就是核心应用
- 使用 SVG 叠加层绘制分割线和标签
- 保存原始像素坐标，缩放后不会影响计算
- 边界线固定存在，不可删除

## 建议的 GitHub 仓库简介

> 单文件浏览器工具，用于图片比例换算、分割线测量和响应式布局检查，适合前端开发中的设计稿还原和移动端适配。

## 建议标签

`javascript` `html` `css` `frontend` `image-tool` `responsive-design` `design-to-code` `rem`

## 许可证

建议在正式公开前补一个许可证。若你希望尽量开放复用，`MIT` 是比较稳妥的默认选择。
