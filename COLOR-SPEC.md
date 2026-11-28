# 配色规范

两种模式分别使用 Zed 官方 One Light 与 One Dark。源码于 **2026-11-20（Asia/Shanghai）** 获取，自 Zed 提交 `10d1b2a564604dba7b8f05b157b7f9e8ed35255b` 读取。原始 JSON SHA-256 为 `ed6cf88015f2f9b39691315840cf0615f35cdc1be4a61f9f0dba8183fa427695`。 [固定版本 JSON](https://github.com/zed-industries/zed/blob/10d1b2a564604dba7b8f05b157b7f9e8ed35255b/assets/themes/one/one.json) · [Zed 官方主题文档](https://zed.dev/docs/themes)

## 颜色使用规则

- HEX 原样记录，保留大小写及 6/8 位写法。8 位末两位是 alpha，`00` 为全透明，`ff` 为全不透明。`null` 是源码显式空值，「缺失」表示该主题没有该键。
- 每套均含 46 个语法颜色与 8 组 player，每组 3 个颜色。Light 共 205 个、Dark 共 207 个实际色值，按来源字段计数，重复色值分别保留。两套各有两个显式空值。Dark 独有两个冲突标记键。
- 运行时保持宿主按 `.theme-light`、`.theme-dark` 自动切换。公共表面和交互变量服务于整个应用。局部作用域用于宿主角色与 One 角色不重合的组件，以及原生围栏分词。
- Markdown 阅读正文使用 `text`，未分词的围栏使用 `editor.foreground`。Dark 的两者分别是 `#dce0e5ff` 和 `#acb2beff`。围栏高亮使用 `syntax.*.color`，上游同节点的字重和斜体信息仅用于识别上游结构。
- 源码 alpha 直接用于半透明状态。Obsidian 1.15.1 的 Callout 接受标准 CSS 颜色，原始 HEX 直接输入，宿主仍施加原生背景混合和边框透明度。Canvas 自定色、系统遮罩与原生透明窗口按宿主处理。
- 色板条目中的「已用」表示至少一个 CSS 声明直接消费此来源。「留档」包含终端、多人协作、不可分的语法及无原生对应物的色值。非活动主标签直接显示标签栏的颜色，两个模式上游的 `tab.inactive_background` 均与 `tab_bar.background` 相同。


## 基础界面、窗口、面板及滚动条

| Zed 原始键 | One Light | One Dark | 移植状态 |
| --- | --- | --- | --- |
| `border` | `#c9c9caff` | `#464b57ff` | 已用 |
| `border.variant` | `#dfdfe0ff` | `#363c46ff` | 已用 |
| `border.focused` | `#7d82e8ff` | `#47679eff` | 已用 |
| `border.selected` | `#cbcdf6ff` | `#293b5bff` | 已用 |
| `border.transparent` | `#00000000` | `#00000000` | 留档 |
| `border.disabled` | `#d3d3d4ff` | `#414754ff` | 已用 |
| `elevated_surface.background` | `#ebebecff` | `#2f343eff` | 已用 |
| `surface.background` | `#ebebecff` | `#2f343eff` | 已用 |
| `background` | `#dcdcddff` | `#3b414dff` | 已用 |
| `element.background` | `#ebebecff` | `#2e343eff` | 已用 |
| `element.hover` | `#dfdfe0ff` | `#363c46ff` | 已用 |
| `element.active` | `#cacacaff` | `#454a56ff` | 已用 |
| `element.selected` | `#cacacaff` | `#454a56ff` | 已用 |
| `element.disabled` | `#ebebecff` | `#2e343eff` | 留档 |
| `drop_target.background` | `#7e808780` | `#83899480` | 已用 |
| `ghost_element.background` | `#00000000` | `#00000000` | 已用 |
| `ghost_element.hover` | `#dfdfe0ff` | `#363c46ff` | 已用 |
| `ghost_element.active` | `#cacacaff` | `#454a56ff` | 已用 |
| `ghost_element.selected` | `#cacacaff` | `#454a56ff` | 已用 |
| `ghost_element.disabled` | `#ebebecff` | `#2e343eff` | 留档 |
| `text` | `#242529ff` | `#dce0e5ff` | 已用 |
| `text.muted` | `#58585aff` | `#a9afbcff` | 已用 |
| `text.placeholder` | `#7e8086ff` | `#878a98ff` | 已用 |
| `text.disabled` | `#7e8086ff` | `#878a98ff` | 已用 |
| `text.accent` | `#5c78e2ff` | `#74ade8ff` | 已用 |
| `icon` | `#242529ff` | `#dce0e5ff` | 已用 |
| `icon.muted` | `#58585aff` | `#a9afbcff` | 已用 |
| `icon.disabled` | `#7e8086ff` | `#878a98ff` | 留档 |
| `icon.placeholder` | `#58585aff` | `#a9afbcff` | 已用 |
| `icon.accent` | `#5c78e2ff` | `#74ade8ff` | 已用 |
| `status_bar.background` | `#dcdcddff` | `#3b414dff` | 已用 |
| `title_bar.background` | `#dcdcddff` | `#3b414dff` | 已用 |
| `title_bar.inactive_background` | `#ebebecff` | `#2e343eff` | 已用 |
| `toolbar.background` | `#fafafaff` | `#282c33ff` | 已用 |
| `tab_bar.background` | `#ebebecff` | `#2f343eff` | 已用 |
| `tab.inactive_background` | `#ebebecff` | `#2f343eff` | 留档 |
| `tab.active_background` | `#fafafaff` | `#282c33ff` | 已用 |
| `search.match_background` | `#5c79e266` | `#74ade866` | 已用 |
| `search.active_match_background` | `#d0a92366` | `#e8af7466` | 已用 |
| `panel.background` | `#ebebecff` | `#2f343eff` | 已用 |
| `panel.focused_border` | `null` | `null` | 留档 |
| `pane.focused_border` | `null` | `null` | 留档 |
| `scrollbar.thumb.background` | `#383a414c` | `#c8ccd44c` | 已用 |
| `scrollbar.thumb.hover_background` | `#dfdfe0ff` | `#363c46ff` | 已用 |
| `scrollbar.thumb.border` | `#dfdfe0ff` | `#363c46ff` | 留档 |
| `scrollbar.track.background` | `#00000000` | `#00000000` | 已用 |
| `scrollbar.track.border` | `#eeeeeeff` | `#2e333cff` | 留档 |
| `link_text.hover` | `#5c78e2ff` | `#74ade8ff` | 已用 |

## 编辑器与定位高亮

| Zed 原始键 | One Light | One Dark | 移植状态 |
| --- | --- | --- | --- |
| `editor.foreground` | `#242529ff` | `#acb2beff` | 已用 |
| `editor.background` | `#fafafaff` | `#282c33ff` | 已用 |
| `editor.gutter.background` | `#fafafaff` | `#282c33ff` | 留档 |
| `editor.subheader.background` | `#ebebecff` | `#2f343eff` | 留档 |
| `editor.active_line.background` | `#ebebecbf` | `#2f343ebf` | 留档 |
| `editor.highlighted_line.background` | `#ebebecff` | `#2f343eff` | 已用 |
| `editor.line_number` | `#b4b4bb` | `#4e5a5f` | 已用 |
| `editor.active_line_number` | `#44454b` | `#d0d4da` | 已用 |
| `editor.hover_line_number` | `#61616b` | `#acb0b4` | 已用 |
| `editor.invisible` | `#b4b4bb` | `#4e5a5f` | 留档 |
| `editor.wrap_guide` | `#383a410d` | `#c8ccd40d` | 留档 |
| `editor.active_wrap_guide` | `#383a411a` | `#c8ccd41a` | 留档 |
| `editor.document_highlight.read_background` | `#5c78e225` | `#74ade81a` | 已用 |
| `editor.document_highlight.write_background` | `#a3a3a466` | `#555a6366` | 留档 |

## 终端与 ANSI

| Zed 原始键 | One Light | One Dark | 移植状态 |
| --- | --- | --- | --- |
| `terminal.background` | `#fafafaff` | `#282c34ff` | 留档 |
| `terminal.foreground` | `#2a2c33ff` | `#abb2bfff` | 留档 |
| `terminal.bright_foreground` | `#2a2c33ff` | `#dce0e5ff` | 留档 |
| `terminal.dim_foreground` | `#bbbbbbff` | `#636d83ff` | 留档 |
| `terminal.ansi.black` | `#000000ff` | `#282c34ff` | 已用 |
| `terminal.ansi.bright_black` | `#000000ff` | `#636d83ff` | 留档 |
| `terminal.ansi.dim_black` | `#555555ff` | `#3b3f4aff` | 留档 |
| `terminal.ansi.red` | `#de3e35ff` | `#e06c75ff` | 留档 |
| `terminal.ansi.bright_red` | `#de3e35ff` | `#EA858Bff` | 已用 |
| `terminal.ansi.dim_red` | `#9c2b26ff` | `#a7545aff` | 留档 |
| `terminal.ansi.green` | `#3f953aff` | `#98c379ff` | 留档 |
| `terminal.ansi.bright_green` | `#3f953aff` | `#AAD581ff` | 已用 |
| `terminal.ansi.dim_green` | `#2b6927ff` | `#6d8f59ff` | 留档 |
| `terminal.ansi.yellow` | `#d2b67cff` | `#e5c07bff` | 留档 |
| `terminal.ansi.bright_yellow` | `#d2b67cff` | `#FFD885ff` | 留档 |
| `terminal.ansi.dim_yellow` | `#a48c5aff` | `#b8985bff` | 留档 |
| `terminal.ansi.blue` | `#2f5af3ff` | `#61afefff` | 留档 |
| `terminal.ansi.bright_blue` | `#2f5af3ff` | `#85C1FFff` | 留档 |
| `terminal.ansi.dim_blue` | `#2140abff` | `#457cadff` | 留档 |
| `terminal.ansi.magenta` | `#950095ff` | `#c678ddff` | 留档 |
| `terminal.ansi.bright_magenta` | `#a00095ff` | `#D398EBff` | 留档 |
| `terminal.ansi.dim_magenta` | `#6a006aff` | `#8d54a0ff` | 留档 |
| `terminal.ansi.cyan` | `#0997b3ff` | `#56b6c2ff` | 留档 |
| `terminal.ansi.bright_cyan` | `#0bbcd6ff` | `#6ED5DEff` | 留档 |
| `terminal.ansi.dim_cyan` | `#0a7b92ff` | `#3c818aff` | 留档 |
| `terminal.ansi.white` | `#bbbbbbff` | `#abb2bfff` | 留档 |
| `terminal.ansi.bright_white` | `#ffffffff` | `#fafafaff` | 留档 |
| `terminal.ansi.dim_white` | `#888888ff` | `#8f969bff` | 留档 |

## 版本控制和状态

| Zed 原始键 | One Light | One Dark | 移植状态 |
| --- | --- | --- | --- |
| `version_control.added` | `#27a657ff` | `#27a657ff` | 留档 |
| `version_control.modified` | `#d3b020ff` | `#d3b020ff` | 留档 |
| `version_control.word_added` | `#2EA04859` | `#2EA04859` | 留档 |
| `version_control.word_deleted` | `#F85149CC` | `#78081BCC` | 留档 |
| `version_control.deleted` | `#e06c76ff` | `#e06c76ff` | 留档 |
| `conflict` | `#a48819ff` | `#dec184ff` | 留档 |
| `conflict.background` | `#faf2e6ff` | `#dec1841a` | 留档 |
| `conflict.border` | `#f4e7d1ff` | `#5d4c2fff` | 留档 |
| `created` | `#669f59ff` | `#a1c181ff` | 留档 |
| `created.background` | `#dfeadbff` | `#a1c1811a` | 留档 |
| `created.border` | `#c8dcc1ff` | `#38482fff` | 留档 |
| `deleted` | `#d36151ff` | `#d07277ff` | 留档 |
| `deleted.background` | `#fbdfd9ff` | `#d072771a` | 留档 |
| `deleted.border` | `#f6c6bdff` | `#4c2b2cff` | 留档 |
| `error` | `#d36151ff` | `#d07277ff` | 已用 |
| `error.background` | `#fbdfd9ff` | `#d072771a` | 已用 |
| `error.border` | `#f6c6bdff` | `#4c2b2cff` | 留档 |
| `hidden` | `#7e8086ff` | `#878a98ff` | 留档 |
| `hidden.background` | `#dcdcddff` | `#696b771a` | 留档 |
| `hidden.border` | `#d3d3d4ff` | `#414754ff` | 留档 |
| `hint` | `#7274a7ff` | `#788ca6ff` | 留档 |
| `hint.background` | `#e2e2faff` | `#5a6f891a` | 已用 |
| `hint.border` | `#cbcdf6ff` | `#293b5bff` | 留档 |
| `ignored` | `#7e8086ff` | `#878a98ff` | 留档 |
| `ignored.background` | `#dcdcddff` | `#696b771a` | 留档 |
| `ignored.border` | `#c9c9caff` | `#464b57ff` | 留档 |
| `info` | `#5c78e2ff` | `#74ade8ff` | 已用 |
| `info.background` | `#e2e2faff` | `#74ade81a` | 已用 |
| `info.border` | `#cbcdf6ff` | `#293b5bff` | 留档 |
| `modified` | `#a48819ff` | `#dec184ff` | 留档 |
| `modified.background` | `#faf2e6ff` | `#dec1841a` | 已用 |
| `modified.border` | `#f4e7d1ff` | `#5d4c2fff` | 留档 |
| `predictive` | `#9b9ec6ff` | `#5a6a87ff` | 留档 |
| `predictive.background` | `#dfeadbff` | `#5a6a871a` | 留档 |
| `predictive.border` | `#c8dcc1ff` | `#38482fff` | 留档 |
| `renamed` | `#5c78e2ff` | `#74ade8ff` | 留档 |
| `renamed.background` | `#e2e2faff` | `#74ade81a` | 留档 |
| `renamed.border` | `#cbcdf6ff` | `#293b5bff` | 留档 |
| `success` | `#669f59ff` | `#a1c181ff` | 已用 |
| `success.background` | `#dfeadbff` | `#a1c1811a` | 已用 |
| `success.border` | `#c8dcc1ff` | `#38482fff` | 留档 |
| `unreachable` | `#58585aff` | `#a9afbcff` | 留档 |
| `unreachable.background` | `#dcdcddff` | `#8389941a` | 留档 |
| `unreachable.border` | `#c9c9caff` | `#464b57ff` | 留档 |
| `warning` | `#a48819ff` | `#dec184ff` | 已用 |
| `warning.background` | `#faf2e6ff` | `#dec1841a` | 已用 |
| `warning.border` | `#f4e7d1ff` | `#5d4c2fff` | 留档 |
| `version_control.conflict_marker.ours` | 缺失 | `#a1c1811a` | 留档 |
| `version_control.conflict_marker.theirs` | 缺失 | `#74ade81a` | 留档 |

## 参与者光标和选区

| Zed 原始键 | One Light | One Dark | 移植状态 |
| --- | --- | --- | --- |
| `players[0].cursor` | `#5c78e2ff` | `#74ade8ff` | 已用 |
| `players[0].background` | `#5c78e2ff` | `#74ade8ff` | 留档 |
| `players[0].selection` | `#5c78e23d` | `#74ade83d` | 已用 |
| `players[1].cursor` | `#984ea5ff` | `#be5046ff` | 留档 |
| `players[1].background` | `#984ea5ff` | `#be5046ff` | 留档 |
| `players[1].selection` | `#984ea53d` | `#be50463d` | 留档 |
| `players[2].cursor` | `#ad6e26ff` | `#bf956aff` | 留档 |
| `players[2].background` | `#ad6e26ff` | `#bf956aff` | 留档 |
| `players[2].selection` | `#ad6e263d` | `#bf956a3d` | 留档 |
| `players[3].cursor` | `#a349abff` | `#b477cfff` | 留档 |
| `players[3].background` | `#a349abff` | `#b477cfff` | 留档 |
| `players[3].selection` | `#a349ab3d` | `#b477cf3d` | 留档 |
| `players[4].cursor` | `#3a82b7ff` | `#6eb4bfff` | 留档 |
| `players[4].background` | `#3a82b7ff` | `#6eb4bfff` | 留档 |
| `players[4].selection` | `#3a82b73d` | `#6eb4bf3d` | 留档 |
| `players[5].cursor` | `#d36151ff` | `#d07277ff` | 留档 |
| `players[5].background` | `#d36151ff` | `#d07277ff` | 留档 |
| `players[5].selection` | `#d361513d` | `#d072773d` | 留档 |
| `players[6].cursor` | `#a48819ff` | `#dec184ff` | 留档 |
| `players[6].background` | `#dec184ff` | `#dec184ff` | 留档 |
| `players[6].selection` | `#dec1843d` | `#dec1843d` | 留档 |
| `players[7].cursor` | `#669f59ff` | `#a1c181ff` | 留档 |
| `players[7].background` | `#669f59ff` | `#a1c181ff` | 留档 |
| `players[7].selection` | `#669f593d` | `#a1c1813d` | 留档 |

## 语法

| Zed 原始键 | One Light | One Dark | 移植状态 |
| --- | --- | --- | --- |
| `syntax.attribute` | `#5c78e2ff` | `#74ade8ff` | 已用 |
| `syntax.boolean` | `#ad6e25ff` | `#bf956aff` | 已用 |
| `syntax.comment` | `#a2a3a7ff` | `#5d636fff` | 已用 |
| `syntax.comment.doc` | `#7c7e86ff` | `#878e98ff` | 留档 |
| `syntax.constant` | `#c18401ff` | `#dfc184ff` | 已用 |
| `syntax.constructor` | `#5c78e2ff` | `#73ade9ff` | 留档 |
| `syntax.embedded` | `#242529ff` | `#dce0e5ff` | 已用 |
| `syntax.emphasis` | `#5c78e2ff` | `#74ade8ff` | 已用 |
| `syntax.emphasis.strong` | `#ad6e25ff` | `#bf956aff` | 已用 |
| `syntax.enum` | `#3882b7ff` | `#6eb4bfff` | 留档 |
| `syntax.function` | `#5b79e3ff` | `#73ade9ff` | 已用 |
| `syntax.hint` | `#7274a7ff` | `#788ca6ff` | 留档 |
| `syntax.keyword` | `#a449abff` | `#b477cfff` | 已用 |
| `syntax.label` | `#5c78e2ff` | `#74ade8ff` | 留档 |
| `syntax.link_text` | `#5b79e3ff` | `#73ade9ff` | 留档 |
| `syntax.link_uri` | `#3882b7ff` | `#6eb4bfff` | 留档 |
| `syntax.namespace` | `#242529ff` | `#dce0e5ff` | 留档 |
| `syntax.number` | `#ad6e25ff` | `#bf956aff` | 已用 |
| `syntax.operator` | `#3882b7ff` | `#6eb4bfff` | 已用 |
| `syntax.predictive` | `#9b9ec6ff` | `#5a6a87ff` | 留档 |
| `syntax.preproc` | `#a449abff` | `#b477cfff` | 留档 |
| `syntax.primary` | `#242529ff` | `#acb2beff` | 留档 |
| `syntax.property` | `#d3604fff` | `#d07277ff` | 已用 |
| `syntax.punctuation` | `#242529ff` | `#acb2beff` | 已用 |
| `syntax.punctuation.bracket` | `#4d4f52ff` | `#b2b9c6ff` | 已用 |
| `syntax.punctuation.delimiter` | `#4d4f52ff` | `#b2b9c6ff` | 留档 |
| `syntax.punctuation.list_marker` | `#d3604fff` | `#d07277ff` | 已用 |
| `syntax.punctuation.markup` | `#d3604fff` | `#d07277ff` | 留档 |
| `syntax.punctuation.special` | `#b92b46ff` | `#b1574bff` | 留档 |
| `syntax.selector` | `#669f59ff` | `#dfc184ff` | 已用 |
| `syntax.selector.pseudo` | `#5c78e2ff` | `#74ade8ff` | 已用 |
| `syntax.string` | `#649f57ff` | `#a1c181ff` | 已用 |
| `syntax.string.escape` | `#7c7e86ff` | `#878e98ff` | 留档 |
| `syntax.string.regex` | `#ad6e26ff` | `#bf956aff` | 已用 |
| `syntax.string.special` | `#ad6e26ff` | `#bf956aff` | 留档 |
| `syntax.string.special.symbol` | `#ad6e26ff` | `#bf956aff` | 留档 |
| `syntax.tag` | `#5c78e2ff` | `#74ade8ff` | 已用 |
| `syntax.text.literal` | `#649f57ff` | `#a1c181ff` | 已用 |
| `syntax.title` | `#d3604fff` | `#d07277ff` | 已用 |
| `syntax.type` | `#3882b7ff` | `#6eb4bfff` | 已用 |
| `syntax.variable` | `#242529ff` | `#acb2beff` | 已用 |
| `syntax.variable.parameter` | `#d3604fff` | `#d07277ff` | 已用 |
| `syntax.variable.special` | `#ad6e25ff` | `#bf956aff` | 留档 |
| `syntax.variant` | `#5b79e3ff` | `#73ade9ff` | 留档 |
| `syntax.diff.plus` | `#50a14fff` | `#98c379ff` | 已用 |
| `syntax.diff.minus` | `#e45649ff` | `#e06c75ff` | 已用 |

## 已实装映射

每行给出精确来源、两套颜色和 Obsidian 入口。局部声明标出选择器。基础色兼容档、没有 Zed 同名控件的映射及宿主汇合分类列为借用或近似。

### 基础色、通用表面和前景

Zed 的中性色复用到宿主等级刻度。Obsidian 可继续用这些变量为内置视图和第三方插件调色。同一颜色承担基础与组件角色时使用相同来源。

| Zed 原始键 | One Light | One Dark | Obsidian 入口 | 关系 |
| --- | --- | --- | --- | --- |
| `editor.background` | `#fafafaff` | `#282c33ff` | `--color-base-00` | 近似或借用 |
| `toolbar.background` | `#fafafaff` | `#282c33ff` | `--color-base-05` | 近似或借用 |
| `element.background` | `#ebebecff` | `#2e343eff` | `--color-base-10`、`--background-modifier-form-field` | 近似或借用 |
| `surface.background` | `#ebebecff` | `#2f343eff` | `--color-base-20`、`--drag-item-background` | 近似或借用 |
| `border.variant` | `#dfdfe0ff` | `#363c46ff` | `--color-base-25`、`--divider-color` | 近似或借用 |
| `background` | `#dcdcddff` | `#3b414dff` | `--color-base-30`、`--background-secondary-alt` | 近似或借用 |
| `border.disabled` | `#d3d3d4ff` | `#414754ff` | `--color-base-35`、`--background-modifier-border-hover` | 近似或借用 |
| `border` | `#c9c9caff` | `#464b57ff` | `--color-base-40` | 近似或借用 |
| `editor.line_number` | `#b4b4bb` | `#4e5a5f` | `--color-base-50` | 近似或借用 |
| `text.placeholder` | `#7e8086ff` | `#878a98ff` | `--color-base-60`、`--text-faint` | 近似或借用 |
| `text.muted` | `#58585aff` | `#a9afbcff` | `--color-base-70` | 近似或借用 |
| `text` | `#242529ff` | `#dce0e5ff` | `--color-base-100`、`--drag-ghost-text-color` | 近似或借用 |
| `error` | `#d36151ff` | `#d07277ff` | `--color-red`、`--background-modifier-error` | 近似或借用 |
| `syntax.number` | `#ad6e25ff` | `#bf956aff` | `--color-orange` | 近似或借用 |
| `warning` | `#a48819ff` | `#dec184ff` | `--color-yellow`、`--background-modifier-warning` | 近似或借用 |
| `success` | `#669f59ff` | `#a1c181ff` | `--color-green`、`--background-modifier-success` | 近似或借用 |
| `syntax.type` | `#3882b7ff` | `#6eb4bfff` | `--color-cyan` | 近似或借用 |
| `text.accent` | `#5c78e2ff` | `#74ade8ff` | `--color-blue` | 近似或借用 |
| `syntax.keyword` | `#a449abff` | `#b477cfff` | `--color-purple` | 近似或借用 |
| `terminal.ansi.bright_red` | `#de3e35ff` | `#EA858Bff` | `--color-pink`、`--background-modifier-error-hover` | 近似或借用 |
| `editor.background` | `#fafafaff` | `#282c33ff` | `--background-primary` | 直接 |
| `surface.background` | `#ebebecff` | `#2f343eff` | `--background-primary-alt` | 直接 |
| `panel.background` | `#ebebecff` | `#2f343eff` | `--background-secondary` | 直接 |
| `border` | `#c9c9caff` | `#464b57ff` | `--background-modifier-border` | 直接 |
| `border.focused` | `#7d82e8ff` | `#47679eff` | `--background-modifier-border-focus` | 直接 |
| `ghost_element.hover` | `#dfdfe0ff` | `#363c46ff` | `--background-modifier-hover` | 近似或借用 |
| `ghost_element.active` | `#cacacaff` | `#454a56ff` | `--background-modifier-active-hover` | 近似或借用 |
| `element.hover` | `#dfdfe0ff` | `#363c46ff` | `--background-modifier-form-field-hover` | 近似或借用 |
| `syntax.constant` | `#c18401ff` | `#dfc184ff` | `--background-modifier-warning-hover` | 近似或借用 |
| `text` | `#242529ff` | `#dce0e5ff` | `--text-normal` | 直接 |
| `text.muted` | `#58585aff` | `#a9afbcff` | `--text-muted` | 直接 |
| `error` | `#d36151ff` | `#d07277ff` | `--text-error` | 直接 |
| `success` | `#669f59ff` | `#a1c181ff` | `--text-success` | 直接 |
| `warning` | `#a48819ff` | `#dec184ff` | `--text-warning` | 直接 |
| `players[0].selection` | `#5c78e23d` | `#74ade83d` | `--text-selection` | 直接 |
| `icon.muted` | `#58585aff` | `#a9afbcff` | `--icon-color` | 直接 |
| `icon` | `#242529ff` | `#dce0e5ff` | `--icon-color-hover`、`--icon-color-focused` | 近似或借用 |
| `icon.accent` | `#5c78e2ff` | `#74ade8ff` | `--icon-color-active` | 直接 |
| `element.background` | `#ebebecff` | `#2e343eff` | `--interactive-normal` | 直接 |
| `element.hover` | `#dfdfe0ff` | `#363c46ff` | `--interactive-hover` | 直接 |
| `text.placeholder` | `#7e8086ff` | `#878a98ff` | `--input-placeholder-color` | 直接 |
| `players[0].cursor` | `#5c78e2ff` | `#74ade8ff` | `--caret-color` | 直接 |
| `scrollbar.track.background` | `#00000000` | `#00000000` | `--scrollbar-bg` | 直接 |
| `scrollbar.thumb.background` | `#383a414c` | `#c8ccd44c` | `--scrollbar-thumb-bg` | 直接 |
| `scrollbar.thumb.hover_background` | `#dfdfe0ff` | `#363c46ff` | `--scrollbar-active-thumb-bg` | 近似或借用 |
| `drop_target.background` | `#7e808780` | `#83899480` | `--drag-ghost-background` | 近似或借用 |
| `border.focused` | `#7d82e8ff` | `#47679eff` | `--divider-color-hover` | 近似或借用 |

### 原生强调色设置

原始强调色用作默认链接和主操作。主按钮悬停填色借用聚焦边线，Dark 悬停前景改用 Zed 正文色。主操作常态前景借用本模式终端黑色。HSL 三通道从同一 HEX 转码，只用于宿主外观取色器。Obsidian 写入用户强调色后沿用宿主色彩派生。

| Zed 原始键 | One Light | One Dark | Obsidian 入口 | 关系 |
| --- | --- | --- | --- | --- |
| `text.accent` | `#5c78e2ff` | `#74ade8ff` | `--color-accent`、`--text-accent` | 直接 |
| `border.focused` | `#7d82e8ff` | `#47679eff` | `--color-accent-1`、`--color-accent-2`、`--interactive-accent-hover` | 近似或借用 |
| `link_text.hover` | `#5c78e2ff` | `#74ade8ff` | `--text-accent-hover` | 直接 |
| `text.accent` | `#5c78e2ff` | `#74ade8ff` | `--interactive-accent` | 近似或借用 |
| `terminal.ansi.black` | `#000000ff` | `#282c34ff` | `--text-on-accent` | 近似或借用 |
| `text.accent` | `#5c78e2ff` | `#74ade8ff` | `--accent-h`（无损 HSL 通道） | 近似或借用 |
| `text.accent` | `#5c78e2ff` | `#74ade8ff` | `--accent-s`（无损 HSL 通道） | 近似或借用 |
| `text.accent` | `#5c78e2ff` | `#74ade8ff` | `--accent-l`（无损 HSL 通道） | 近似或借用 |
| `text` | `#242529ff` | `#dce0e5ff` | `--text-on-accent`（`.theme-dark:not([style*="--accent-h:"]) button.mod-cta:is(:hover, .mobile-tap)`） | 近似或借用 |

### 工作区与导航

活动主标签使用原生卡片轮廓。悬停在未激活的主标签上时，内层显示悬停底色，外轮廓使用透明色，与 Default 的层级一致。Ribbon 底色复用外框色，悬停借用比外框更深的上游颜色，以获得清楚的凹下效果。两侧文件、反向链接及其他侧栏视图共享面板。仅给非原生透明窗口的工作区与应用外壳着色。

| Zed 原始键 | One Light | One Dark | Obsidian 入口 | 关系 |
| --- | --- | --- | --- | --- |
| `title_bar.inactive_background` | `#ebebecff` | `#2e343eff` | `--titlebar-background` | 直接 |
| `title_bar.background` | `#dcdcddff` | `#3b414dff` | `--titlebar-background-focused` | 直接 |
| `border.variant` | `#dfdfe0ff` | `#363c46ff` | `--titlebar-border-color`、`--status-bar-border-color`、`--tab-divider-color`、`--tab-outline-color`、`--nav-indentation-guide-color` | 近似或借用 |
| `text.muted` | `#58585aff` | `#a9afbcff` | `--titlebar-text-color`、`--status-bar-text-color`、`--tab-text-color`、`--tab-text-color-focused`、`--nav-item-color`、`--nav-heading-color-collapsed` | 近似或借用 |
| `text` | `#242529ff` | `#dce0e5ff` | `--titlebar-text-color-focused`、`--tab-text-color-active`、`--tab-text-color-focused-active`、`--tab-text-color-focused-active-current`、`--nav-item-color-hover`、`--nav-item-color-active`、`--nav-item-color-selected`、`--nav-heading-color`、`--nav-heading-color-hover`、`--nav-heading-color-collapsed-hover` | 近似或借用 |
| `background` | `#dcdcddff` | `#3b414dff` | `--ribbon-background`、`--ribbon-background-collapsed` | 近似或借用 |
| `status_bar.background` | `#dcdcddff` | `#3b414dff` | `--status-bar-background` | 直接 |
| `tab_bar.background` | `#ebebecff` | `#2f343eff` | `--tab-container-background`、`--sidebar-tab-container-background` | 直接 |
| `tab.active_background` | `#fafafaff` | `#282c33ff` | `--tab-background-active` | 直接 |
| `border` | `#c9c9caff` | `#464b57ff` | `--tab-outline-color-hover` | 近似或借用 |
| `ghost_element.background` | `#00000000` | `#00000000` | 主标签栏的 `--tab-outline-color-hover`（`.mod-root .workspace-tab-header-container`） | 近似或借用 |
| `ghost_element.hover` | `#dfdfe0ff` | `#363c46ff` | `--tab-inner-background-hover` | 近似或借用 |
| `text.accent` | `#5c78e2ff` | `#74ade8ff` | `--tab-text-color-focused-highlighted`、`--nav-item-color-highlighted` | 近似或借用 |
| `ghost_element.hover` | `#dfdfe0ff` | `#363c46ff` | `--nav-item-background-hover` | 直接 |
| `ghost_element.active` | `#cacacaff` | `#454a56ff` | `--nav-item-background-active` | 直接 |
| `ghost_element.selected` | `#cacacaff` | `#454a56ff` | `--nav-item-background-selected` | 直接 |
| `icon.muted` | `#58585aff` | `#a9afbcff` | `--nav-collapse-icon-color` | 近似或借用 |
| `icon.placeholder` | `#58585aff` | `#a9afbcff` | `--nav-collapse-icon-color-collapsed` | 近似或借用 |
| `toolbar.background` | `#fafafaff` | `#282c33ff` | `--file-header-background`、`--file-header-background-focused` | 直接 |
| `panel.background` | `#ebebecff` | `#2f343eff` | `--mobile-sidebar-background` | 近似或借用 |
| `background` | `#dcdcddff` | `#3b414dff` | `background-color`（`body:not(.is-translucent) :where(.app-container, .workspace)`） | 近似或借用 |
| `tab_bar.background` | `#ebebecff` | `#2f343eff` | `--tab-container-background`、`--sidebar-tab-container-background`（`.workspace-tabs.mod-top`） | 直接 |
| `tab_bar.background` | `#ebebecff` | `#2f343eff` | macOS 隐藏标题栏时的主 Ribbon 顶部背景 | 借用标签栏颜色，使原生窗口按钮后方与相邻标签栏连续；透明窗口沿用宿主 |
| `panel.background` | `#ebebecff` | `#2f343eff` | `--file-header-background`、`--file-header-background-focused`（`.workspace :where(.mod-sidedock) .view-header`） | 直接 |
| Light `element.active` / Dark `editor.background` | `#cacacaff` | `#282c33ff` | 左侧 Ribbon 图标的 `--background-modifier-hover` | 近似或借用 |

### 设置、浮层及搜索

所有浮层借用同一抬升表面。设置页左侧导航、右侧面板及设置组共用抬升表面，通过宿主原有分隔线区分区域。普通按钮和输入框借用编辑器底色，保持控件辨识度。设置分类使用选中元素色。搜索命中和 Markdown 高亮各自走宿主入口。全库搜索使用普通搜索匹配色，编辑器内查找使用当前匹配色。应用绘制的菜单获得配色，系统菜单沿用平台。

| Zed 原始键 | One Light | One Dark | Obsidian 入口 | 关系 |
| --- | --- | --- | --- | --- |
| `elevated_surface.background` | `#ebebecff` | `#2f343eff` | `--modal-background`、`--menu-background`、`--prompt-background`、`--suggestion-background`、`--tooltip-background`、`--notice-background` | 直接 |
| `border` | `#c9c9caff` | `#464b57ff` | `--modal-border-color`、`--menu-border-color`、`--prompt-border-color` | 近似或借用 |
| `border.variant` | `#dfdfe0ff` | `#363c46ff` | `--menu-divider-color` | 近似或借用 |
| `text` | `#242529ff` | `#dce0e5ff` | `--tooltip-color`、`--notice-color` | 近似或借用 |
| `surface.background` | `#ebebecff` | `#2f343eff` | `--search-result-background` | 近似或借用 |
| `icon.muted` | `#58585aff` | `#a9afbcff` | `--search-icon-color` | 近似或借用 |
| `icon.placeholder` | `#58585aff` | `#a9afbcff` | `--search-clear-button-color` | 近似或借用 |
| `elevated_surface.background` | `#ebebecff` | `#2f343eff` | `--settings-background`（`.modal:where(.mod-settings, .mod-community-theme)`） | 近似或借用 |
| `panel.background` | `#ebebecff` | `#2f343eff` | `--modal-sidebar-background`（`.modal:where(.mod-settings, .mod-community-theme)`） | 直接 |
| `editor.background` | `#fafafaff` | `#282c33ff` | `--setting-items-background`、`--background-modifier-form-field`（`.modal:where(.mod-settings, .mod-community-theme)`） | 近似或借用 |
| `editor.background` | `#fafafaff` | `#282c33ff` | 设置内容区的 `--settings-background` 与 `.vertical-tab-content` 底色 | 近似或借用 |
| `panel.background` | `#ebebecff` | `#2f343eff` | 设置导航的 `--modal-sidebar-background` | 直接 |
| `surface.background` | `#ebebecff` | `#2f343eff` | 设置分组的 `--setting-items-background` | 近似或借用 |
| `editor.background` | `#fafafaff` | `#282c33ff` | 设置内普通控件的 `--interactive-normal`（`.modal.mod-settings`） | 近似或借用 |
| `border` | `#c9c9caff` | `#464b57ff` | `--setting-items-border-color`（`.modal:where(.mod-settings, .mod-community-theme)`） | 近似或借用 |
| `border.variant` | `#dfdfe0ff` | `#363c46ff` | `--setting-items-divider-color`（`.modal:where(.mod-settings, .mod-community-theme)`） | 近似或借用 |
| `text` | `#242529ff` | `#dce0e5ff` | `--setting-group-heading-color`、`--setting-item-name-color`（`.modal:where(.mod-settings, .mod-community-theme)`） | 近似或借用 |
| `element.hover` | `#dfdfe0ff` | `#363c46ff` | `--background-modifier-form-field-hover`（`.modal:where(.mod-settings, .mod-community-theme)`） | 近似或借用 |
| `element.selected` | `#cacacaff` | `#454a56ff` | `--background-modifier-hover`（`.modal.mod-settings .vertical-tab-nav-item.is-active`） | 近似或借用 |
| `text` | `#242529ff` | `#dce0e5ff` | `--text-muted`（`.modal.mod-settings .vertical-tab-nav-item.is-active`） | 直接 |
| `icon.accent` | `#5c78e2ff` | `#74ade8ff` | `--icon-color`（`.modal.mod-settings .vertical-tab-nav-item.is-active`） | 直接 |
| `panel.background` | `#ebebecff` | `#2f343eff` | `background-color`（`.modal.mod-community-theme .modal-sidebar`） | 近似或借用 |
| `border.variant` | `#dfdfe0ff` | `#363c46ff` | `border-color`（`.modal.mod-community-theme .modal-sidebar`） | 近似或借用 |
| `text.disabled` | `#7e8086ff` | `#878a98ff` | `color`（`.markdown-source-view :is(input, textarea):disabled`） | 近似或借用 |
| `search.match_background` | `#5c79e266` | `#74ade866` | `--highlight-background`（`.search-result-file-matched-text`） | 近似或借用 |
| `search.active_match_background` | `#d0a92366` | `#e8af7466` | `background-color`（`.markdown-source-view.mod-cm6 .obsidian-search-match-highlight`） | 近似或借用 |

### Markdown 和 Properties

编辑与阅读共用 Markdown 局部映射。标题与文字强调沿用正文色，保持宿主字体层级。引用、表头和交替行借用次级表面。任务勾选借用成功色，普通输入复选框仍沿用宿主交互色。未解析链接保留原有透明度。数学公式继承上游嵌入式内容色。

| Zed 原始键 | One Light | One Dark | Obsidian 入口 | 关系 |
| --- | --- | --- | --- | --- |
| `text` | `#242529ff` | `#dce0e5ff` | `--h1-color`、`--h2-color`、`--h3-color`、`--h4-color`、`--h5-color`、`--h6-color`、`--inline-title-color`、`--bold-color`、`--italic-color`、`--table-text-color`、`--table-header-color`、`--metadata-label-text-color-hover`、`--metadata-input-text-color`（`Markdown 视图`） | 近似或借用 |
| `search.active_match_background` | `#d0a92366` | `#e8af7466` | `--text-highlight-bg`（`Markdown 视图`） | 近似或借用 |
| `var(--text-highlight-bg)` | 继承 | 继承 | `--highlight-background`（`Markdown 视图`） | 近似或借用 |
| `error.background` | `#fbdfd9ff` | `#d072771a` | `--highlight-background-red`（`Markdown 视图`） | 近似或借用 |
| `modified.background` | `#faf2e6ff` | `#dec1841a` | `--highlight-background-orange`（`Markdown 视图`） | 近似或借用 |
| `warning.background` | `#faf2e6ff` | `#dec1841a` | `--highlight-background-yellow`（`Markdown 视图`） | 近似或借用 |
| `success.background` | `#dfeadbff` | `#a1c1811a` | `--highlight-background-green`（`Markdown 视图`） | 近似或借用 |
| `info.background` | `#e2e2faff` | `#74ade81a` | `--highlight-background-blue`（`Markdown 视图`） | 近似或借用 |
| `hint.background` | `#e2e2faff` | `#5a6f891a` | `--highlight-background-purple`（`Markdown 视图`） | 近似或借用 |
| `text.muted` | `#58585aff` | `#a9afbcff` | `--blockquote-color`、`--list-marker-color-hover`、`--checklist-done-color`、`--metadata-label-text-color`（`Markdown 视图`） | 近似或借用 |
| `border.variant` | `#dfdfe0ff` | `#363c46ff` | `--blockquote-border-color`、`--table-header-border-color`、`--tag-border-color`、`--tag-border-color-hover`、`--metadata-border-color`、`--metadata-divider-color`（`Markdown 视图`） | 近似或借用 |
| `surface.background` | `#ebebecff` | `#2f343eff` | `--blockquote-background-color`、`--table-header-background`、`--table-row-alt-background`（`Markdown 视图`） | 近似或借用 |
| `border` | `#c9c9caff` | `#464b57ff` | `--hr-color`、`--checkbox-border-color`、`--table-border-color`、`--metadata-divider-color-hover`（`Markdown 视图`） | 近似或借用 |
| `syntax.punctuation.list_marker` | `#d3604fff` | `#d07277ff` | `--list-marker-color`（`Markdown 视图`） | 近似或借用 |
| `text.accent` | `#5c78e2ff` | `#74ade8ff` | `--list-marker-color-collapsed`（`Markdown 视图`） | 近似或借用 |
| `border.focused` | `#7d82e8ff` | `#47679eff` | `--checkbox-border-color-hover`、`--metadata-divider-color-focus`（`Markdown 视图`） | 近似或借用 |
| `success` | `#669f59ff` | `#a1c181ff` | `--checkbox-color`（`Markdown 视图`） | 近似或借用 |
| `terminal.ansi.bright_green` | `#3f953aff` | `#AAD581ff` | `--checkbox-color-hover`（`Markdown 视图`） | 近似或借用 |
| `editor.background` | `#fafafaff` | `#282c33ff` | `--checkbox-marker-color`、`--table-background`（`Markdown 视图`） | 近似或借用 |
| `ghost_element.hover` | `#dfdfe0ff` | `#363c46ff` | `--table-row-alt-background-hover`、`--table-row-background-hover`、`--table-header-background-hover`、`--metadata-property-background-hover`、`--metadata-input-background-hover`（`Markdown 视图`） | 近似或借用 |
| `border.selected` | `#cbcdf6ff` | `#293b5bff` | `--table-selection-border-color`（`Markdown 视图`） | 近似或借用 |
| `text.placeholder` | `#7e8086ff` | `#878a98ff` | `--link-unresolved-color`、`--link-unresolved-decoration-color`（`Markdown 视图`） | 近似或借用 |
| `editor.document_highlight.read_background` | `#5c78e225` | `#74ade81a` | `--tag-background`、`--tag-background-hover`（`Markdown 视图`） | 近似或借用 |
| `element.active` | `#cacacaff` | `#454a56ff` | `--metadata-label-background-active`、`--metadata-property-background-active`、`--metadata-input-background-active`（`Markdown 视图`） | 近似或借用 |
| `editor.line_number` | `#b4b4bb` | `#4e5a5f` | `color`（`.markdown-source-view :where(.cm-lineNumbers) .cm-gutterElement`） | 近似或借用 |
| `editor.active_line_number` | `#44454b` | `#d0d4da` | `color`（`.markdown-source-view :where(.cm-lineNumbers) .cm-gutterElement.cm-active`） | 近似或借用 |
| `editor.hover_line_number` | `#61616b` | `#acb0b4` | `color`（`.markdown-source-view :where(.cm-lineNumbers) .cm-gutterElement:hover`） | 近似或借用 |
| `editor.highlighted_line.background` | `#ebebecff` | `#2f343eff` | `--highlight-background`（`.markdown-source-view :where(.is-flashing), .markdown-rendered :where(.is-flashing)`） | 近似或借用 |
| `syntax.embedded` | `#242529ff` | `#dce0e5ff` | `color`（`:where(.markdown-source-view, .markdown-rendered) :is(.math, .cm-math)`） | 近似或借用 |

### Callout 与内置绘图

Callout 用 One 的信息、成功、警示和其他颜色标识原生类型。图表使用现有表面、文本和语义状态为其分别填色，没有定义第二套图表色板。Canvas 的六个槽保持 Obsidian 原编号。图表自定义色和本身的混色归宿主。

| Zed 原始键 | One Light | One Dark | Obsidian 入口 | 关系 |
| --- | --- | --- | --- | --- |
| `text.accent` | `#5c78e2ff` | `#74ade8ff` | `--callout-default`、`--callout-todo`、`--graph-node-focused`、`--mermaid-accent`、`--mermaid-color-1` | 近似或借用 |
| `info` | `#5c78e2ff` | `#74ade8ff` | `--callout-info`、`--callout-summary`、`--graph-node-attachment` | 近似或借用 |
| `syntax.type` | `#3882b7ff` | `#6eb4bfff` | `--callout-tip`、`--canvas-color-5`、`--mermaid-color-5` | 近似或借用 |
| `syntax.keyword` | `#a449abff` | `#b477cfff` | `--callout-important`、`--callout-example`、`--canvas-color-6`、`--mermaid-color-7` | 近似或借用 |
| `success` | `#669f59ff` | `#a1c181ff` | `--callout-success`、`--graph-node-tag`、`--canvas-color-4`、`--mermaid-color-3` | 近似或借用 |
| `warning` | `#a48819ff` | `#dec184ff` | `--callout-question`、`--callout-warning`、`--canvas-color-3`、`--mermaid-color-6` | 近似或借用 |
| `error` | `#d36151ff` | `#d07277ff` | `--callout-error`、`--callout-fail`、`--callout-bug`、`--canvas-color-1`、`--mermaid-error`、`--mermaid-critical`、`--mermaid-color-4` | 近似或借用 |
| `text.muted` | `#58585aff` | `#a9afbcff` | `--callout-quote`、`--graph-node`、`--canvas-card-label-color`、`--mermaid-muted-color`、`--mermaid-line-color` | 近似或借用 |
| `text.placeholder` | `#7e8086ff` | `#878a98ff` | `--graph-node-unresolved` | 近似或借用 |
| `border` | `#c9c9caff` | `#464b57ff` | `--graph-line`、`--mermaid-border-color` | 近似或借用 |
| `text` | `#242529ff` | `#dce0e5ff` | `--graph-text`、`--mermaid-text-color` | 近似或借用 |
| `editor.background` | `#fafafaff` | `#282c33ff` | `--canvas-background`、`--mermaid-background` | 近似或借用 |
| `border.variant` | `#dfdfe0ff` | `#363c46ff` | `--canvas-dot-pattern` | 近似或借用 |
| `syntax.number` | `#ad6e25ff` | `#bf956aff` | `--canvas-color-2`、`--mermaid-color-2` | 近似或借用 |
| `surface.background` | `#ebebecff` | `#2f343eff` | `--mermaid-surface` | 近似或借用 |
| `elevated_surface.background` | `#ebebecff` | `#2f343eff` | `--mermaid-surface-alt` | 近似或借用 |
| `terminal.ansi.bright_red` | `#de3e35ff` | `#EA858Bff` | `--mermaid-color-8` | 近似或借用 |
| `border` | `#c9c9caff` | `#464b57ff` | `--canvas-color`（`.canvas-wrapper`） | 近似或借用 |

### 两种视图共用的代码入口

普通代码用 Zed 编辑器前景。围栏底色借用次级表面。正文行内代码使用 Zed 的 `text.literal`。表格单元格内的行内代码回到 `editor.foreground`，由单元格行底色透出，避免奇偶行有的显示色块、有的融入底色。用原生等宽字区分代码。

| Zed 原始键 | One Light | One Dark | Obsidian 入口 | 关系 |
| --- | --- | --- | --- | --- |
| `surface.background` | `#ebebecff` | `#2f343eff` | `--code-background`（`Markdown 视图`） | 近似或借用 |
| `border` | `#c9c9caff` | `#464b57ff` | `--code-border-color`（`Markdown 视图`） | 近似或借用 |
| `editor.foreground` | `#242529ff` | `#acb2beff` | `--code-normal`（`Markdown 视图`） | 直接 |
| `syntax.comment` | `#a2a3a7ff` | `#5d636fff` | `--code-comment`（`Markdown 视图`） | 直接 |
| `syntax.function` | `#5b79e3ff` | `#73ade9ff` | `--code-function`（`Markdown 视图`） | 直接 |
| `syntax.string.regex` | `#ad6e26ff` | `#bf956aff` | `--code-important`（`Markdown 视图`） | 近似或借用 |
| `syntax.keyword` | `#a449abff` | `#b477cfff` | `--code-keyword`（`Markdown 视图`） | 直接 |
| `syntax.operator` | `#3882b7ff` | `#6eb4bfff` | `--code-operator`（`Markdown 视图`） | 直接 |
| `syntax.property` | `#d3604fff` | `#d07277ff` | `--code-property`（`Markdown 视图`） | 直接 |
| `syntax.punctuation` | `#242529ff` | `#acb2beff` | `--code-punctuation`（`Markdown 视图`） | 直接 |
| `syntax.string` | `#649f57ff` | `#a1c181ff` | `--code-string`（`Markdown 视图`） | 直接 |
| `syntax.tag` | `#5c78e2ff` | `#74ade8ff` | `--code-tag`（`Markdown 视图`） | 直接 |
| `syntax.number` | `#ad6e25ff` | `#bf956aff` | `--code-value`（`Markdown 视图`） | 直接 |
| `syntax.text.literal` | `#649f57ff` | `#a1c181ff` | `--code-normal`（`.markdown-source-view span.cm-inline-code:where(:not(.cm-hmd-codeblock)), .markdown-rendered :not(pre) > code`） | 直接 |
| `ghost_element.background` | `#00000000` | `#00000000` | 表格行内代码的 `--code-background` | 近似或借用 |
| `editor.foreground` | `#242529ff` | `#acb2beff` | 表格行内代码的 `--code-normal` | 近似或借用 |

### CodeMirror 围栏

具有独立类别的宿主 token 对应上游语法类别。定义类复用了函数色，类名和函数声明的多义归属由宿主决定。若 Python 的 True 与关键字共用类，沿用关键字色。编辑器的 CSS 类选择器可通过 .cm-qualifier 着色。ID、伪类和构造函数复用其它语法类时保留宿主颗粒度。

| Zed 原始键 | One Light | One Dark | Obsidian 入口 | 关系 |
| --- | --- | --- | --- | --- |
| `syntax.function` | `#5b79e3ff` | `#73ade9ff` | `color`（`.markdown-source-view .cm-hmd-codeblock.cm-def`） | 近似或借用 |
| `syntax.type` | `#3882b7ff` | `#6eb4bfff` | `color`（`.markdown-source-view .cm-hmd-codeblock.cm-type`） | 直接 |
| `syntax.attribute` | `#5c78e2ff` | `#74ade8ff` | `color`（`.markdown-source-view .cm-hmd-codeblock.cm-attribute`） | 直接 |
| `syntax.property` | `#d3604fff` | `#d07277ff` | `color`（`.markdown-source-view .cm-hmd-codeblock.cm-property`） | 直接 |
| `syntax.variable` | `#242529ff` | `#acb2beff` | `color`（`.markdown-source-view .cm-hmd-codeblock.cm-variable`） | 直接 |
| `syntax.boolean` | `#ad6e25ff` | `#bf956aff` | `color`（`.markdown-source-view .cm-hmd-codeblock.cm-atom`） | 直接 |
| `syntax.punctuation.bracket` | `#4d4f52ff` | `#b2b9c6ff` | `color`（`.markdown-source-view .cm-hmd-codeblock.cm-bracket`） | 直接 |
| `syntax.selector` | `#669f59ff` | `#dfc184ff` | `color`（`.markdown-source-view .cm-hmd-codeblock.cm-qualifier`） | 直接 |
| `syntax.diff.plus` | `#50a14fff` | `#98c379ff` | `color`（`.markdown-source-view .cm-hmd-codeblock.cm-positive`） | 直接 |
| `syntax.diff.minus` | `#e45649ff` | `#e06c75ff` | `color`（`.markdown-source-view .cm-hmd-codeblock.cm-negative`） | 直接 |
| `syntax.title` | `#d3604fff` | `#d07277ff` | `color`（`.markdown-source-view .cm-hmd-codeblock.cm-header`） | 直接 |
| `syntax.emphasis` | `#5c78e2ff` | `#74ade8ff` | `color`（`.markdown-source-view .cm-hmd-codeblock.cm-em`） | 直接 |
| `syntax.emphasis.strong` | `#ad6e25ff` | `#bf956aff` | `color`（`.markdown-source-view .cm-hmd-codeblock.cm-strong`） | 直接 |

### Prism 围栏

只细分原生 token。属性值使用字符串色。class-name 归入类型，包括构造调用目标，Bash 的内置命令跳过该映射。CSS 伪类优先于父选择器。正则、Diff、布尔和属性语言差异依实际渲染标记。

| Zed 原始键 | One Light | One Dark | Obsidian 入口 | 关系 |
| --- | --- | --- | --- | --- |
| `syntax.boolean` | `#ad6e25ff` | `#bf956aff` | `color`（`.markdown-rendered pre code .token.boolean`） | 直接 |
| `syntax.constant` | `#c18401ff` | `#dfc184ff` | `color`（`.markdown-rendered pre code .token.constant`） | 直接 |
| `syntax.attribute` | `#5c78e2ff` | `#74ade8ff` | `color`（`.markdown-rendered pre code .token.attr-name`） | 直接 |
| `syntax.string` | `#649f57ff` | `#a1c181ff` | `color`（`.markdown-rendered pre code .token.attr-value`） | 直接 |
| `syntax.type` | `#3882b7ff` | `#6eb4bfff` | `color`（`.markdown-rendered pre code .token.class-name:where(:not(.builtin)), .markdown-rendered pre code.language-typescript .token.builtin`） | 直接 |
| `syntax.property` | `#d3604fff` | `#d07277ff` | `color`（`.markdown-rendered pre code .token.property-access:where(:not(.function))`） | 直接 |
| `syntax.variable.parameter` | `#d3604fff` | `#d07277ff` | `color`（`.markdown-rendered pre code .token.parameter`） | 直接 |
| `syntax.variable` | `#242529ff` | `#acb2beff` | `color`（`.markdown-rendered pre code .token.variable`） | 直接 |
| `syntax.selector` | `#669f59ff` | `#dfc184ff` | `color`（`.markdown-rendered pre code.language-css .token.selector`） | 直接 |
| `syntax.selector.pseudo` | `#5c78e2ff` | `#74ade8ff` | `color`（`.markdown-rendered pre code.language-css .token.pseudo-class`） | 直接 |
| `syntax.diff.plus` | `#50a14fff` | `#98c379ff` | `color`（`.markdown-rendered pre code .token.inserted`） | 直接 |
| `syntax.diff.minus` | `#e45649ff` | `#e06c75ff` | `color`（`.markdown-rendered pre code .token.deleted`） | 直接 |
| `syntax.title` | `#d3604fff` | `#d07277ff` | `color`（`.markdown-rendered pre code.language-markdown .token.title`） | 直接 |
| `syntax.emphasis` | `#5c78e2ff` | `#74ade8ff` | `color`（`.markdown-rendered pre code.language-markdown .token.italic`） | 直接 |
| `syntax.emphasis.strong` | `#ad6e25ff` | `#bf956aff` | `color`（`.markdown-rendered pre code.language-markdown .token.bold`） | 直接 |
