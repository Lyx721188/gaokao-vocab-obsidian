# 高考英语词汇 · Obsidian 笔记版 / GAOKAO Vocabulary for Obsidian

> 高考英语大纲词表，共 **3,806 个词条**，每词一篇 Obsidian 笔记：YAML frontmatter + 音标 + 词性 + 中文释义，方便检索、双链、属性筛选与进度管理。

## 数据来源与致谢 / Source & Credits

- 词表数据提取自开源项目 [Jimmy-xuzimo/gaokao-vocab](https://github.com/Jimmy-xuzimo/gaokao-vocab)（其 README 标注为 MIT 协议）。本仓库仅采用其词表中的**事实性数据**（单词、音标、词性、通用释义），不包含原仓库的任何代码、界面素材或其他创作性内容。
- 词表本身对应教育部高考英语考试大纲词汇表（约 3,500 词级别）。
- 对源数据中若干明显损坏的条目做了修复，例如：`soft`、`sort` 的音标断行，`war` / `warn` 词条行丢失，`park` 音标误标（原为 Paris 的音标），并合并了大小写重复词条（AD/ad、march/March、fall、order 等 9 组）。

## 目录结构

```
高考词汇/
├── 00 总览.md          # 全部词条索引（按字母分组，可点击跳转）
├── A/ … Z/            # 每个首字母一个文件夹
│   └── abandon.md     # 每词一篇笔记
data/
└── gaokao-vocab.json  # 机器可读的 JSON 版词库
```

## 笔记格式

每篇笔记的 frontmatter：

```yaml
---
word: abandon
phonetic: "[əˈbændən]"
meaning:
  - v.抛弃，舍弃，放弃
tags:
  - 英语/高考词汇
mastered: false
---
```

- `word`：单词（大小写重复的词条以 `aliases` 保留别名，如 `AD` ↔ `ad`）
- `phonetic`：音标（个别词条源数据缺失则省略）
- `meaning`：释义列表（同一单词的多个义项分条列出）
- `mastered`：掌握状态开关，可用 Obsidian Properties 面板直接切换，或配合 Dataview / Bases 统计进度

## 使用方法

1. **导入已有仓库**：把 `高考词汇/` 整个文件夹复制到你的 Obsidian vault 中任意位置即可。
2. **独立使用**：将本仓库克隆为 Obsidian vault 打开（`git clone` 后在 Obsidian 中「打开文件夹作为仓库」）。
3. **程序处理**：直接读取 `data/gaokao-vocab.json`。

进度统计示例（需安装 Dataview 插件）：

```dataview
TABLE length(rows) AS 已掌握数
FROM "高考词汇"
WHERE mastered = true
GROUP BY true
```

## 许可证 / License

本仓库内容以 [**CC BY 4.0（署名 4.0 国际）**](./LICENSE) 协议开源。分发或改编时请署名并附上本仓库及 [Jimmy-xuzimo/gaokao-vocab](https://github.com/Jimmy-xuzimo/gaokao-vocab) 的链接。
