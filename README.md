# Yifan Ju's Personal LaTeX Template

## 快速开始

### 1. 复制模板
```bash
cp template.tex my-homework.tex
```

### 2. 编辑模板（填写信息）
打开 `my-homework.tex`，在空括号中填入内容。

### 3. 编译
```bash
xelatex -output-directory=out my-homework.tex
```

---

## 主要功能

### 页面模式（2 选 1）
```latex
\setTitleLayoutMode{coveronly}   % 仅封面，content 单独另起一页
\setTitleLayoutMode{titleonly}   % 仅标题，无 content
```

### 封面页配置
```latex
\setCoverSeasonYear{学期}
\setCoverTitle{标题}
\setCoverCourse{课程代码}

\setCoverFieldsNumber{n}         % 1-5 个字段
\setCoverFieldOne{标签}{内容}
\setCoverFieldTwo{标签}{内容}
```

### 封面页图片设置
```latex
% 所有图片都在 graph/coverage and title/ 文件夹中
% 只需提供文件名即可

\setSchoolLogo{文件名.png}       % 校徽（默认 UTSC.png）
\setSchoolLogoScale{0.15}        % 校徽缩放比例

\setSignatureImage{文件名.png}   % 签名图片
\setSignatureScale{0.03}         % 签名缩放比例
```

### 标题页配置
```latex
\setDocTitle{标题}
\setDocAuthor{作者}
\setDocDate{日期}

\setTitleFieldsNumber{n}         % 0-5 个额外字段
\setTitleFieldOne{标签}{内容}
\setTitleFieldTwo{标签}{内容}
```

### 页眉设置
```latex
\setHeaderLeft{左}
\setHeaderCenter{中}
\setHeaderRight{右}
\setupHeaderStyle
```

---

## 代码块环境

模板支持在文档中插入各种编程语言的代码，具有行号显示和黑白纯文本格式。

### 使用方法

将代码存储在 `code/` 目录下，然后使用 `\inputcode` 命令引入：

```latex
\inputcode{python}{./code/hello_world.py}
```

**优点：**
- ✓ 代码缩进和格式永远不会被 LaTeX 格式化工具破坏
- ✓ 代码可单独维护，便于测试和复用
- ✓ 文档更清晰，代码更易修改
- ✓ 黑白纯文本，打印友好

### 支持的语言

以下是 listings 包原生支持的常见编程语言：

| 语言    | 代码      | 语言   | 代码   |
| ------- | --------- | ------ | ------ |
| Python  | `python`  | Java   | `java` |
| C       | `c`       | Racket | `lisp` |
| Haskell | `haskell` | SQL    | `sql`  |
| Prolog  | `prolog`  | HTML   | `html` |
| XML     | `xml`     | Bash   | `bash` |
| R       | `r`       | Ruby   | `ruby` |

### 纯文本模式

如果不指定语言，使用空的大括号表示纯文本模式（适合伪代码）：

```latex
\inputcode{}{./code/pseudocode.txt}
```

### 代码块的外观特性

- **行号**：代码块左侧自动显示行号（从 0 开始）
- **框线**：代码块用阴影框显示
- **换行**：长代码自动换行
- **缩进**：完全保留原始缩进

---

## 数学环境

模板提供多种数学陈述环境：`theorem` | `lemma` | `claim` | `proposition` | `definition`

**环境说明**：
- **Theorem**：主要定理，重要结论
- **Lemma**：辅助引理，用于证明其他结论
- **Claim**：临时小台阶，用于逐步推导或中间步骤
- **Proposition**：个人结论或观察
- **Definition**：术语、概念或对象的正式定义

支持编号版本和非编号版本（加星号 `*`）。

**证明结束符号**：
- Theorem / Proposition 用 ∎（黑方块）
- Lemma / Claim 用 □（空心方块）
- Definition 无证明结束符号

另提供 `solution` 环境用于解答（支持编号和非编号版本）。

---

## 文件说明

| 文件                             | 说明                 |
| -------------------------------- | -------------------- |
| `template.tex`                   | 📄 空模板（直接使用） |
| `minimal-example.tex`            | 📝 最小完整示例       |
| `Yifan_Ju_Personal_Template.sty` | ⚙️ 核心引擎           |

---

## 常见用法

**仅封面 + 3 个字段：**
```latex
\setTitleLayoutMode{coveronly}
\setCoverFieldsNumber{3}
\setCoverFieldOne{...}{...}
\setCoverFieldTwo{...}{...}
\setCoverFieldThree{...}{...}
```

**标题 + 2 个额外字段：**
```latex
\setTitleLayoutMode{titleonly}
\setTitleFieldsNumber{2}
\setTitleFieldOne{...}{...}
\setTitleFieldTwo{...}{...}
```

---
详细的使用示例请查看 `minimal-example.tex`。