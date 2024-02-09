---
title: GitHub的Raw链
categories: GIT
tags:
  - GIT
  - Javascript
---
GitHub 的 raw 链接允许用户直接访问仓库文件的原始内容。与在 GitHub 上查看文件的正常视图不同，raw 链接显示的是纯文本形式，不包含任何附加的格式或界面元素。这对于以下场景都很有用：

1. **直接下载文件**：用户可以使用 raw 链接直接下载文件的内容。
2. **嵌入脚本或样式表**：对于 JavaScript、CSS 等文件，raw 链接可以用于直接在 HTML 中嵌入或引用。
3. **API 或工具的输入**：某些在线工具或服务可能需要文件的直接链接作为输入。
4. **简化预览**：对于只想快速查看文件内容的用户，raw 视图提供了简洁方式。

加上 `?true` 参数可能是为了某种特定目的或约定。尽管 `?true` 本身并不改变 raw 文件的内容或行为，但它可能被某些工具或服务用作一个标记或检查点。

## 将普通 GitHub 链接转换为带 `?true` 的 Raw 链接

要将 GitHub 的普通文件链接转换为带 `?true` 的 raw 链接，你可以按照以下步骤操作：**定位到 `/blob/`**：在 GitHub 文件的 URL 中，你通常会看到 `/blob/` 路径，表示你正在查看该文件的某个版本。

1. 将 `github.com` 替换为 `raw.githubusercontent.com`,删除 `/blob/` 部分。
2. 把blob换成raw
3. **在 URL 末尾添加 `?true`**。

示例：

将这样的标准 GitHub 链接：

```
https://github.com/username/repository/blob/branch/folder/file.ext
```

转换为带 `?true` 的 raw 链接：

```
https://raw.githubusercontent.com/username/repository/branch/folder/file.ext?true
```

通过上述步骤，你可以将任何 GitHub 文件的链接转换为带 `?true` 的 raw 形式。


