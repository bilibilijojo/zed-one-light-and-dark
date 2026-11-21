# Zed One Light and Dark

A CSS-only port of the original Zed One Light and One Dark palettes for the default Obsidian interface. An independent community theme.

用 Zed 官方 **One Light** 和 **One Dark** 给 Obsidian Default 换色。工作区、导航、编辑器、浮层和内置视图使用同一套 One 颜色。字体、布局、组件尺寸和交互沿用 Obsidian。主题由 CSS 实现。 [Zed One 上游](https://github.com/zed-industries/zed/blob/10d1b2a564604dba7b8f05b157b7f9e8ed35255b/assets/themes/one/one.json)

![Zed One Light and One Dark palette preview](screenshot.png)

## 安装

需要 Obsidian **1.15.1 或更新版本**。本版在 macOS 1.15.1 验收。

1. 解压发行 ZIP，将整个 **Zed One Light and Dark** 文件夹放进目标 Vault 的 `.obsidian/themes/`。如果从本项目文件夹手动安装，先在目标 Vault 创建名为 **Zed One Light and Dark** 的文件夹，再把 `manifest.json` 和 `theme.css` 放进去。
2. 打开 **设置 → 外观 → 主题**，选择 **Zed One Light and Dark**。若主题未列出，重新打开 Obsidian。
3. 在 **基础配色方案** 选择「浅色」「深色」或「跟随系统」。主题跟随 Obsidian 切换 One Light 和 One Dark。外观中手动设置的强调色仍由 Obsidian 管理。重置强调色即可恢复 One 的默认蓝色。

从 **Zed One Light & Dark**、**Linen & Slate** 或 **One for Obsidian** 升级时，按上述步骤安装并选择新名称。两个版本以各自的目录名出现在主题列表中，切换完成后可以移除旧主题目录。

## 配色边界

- 编辑视图和阅读视图共享 One 语法色。能细分的 token 依各视图原生分词着色。例如在 Python 的编辑视图，`True` 与常规关键字共用分类。无语义标记的围栏（包括测试用 Cisco IOS 样本）使用 One 的普通代码前景。
- One 原色完整保留。One Light 的默认链接强调色在编辑器底面上的对比度约为 3.84∶1，两套上游的代码注释都是低对比用色。
- 系统绘制的菜单和窗口控件、Canvas 中用户指定的颜色及图表自定义配色沿用各自来源。使用 Obsidian 公共颜色变量的社区插件可继承主题，插件自带固定色由插件处理。

完整上游色板、语义映射和局部选择器见 [COLOR-SPEC.md](COLOR-SPEC.md)。

## 许可

本项目原创部分采用 MIT。One Light 和 One Dark 配色来自 Zed 官方主题 JSON。上游 MIT 版权归属及全文见 [LICENSE](LICENSE) 和 [THIRD-PARTY-NOTICES.md](THIRD-PARTY-NOTICES.md)。这是一个独立的 Obsidian 社区主题项目。
