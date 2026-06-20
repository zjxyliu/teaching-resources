# teaching-resources

用于管理和展示教学演示页面的静态资源仓库。

## 资源组织模式

采用统一分层结构：

`学科 -> 章节 -> 页面(html)`

示例：

- 学科：大学物理
- 章节：第3章 刚体转动与角动量
- 页面：力矩演示、角动量演示等

该模式支持后续新增其它学科（如教学论）而无需重做首页。

## 当前功能

- 统一入口页面：`index.html`
- 首页导航支持：
  - 学科切换（Tab）
  - 章节分组展示
  - 关键词搜索（名称/章节/关键词）
  - 当前页打开 / 新标签页打开
  - 最近访问记录（浏览器本地存储）

## 目录结构

```text
teaching-resources/
├── index.html
├── resources/
│   ├── 大学物理/
│   │   ├── 03-刚体转动/
│   │   │   ├── 力矩.html
│   │   │   └── 角动量演示(矢量）.html
│   │   └── 04-万有引力与开普勒定律/
│   │       └── 开普勒轨道模拟（优化版）.html
│   └── 教学论/
│       └── .gitkeep
└── README.md
```

## 使用方式

1. 直接在浏览器打开 `index.html`
2. 先选择学科，再按章节浏览资源页面
3. 点击资源卡片进入对应演示

## 新增资源（推荐流程）

新增一个页面时，按以下步骤操作：

1. 在 `resources/` 下选择或新建学科目录  
   例如：`resources/大学物理/` 或 `resources/教学论/`
2. 在学科目录下新建章节目录（推荐使用“序号-章节名”）
3. 将新 `.html` 放入对应章节目录
4. 在 `index.html` 的 `catalog` 数组中维护对应学科/章节/页面信息

```javascript
{
    id: "pedagogy",
    subject: "教学论",
    description: "课程资源",
    chapters: [
        {
            id: "chapter-01",
            title: "第1章 示例章节",
            resources: [
                {
                    id: "lesson-demo",
                    title: "示例页面",
                    file: "resources/教学论/01-示例章节/示例页面.html",
                    description: "页面简介",
                    keywords: ["关键词1", "关键词2"]
                }
            ]
        }
    ]
}
```

完成后刷新 `index.html` 即可在导航页看到新资源。