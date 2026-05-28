# 图片比例换算工具 — 开发文档

## 项目路径

`index.html` — 纯单文件，浏览器直接打开即可使用

## 用途

前端开发时，从设计稿（如 540px 宽）换算到目标设备宽度（如 375px）的尺寸计算工具。

## 核心功能

1. **图片上传** — 点击、拖拽、粘贴上传，显示原始尺寸、比例、文件大小
2. **目标宽度 & rem 基准** — 默认 375 / 37.5，实时换算所有数值
3. **分割线** — 水平线 + 垂直线，自动在图片四边添加边界线
4. **拖拽** — 拖图片外侧的数字标签或线条区域移动分割线
5. **数据面板** — 每段：原始px、换算px、占比%、rem值，带下载按钮裁切下载
6. **删除** — 标签旁 × 或面板行内 × 删除用户线（边界线不可删）

## 核心公式

```
scale = targetWidth / naturalWidth
convertedPx = originalPx × scale
percent = convertedPx / convertedDimension × 100
rem = convertedPx / remBase
```

## 技术方案

- 纯 HTML/CSS/JS 单文件，无依赖
- SVG 叠加层绘制分割线和标签，ResizeObserver 同步尺寸
- 分割线位置存原始像素坐标系，绘制时乘 displayScale 转屏幕坐标
- 边界线（boundary: true）不可拖拽不可删除，始终在图片边缘

## 交互设计

- **标签在图片外侧** — 水平线标签在左侧（x=-8），垂直线标签在上方（y=-6），不遮挡图片
- **大触摸区域** — 每条线有 14px 透明命中区域 + 带背景色的可拖拽标签手柄
- **hover 高亮** — 鼠标悬停面板表格行时图片对应段变色

## 数据结构

```js
state.hLines / state.vLines = [
  { id, pos, color, boundary? }
]
// boundary=true → 边界线（0和max），不可拖拽删除
// boundary=undefined → 用户线，可拖拽可删除
```

## 2025-05-25 改动记录

- 初始实现：图片上传、分割线、换算面板、下载功能
- 添加边界线：图片四边自动生成不可拖拽的边界线
- 标签移到图片外侧：不遮挡内容
- 增加 label-handle（可拖拽标签手柄）和 line-hitarea（14px透明命中区域）
- 删除按钮移到标签区域
