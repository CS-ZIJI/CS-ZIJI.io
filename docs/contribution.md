---
comments: false
---

# 贡献指导

!!! warning "WIP"

    本页尚不完善！欢迎参与共同维护！

本文主要是为了统一社区贡献风格而做的一些约定，以向贡献者提供更好的协作体验、向资源使用者提供更好的阅读体验。

- [贡献指导](#贡献指导)
  - [标准工作流程](#标准工作流程)
    - [初始化](#初始化)
    - [同步模板](#同步模板)
    - [后续维护指导](#后续维护指导)
    - [写作风格指导](#写作风格指导)

## 标准工作流程

### 初始化

!!! key-point "Important"

    初始化操作可联系常驻维护者代为设置，此页更多是作为流程备忘录设置；但如果你有兴趣自己设置也可以尝试自行遵循如下步骤。

目前 ZIJI 提供了 MkDocs 的快速启动模板 [F-MkDocs-Template](https://github.com/ZIJI-CS/F-MkDocs-Template){target="_blank"}，维护者可以选择基于本仓库进行内容编写，专注于内容编写而无需在意其它的配置内容。

使用该模板进行初始化，请遵循以下步骤：

1. 克隆 [F-MkDocs-Template](https://github.com/ZIJI-CS/F-MkDocs-Template){target="_blank"} 作为 codebase
    ```shell
    git clone git@github.com:ZIJI-CS/F-MkDocs-Template.git <LocalRepoName>  # Replace <LocalRepoName>!
    ```
2. 运行 `scripts/init.sh` 完成初始化设置
   ```shell
    cd <LocalRepoName>  # Replace <LocalRepoName>!
    ./scripts/init.sh  # Remove `.trash` folder if you want after running this.
   ```
3. 修改 `mkdocs.yaml` 来进行基础设置
    1. 检查所有 `#TODO` 注释，其中 `nav` 需要在文章内容更新过程中同步进行修改
    2. 具体每个配置项的含义，请参考注释
4. 修改 `docs/index.md` 来填写课程信息，初始化内容
5. 在组织中创建 repo，启动 GitHub Action、Pages 服务，并提交 commit，检查是否正常（此步骤可委托管理员进行）
6. 修改 repo 的 About 项，填入 page URL

特别的，对于仓库命名，我们做如下约定：

- 除特殊仓库，其它仓库命名应当遵守 `{Flag}-{Name}` 的形式
- 其中，`{Flag}` 标识仓库功能，`{Name}` 标识仓库内容
- `{Flag}` 包括：
    - T(tutorial): 笔记、教程类内容资源，例如数字逻辑设计课程笔记
    - F(functional): 功能类仓库，例如模板库
    - ...

### 同步模板

有时候我们会对 F-MkDocs-Template 做一些更新，各基于此仓库展开的仓库都应当适时同步这些更新。我们已经提供了自动化的脚本来实现比较基础的同步，您可以通过执行如下命令来进行同步：

```shell
./scripts/sync_base.sh
```

但众所周知，**版本合并是一个比较复杂的问题**，如果当前项目在此前进行了修改导致出现了合并冲突，那是很正常的。此时脚本会提示您手动解决冲突。完成之后，您需要从 `./scripts/sync_base.sh` 的 Step 6 开始手动完成剩下步骤。

### 后续维护指导

直接与笔记内容有关的部分，应当全部放在 `docs` 目录下，并遵循如下组织结构：

```
.
├── index.md
├── 0-x.md
├── 1-x.md
├── ...
└── imgs
    ├── ZIJI-LOGO.png
    └── ...
```

如果有非图片类多媒体资源，请根据媒体类型创建对应的文件夹。当然，资源管理只要做到整齐即可，如果维护者认为这种结构不合适，也可以选择使用更清晰的组织方式。

### 写作风格指导

并不对写作风格做严格要求，但是最起码请保证全文**风格统一**，保证最基本的美观和整洁。

如下是一些建议：

- 引用内容做好来源标注
- 中西文之间使用空格隔开，例如：「不论 R/W 置任何值，读操作都在正常进行」
- 不要混用中文括号 `（）` 和英文括号 `()`，建议使用英文括号 `()` 进行术语翻译，用中文括号 `（）` 进行补充说明，例如：「**浙江大学(Zhejiang University, ZJU)**位于浙江省杭州市（这里特指紫荆港校区）」
- 更多内容可以参考 xg 的这份 [文档降压宝典](https://hypotensor.tonycrane.cc/ta/typesetting/){target="_blank"}