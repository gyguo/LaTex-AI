<h1 align="center">LaTeX-AI</h1>

<table align="center">
  <tr>
    <td align="center" width="300">
      <h2><a href="./README.md">📘 简体中文</a></h2>
      <b>当前版本</b>
    </td>
    <td align="center" width="300">
      <h2><a href="./README_EN.md">🌐 English</a></h2>
      <b>Click to switch</b>
    </td>
  </tr>
</table>

<p align="center">LaTeX 常见编辑器汇总：优缺点及配置教程（TeX Live / VS Code / Overleaf）</p>

---

## 1. VS Code + TeX Live + LaTeX Workshop + AI 辅助（推荐）

### 1.1 安装及配置教程

#### 1.1.1 安装 TeX Live

- 安装参考链接： https://www.bilibili.com/read/cv6966909?from=search
- TeX Live 清华镜像： https://mirrors.tuna.tsinghua.edu.cn/CTAN/systems/texlive/Images/

#### 1.1.2 安装 VS Code

- 安装 LaTeX Workshop 插件

#### 1.1.3 修改 VS Code 的配置文件，设置编译程序

> **！！！简单使用不需要进行下方配置**

详细配置见单独文档：[修改 VS Code 配置文件，设置编译程序](./docs/vscode-latex-tools.md)

#### 1.1.4 预览及同步（LaTeX Workshop 自带，不需要配置）

> **！！！最新版本的 LaTeX Workshop 可以用浏览器作为 PDF 阅读器，并且自带同步功能，不需要额外配置安装**

- 亲测使用 Microsoft Edge 浏览器可以作为 PDF 阅读器。
- LaTeX 到 PDF 前向同步：`Ctrl` + `Alt` + `J`（Mac 上为 `Cmd` + `Option` + `J`）。
- PDF 到 LaTeX 反向同步：`Ctrl` + 鼠标左键（Mac 上为 `Cmd` + 鼠标左键）。

以下是**旧版本**在 Windows 上安装 SumatraPDF 用于预览 PDF 和反向搜索的方法，新版本不需要配置，仅供参考：[Windows 安装 SumatraPDF 用于预览 PDF 和反向搜索](./docs/sumatrapdf-preview.md)

#### 1.1.5 安装 CodeX / GitHub Copilot 等 AI 辅助工具

### 1.2 优缺点

- **优点：** 可以结合多种插件，扩展性比较强。比如可随时同步 GitHub，结合 Overleaf 使用实现在线编辑和本地编辑的同步；或者结合 Zotero 实现参考文献直接插入；可以使用 CodeX、GitHub Copilot 等插件或者本地 Agent 工具实现辅助写作。
- **缺点：** 整体配置比较麻烦（新版本已经大幅度改进）。

## 2. TeX Live + TeXstudio

### 2.1 安装及配置

- 安装参考链接： https://www.bilibili.com/read/cv6966909?from=search
- TeX Live 清华镜像： https://mirrors.tuna.tsinghua.edu.cn/CTAN/systems/texlive/Images/

### 2.2 优缺点

- **优点：** 安装简单，定期更新，功能完善，界面优美。
- **缺点：** 中文支持不好。

## 3. Overleaf 在线版编辑

- 官网： https://www.overleaf.com/

### 3.1 优缺点

- **优点：** 在线编译，不限设备随时查看，支持多人编辑。
- **缺点：** 编译较慢，调试 bug 较难。

## 4. VS Code + GitHub + Overleaf

### 4.1 使用逻辑

- 本地用 VS Code 编写完成后上传到 GitHub，在线用 Overleaf 编辑时通过 GitHub 同步。
- Overleaf 编辑后同步到 GitHub，再通过 GitHub 下载到本地。

### 4.2 安装及配置教程

- 安装配置 VS Code + TeX Live + LaTeX Workshop。
- 从官网下载 Git 安装包 https://git-scm.com/download 然后点击安装。
- 在 Overleaf 中新建 project，将文件同步到 GitHub 上面（新用户需要付费会员）。
- 在 VS Code 左侧打开在 GitHub 中托管的仓库文件夹，用 GitHub 账号登录 VS Code，从 GitHub 克隆到本地。
- 本地修改的文件可以提交到 GitHub 上面，Overleaf 随时可从 GitHub 上同步。

### 4.3 优缺点

- **优点：** 可以轻松实现在线编辑和本地编辑之间的同步。
- **缺点：** 整体流程较多，多人协同时容易覆盖。
