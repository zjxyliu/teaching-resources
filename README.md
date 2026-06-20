# teaching-resources

用于管理和展示教学演示页面的静态资源仓库。

## 当前功能

- 提供统一入口页面：`index.html`
- 所有演示页面集中存放在：`html-pages/`
- 首页支持：
  - 资源卡片展示
  - 关键词搜索
  - 当前页打开 / 新标签页打开
  - 最近访问记录（浏览器本地存储）

## 目录结构

```text
teaching-resources/
├── index.html
├── html-pages/
│   ├── 力矩.html
│   ├── 开普勒轨道模拟（优化版）.html
│   └── 角动量演示(矢量）.html
└── README.md
```

## 使用方式

1. 直接在浏览器打开 `index.html`
2. 在首页点击对应资源进入演示页面

## 新增教学页面（后续扩展）

新增一个页面时，按以下步骤：

1. 将新 `.html` 文件放入 `html-pages/` 目录
2. 在 `index.html` 的 `resources` 数组中增加一项，例如：

```javascript
{
    id: "new-demo",
    title: "新演示页面",
    file: "html-pages/新演示页面.html",
    description: "页面简介",
    keywords: ["关键词1", "关键词2"]
}
```

完成后刷新 `index.html` 即可在首页看到新资源。