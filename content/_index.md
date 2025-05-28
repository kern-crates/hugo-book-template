---
title: xxx 的文档
titleOnly: true
weight: 1
bookToc: false
---

# 文档模板

阅读地址：<https://kern-crates.github.io/hugo-book-template>

## 首次使用

1. 创建一个 Github 仓库，假设为 my-doc
2. 将该模板下载至本地，并上传至 Github 仓库

```bash
# 下载模板到 my-doc 目录
git clone https://github.com/kern-crates/hugo-book-template.git my-doc

# 进入 my-doc 目录
cd my-doc

# 删除旧的远程仓库地址，并设置成你自己的仓库地址
git remote remove origin
git remote add origin your-repo-url # 💡: 修改此处

# 推送提交
git push --set-upstream origin main
```

3. Github 设置从 Github Action 中部署 Pages。具体见 [#1](https://github.com/kern-crates/hugo-book-template/issues/1)。
4. 在 `hugo.toml` 文件修改你的仓库等信息，尤其那些带 `💡` 的地方

## 添加/更新文档

仓库地址：<https://github.com/kern-crates/hugo-book-template>

该文档采用 hugo 生成静态网页，并在 `content/docs/` 目录添加或者更新文档。

以下是一些 make 命令简化流程：

* `make new doc=design/hi.md`：从模板中创建 `content/docs/design/hi.md` 文件
* `make serve`：本地预览文档
  * 如需修改地址和端口，使用 `make serve BIND=xxx PORT=xxx`
* `make generate`：在 public 目录中生成静态网页
  * 通常需要 baseURL 调整地址：`make generate baseURL=your-url`

注意：make 命令将把 README.md 的内容复制到 `content/_index.md`，以保持生成的网页主页与 README 内容一致。

## 相关链接

* AsyncOS 文档 ( <https://asyncos.github.io> ）采用相同的结构和模板，可以参考它的内容
* [hugo-book](https://github.com/alex-shpak/hugo-book) 主题
