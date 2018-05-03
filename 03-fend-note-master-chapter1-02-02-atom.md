# Atom 文本编辑器


本文即为在 **Atom** 下编写完成，在写作过程中让我对这个崭新的 1.0 版本文本编辑器
有了更多的了解。
在阅读本文时注意快捷键于后面英文单词的对应可帮助记忆，在使用中忘记的快捷键以可以通过使用
**查询面板**（后面会提到）进行查询。
如果你在使用过程中发现了异常和错误可以到 **Atom** 所在的
GitHub 仓库提交问题报告。同一款编辑器一同成长，愿力量与你同在！
下面的快捷键均为 **Mac OS X** 默认设置。如你用的是 Windows 或者是 Linux，可能需要尝试将
所有提到的 <kbd>cmd</kbd> 改为 <kbd>ctrl</kbd>。

#### 基础中的基础

开始之前先把下面这条快捷键记住。<kbd>cmd</kbd>+<kbd>shift</kbd>+<kbd>P</kbd>
它会打开类似 Alfred 的快捷功能选择窗口，
如果你从来没有听过 Alfred（此为 Mac OS X 特有应用） 那你应该赶紧去所搜引擎中找找了。

**保存时间**

|快捷键|描述|
|-----|----|
|`cmd-shift-S`|可以另存为 "Save As"|
|`cmd-alt-S`|可以保存全部的 "Save All".|

**打开文件与目录**

如果在命令行环境中可以使用下面的方法一次打开多个目录。

```bash
# 打开目录
atom ./hopes ./dreams

# 获得帮助
atom -h
```

|快捷键|描述|
|-----|----|
|`cmd-O`|打开文件|
|`cmd-shift-O`|添加目录至当前编辑器窗口|

`cmd-P` 可以打开 Fuzzy Finder 进行模糊搜索，默认可所搜区域为项目内所有文件。
下面的命令可以对模糊所搜做一些限制，`cmd-B` 只所搜已打开的文件（存在与 Buffer 中的文件）。
`cmd-shift-B`

1.0 版本中在编辑器中添加的新文件无法使用 Fuzzy Finder（模糊寻找） 找到，重启后则可以解决。

**边栏（树目录）**

|快捷键|描述|
|-----|----|
|`cmd-\`|显示或隐藏边栏|
|`ctrl-0`|聚焦边栏，聚焦后可以操作树目录中的文件|

在聚焦后可以通过 `a` 来增加（add），`m` 来移动（move），`d` 来复制（duplicate）或者
`delete` 来删除（此处为键盘删除键）。
这里的操作并没有自动路径补全功能，之后可能需要插件支持。

#### 开始使用

**Atom** 中几乎所有的功能都是以插件的形式存在的。所有如何安装插件则就是我们第一件要做的事。
除了图形界面安装的方法外，随 **Atom** 还安装了插件管理器叫做 `apm` 。通过它也可以直接安装
和更新插件。简单说主题也是插件，所以安装主题与安装插件的步骤类似。

*下面的操作均需要联网*

```
# 安装插件
apm install <package_name>

# 安装指定版本的插件
apm install <package_name>@<package_version>

# 查询插件
apm search <package_name>

# 查询插件详情
apm view <package_name>
```

##### 移动光标

**Atom** 的移动快方法同 **Emacs** 一致。在熟悉使用 **Atom** 后也很容易的转移至
**Emacs** 的环境下熟练工作。

单个字符的移动，效果于方向键一致。

|快捷键|描述|
|-----|----|
|`ctrl-P`|上移（Previous）|
|`ctrl-N`|下移（Next）|
|`ctrl-B`|后移（Back）|
|`ctrl-F`|前移（Forward）|

在单个字符移动基础上，可以延展至更大范围的移动。例如，单词，整行。

|快捷键|描述|
|-----|----|
|`alt-B`|向后以词为单位移动（英文），中文则以英文标点为间隔|
|`alt-F`|向前以词为单位移动（英文），中文则以英文标点为间隔|
|`ctrl-E`|移动至行末（End）|
|`ctrl-A`|移动至此行首字符（Ahead)|
|`ctrl-A`（敲击两次）|移动至此行行首（包括空格）|
|`cmd-up`|移动至文件最顶|
|`cmd-down`|移动至文件最低|

`ctrl-G` 加数字可移动至**目标行**，使用 `row:column` 可以定位行数和列数，
使用这个方法在查找错误时变得十分方便。

`cmd-R` 可以**在当前文件中**（Buffer）按照符号来搜索，符号关键字指的是函数名（代码中）
或标题（文档中）。

<!-- TODO: Add Generate ctags and Fuzzy Finder for entire project -->
<!-- TODO: Add the usage of `ctrl-shift-R` for project width search -->
<!-- https://atom.io/docs/v1.0.0/using-atom-moving-in-atom#navigating-by-symbols -->

##### 选择

选择是在移动的基础上加入 `shift` 既可完成。特别的几种选择方法如下。

|快捷键|描述|
|-----|----|
|`cmd-L`|选取整行|
|`ctrl-shift-W`|选取当前单词（英文），中文则为整行|

##### 编辑与删除

**Atom** 如同其他的常用的文本编辑器一样可以直接编辑文字，并不存在特殊的模式。但了解下面的
编辑技巧可以让你使用 **Atom** 更得心应手。

**编辑操作**

|快捷键|描述|
|-----|----|
|`ctrl-T`|交换光标两边的字符（Transpose）|
|`ctrl-J`|将下一行同当前行合并（Join）|
|`ctrl-cmd-up`|向上冒泡当前行|
|`ctrl-cmd-down`|向下冒泡当前行|
|`cmd-shift-D`|复制当前行（Duplicate）|
|`cmd-K, cmd-U`|转换选中字符至全大写|
|`cmd-K, cmd-L`|转换选中字符至全小|

<!-- TODO: re-flow selected paragraph to hard-wrap at given line length -->
<!-- TODO: cmd-alt-Q -->

**删除操作**

|快捷键|描述|
|-----|----|
|`ctrl-shift-K`|删除当前（Cut）|
|`cmd-delete`|删除此行光标后全部字符|
|`cmd-backspace`|删除至当前行首|
|`ctrl-K`|切帖至行末（Cut）|
|`alt-H`|删除前一个字符|
|`alt-D`|删除后一个字符|

**多个光标及选择**

同 **Sublime Text** 相同，**Atom** 也同样有多光标的实现。
按住<kbd>cmd</kbd>可以在文本中使用进行区域性选择。

|快捷键|描述|
|-----|----|
|`cmd-click`|在点击处增加新光标|
|`cmd-shift-L`|将选择区域转换为多光标|
|`ctrl-shift-up`|在上一行增加新光标|
|`ctrl-shift-down`|在下一行增加新光标|
|`cmd-D`|选择下一个于当前被选字符相同的字符并添加新光标|
|`cmd-ctrl-G`|选择全部于当前选中字符相同的字符并添加光标|

##### 括号

编程中最常打交道和需要跳出的莫属于括号和引号了。**Atom** 对于括号有很好的处理办法，
各种括号在光标内移动都会被自动高亮（引号和 HTML 中的标签也会被高亮和自动补全）。
选中内容后使用括号可以自动将选中内容包含在括号或引号内。

|快捷键|描述|
|-----|----|
|`ctrl-M`|跳至最近的一个括号的起始位置|
|`ctrl-cmd-M`|选中括号内的所有内容|
|`alt-cmd-.`|关闭最近的一个 XML/HTML 标签|

##### 搜索与替换

|快捷键|描述|
|-----|----|
|`cmd-F`|当前文本中搜索|
|`cmd-shift-F`|搜索整个项目|
|`cmd-G`|找到下一个匹配的搜索结果|
|`cmd-G-shift`|找到上一个匹配的搜索结果|

在项目搜索中可以使用 wildcard 和指定目标的搜索路径。

##### 代码片段（Snippets）

代码片段让你在写代码时有飞一般的感觉，代码片段会将预先设置好的代码片段替换在当前文本中，
并且设置焦点并用 <kbd>tab</kbd> 聚焦下一个焦点，
或 <kbd>shift</kbd> + <kbd>tab</kbd> 聚焦上一个焦点。

所有的代码片都存储在下面的目录中 `~/.atom/snippets.cson`，
你可以通过 Open Your Snippets Menu 打开此文件。

|快捷键|描述|
|-----|----|
|`alt-shift-S`|显示当前文件类型下的全部代码片段|

当然制作代码片也有一个代码片，它就是 `snip` 。

###### 制作代码片段

下面是一个简单的代码片样例。

```javascript
'.source.js':
  'console.log':
    'prefix': 'log'
    'body': 'console.log(${1: "crash"});$2'
```

- `.source.js` 为代码片可用的文件类型范围
- `console.log` 为代码片内容描述
- `prefix` 为代码片调用字符
- `body` 代码片主体内容
- `${1:'crash'}` 用于定义焦点，顺序及其默认值

多行代码代码片

```javascript
'.source.js':
  'if, else if, else':
    'prefix': 'ieie'
    'body': """
      if (${1:true}) {
        $2
      } else if (${3:false}) {
        $4
      } else {
        $5
      }
    """
```

<!-- TODO: 解决实现代码片中存在的问题 -->

##### 代码折叠

可以点击代码行号边的箭头折叠当前层级的代码。

|快捷键|描述|
|-----|----|
|`alt-cmd-[`|折叠当前层级|
|`alt-cmd-]`|展开当前层级|
|`alt-cmd-shift-{`|折叠全部层级|
|`alt-cmd-shift-}`|展开全部层级|
|`cmd-K, cmd-N`（层级数）|根据层级级别折叠|

##### 多窗口模式

任意一个窗口都可以无需的四面分割，分割的部分则依然使用标签来表示。

|快捷键|描述|
|-----|----|
|`cmd-k arrow`|根据方向指定分割窗口|
|`cmd-K, cmd-arrow`|聚焦指定方向的窗口|

<!-- TODO: 分离窗口快捷键无效 -->

##### 解码（Encoding）

**Atom** 支持多种解码格式（包括中文 GBK 的支持），也可自动识别解码方式
（不能识别时则默认为 UTF-8）。当然你也可以使用这种方法将多种文本在多种解码格式直接转换。

|快捷键|描述|
|-----|----|
|`ctrl-shift-U`|切换解码方式|

##### 书签

在 **Atom** 添加书签就如同你看书的时添加书签一样，它使你在书写代码时可以自如的跳转到你需要的
位置。

|快捷键|描述|
|-----|----|
|`F2-cmd`|可以在当前行切换标记书签|
|`F2`|跳转至下一个书签|
|`F2-shift`|跳转至上一个书签|
|`F2-ctrl`|查看全部的书签|
|`F2-cmd-shift`|清除全部标签|

##### 扩展插件

下面列出了笔者在日常 Web 开发中所易用的插件，这些插件满足了超过百分之九十笔者的开发需求。下面的这些插件均可以在官方插件管理器中进行下载和安装。

```javascript
[
	{
		"name": "advanced-new-file",
		"version": "0.4.3"
	},
	{
		"name": "advanced-open-file",
		"version": "0.8.2"
	},
	{
		"name": "atom-beautify",
		"version": "0.28.8"
	},
	{
		"name": "AtomicChar",
		"version": "0.3.8"
	},
	{
		"name": "autocomplete-paths",
		"version": "1.0.2"
	},
	{
		"name": "docblockr",
		"version": "0.7.3"
	},
	{
		"name": "ex-mode",
		"version": "0.7.0"
	},
	{
		"name": "file-icons",
		"version": "1.6.2"
	},
	{
		"name": "language-jade",
		"version": "0.6.2"
	},
	{
		"name": "linter",
		"version": "1.3.0"
	},
	{
		"name": "linter-jshint",
		"version": "1.1.4"
	},
	{
		"name": "markdown-toc",
		"version": "0.3.0"
	},
	{
		"name": "merge-conflicts",
		"version": "1.3.5"
	},
	{
		"name": "minimap",
		"version": "4.12.2"
	},
	{
		"name": "minimap-linter",
		"version": "1.0.0"
	},
	{
		"name": "open-in-browser",
		"version": "0.4.6"
	},
	{
		"name": "pigments",
		"version": "0.9.3"
	},
	{
		"name": "sort-lines",
		"version": "0.11.0"
	},
	{
		"name": "sync-settings",
		"version": "0.6.0"
	},
	{
		"name": "tab-switcher",
		"version": "1.2.1"
	},
	{
		"name": "theme-switcher",
		"version": "1.1.0"
	},
	{
		"name": "vim-mode",
		"version": "0.57.0"
	},
	{
		"name": "atom-dark-syntax",
		"version": "0.27.0",
		"theme": "syntax"
	},
	{
		"name": "atom-dark-ui",
		"version": "0.49.0",
		"theme": "ui"
	},
	{
		"name": "atom-light-syntax",
		"version": "0.28.0",
		"theme": "syntax"
	},
	{
		"name": "atom-light-ui",
		"version": "0.41.0",
		"theme": "ui"
	},
	{
		"name": "base16-tomorrow-dark-theme",
		"version": "0.26.0",
		"theme": "syntax"
	},
	{
		"name": "base16-tomorrow-light-theme",
		"version": "0.9.0",
		"theme": "syntax"
	},
	{
		"name": "one-dark-ui",
		"version": "1.0.2",
		"theme": "ui"
	},
	{
		"name": "one-dark-syntax",
		"version": "1.1.0",
		"theme": "syntax"
	},
	{
		"name": "one-light-syntax",
		"version": "1.1.0",
		"theme": "syntax"
	},
	{
		"name": "one-light-ui",
		"version": "1.0.2",
		"theme": "ui"
	},
	{
		"name": "solarized-dark-syntax",
		"version": "0.38.1",
		"theme": "syntax"
	},
	{
		"name": "solarized-light-syntax",
		"version": "0.22.1",
		"theme": "syntax"
	},
	{
		"name": "about",
		"version": "1.0.1"
	},
	{
		"name": "archive-view",
		"version": "0.58.0"
	},
	{
		"name": "autocomplete-atom-api",
		"version": "0.9.2"
	},
	{
		"name": "autocomplete-css",
		"version": "0.9.0"
	},
	{
		"name": "autocomplete-html",
		"version": "0.7.2"
	},
	{
		"name": "autocomplete-plus",
		"version": "2.19.0"
	},
	{
		"name": "autocomplete-snippets",
		"version": "1.7.1"
	},
	{
		"name": "autoflow",
		"version": "0.25.0"
	},
	{
		"name": "autosave",
		"version": "0.22.0"
	},
	{
		"name": "background-tips",
		"version": "0.25.0"
	},
	{
		"name": "bookmarks",
		"version": "0.35.0"
	},
	{
		"name": "bracket-matcher",
		"version": "0.76.0"
	},
	{
		"name": "command-palette",
		"version": "0.36.0"
	},
	{
		"name": "deprecation-cop",
		"version": "0.53.1"
	},
	{
		"name": "dev-live-reload",
		"version": "0.46.0"
	},
	{
		"name": "encoding-selector",
		"version": "0.21.0"
	},
	{
		"name": "exception-reporting",
		"version": "0.36.0"
	},
	{
		"name": "find-and-replace",
		"version": "0.175.0"
	},
	{
		"name": "fuzzy-finder",
		"version": "0.87.0"
	},
	{
		"name": "git-diff",
		"version": "0.55.0"
	},
	{
		"name": "go-to-line",
		"version": "0.30.0"
	},
	{
		"name": "grammar-selector",
		"version": "0.47.0"
	},
	{
		"name": "image-view",
		"version": "0.54.0"
	},
	{
		"name": "incompatible-packages",
		"version": "0.24.1"
	},
	{
		"name": "keybinding-resolver",
		"version": "0.33.0"
	},
	{
		"name": "link",
		"version": "0.30.0"
	},
	{
		"name": "markdown-preview",
		"version": "0.150.0"
	},
	{
		"name": "metrics",
		"version": "0.51.0"
	},
	{
		"name": "notifications",
		"version": "0.57.0"
	},
	{
		"name": "open-on-github",
		"version": "0.37.0"
	},
	{
		"name": "package-generator",
		"version": "0.40.0"
	},
	{
		"name": "release-notes",
		"version": "0.53.0"
	},
	{
		"name": "settings-view",
		"version": "0.211.2"
	},
	{
		"name": "snippets",
		"version": "0.95.0"
	},
	{
		"name": "spell-check",
		"version": "0.59.0"
	},
	{
		"name": "status-bar",
		"version": "0.75.1"
	},
	{
		"name": "styleguide",
		"version": "0.44.0"
	},
	{
		"name": "symbols-view",
		"version": "0.100.0"
	},
	{
		"name": "tabs",
		"version": "0.82.0"
	},
	{
		"name": "timecop",
		"version": "0.31.0"
	},
	{
		"name": "tree-view",
		"version": "0.180.0"
	},
	{
		"name": "update-package-dependencies",
		"version": "0.10.0"
	},
	{
		"name": "whitespace",
		"version": "0.30.0"
	},
	{
		"name": "wrap-guide",
		"version": "0.35.0"
	},
	{
		"name": "language-c",
		"version": "0.45.0"
	},
	{
		"name": "language-clojure",
		"version": "0.16.0"
	},
	{
		"name": "language-coffee-script",
		"version": "0.41.0"
	},
	{
		"name": "language-csharp",
		"version": "0.6.0"
	},
	{
		"name": "language-css",
		"version": "0.32.1"
	},
	{
		"name": "language-gfm",
		"version": "0.80.0"
	},
	{
		"name": "language-git",
		"version": "0.10.0"
	},
	{
		"name": "language-go",
		"version": "0.31.0"
	},
	{
		"name": "language-html",
		"version": "0.40.0"
	},
	{
		"name": "language-hyperlink",
		"version": "0.14.0"
	},
	{
		"name": "language-java",
		"version": "0.15.0"
	},
	{
		"name": "language-javascript",
		"version": "0.85.0"
	},
	{
		"name": "language-json",
		"version": "0.15.0"
	},
	{
		"name": "language-less",
		"version": "0.28.1"
	},
	{
		"name": "language-make",
		"version": "0.14.0"
	},
	{
		"name": "language-mustache",
		"version": "0.12.0"
	},
	{
		"name": "language-objective-c",
		"version": "0.15.0"
	},
	{
		"name": "language-perl",
		"version": "0.28.0"
	},
	{
		"name": "language-php",
		"version": "0.27.0"
	},
	{
		"name": "language-property-list",
		"version": "0.8.0"
	},
	{
		"name": "language-python",
		"version": "0.38.0"
	},
	{
		"name": "language-ruby",
		"version": "0.57.0"
	},
	{
		"name": "language-ruby-on-rails",
		"version": "0.22.0"
	},
	{
		"name": "language-sass",
		"version": "0.40.0"
	},
	{
		"name": "language-shellscript",
		"version": "0.15.0"
	},
	{
		"name": "language-source",
		"version": "0.9.0"
	},
	{
		"name": "language-sql",
		"version": "0.17.0"
	},
	{
		"name": "language-text",
		"version": "0.7.0"
	},
	{
		"name": "language-todo",
		"version": "0.25.0"
	},
	{
		"name": "language-toml",
		"version": "0.16.0"
	},
	{
		"name": "language-xml",
		"version": "0.30.0"
	},
	{
		"name": "language-yaml",
		"version": "0.22.0"
	}
]
```
