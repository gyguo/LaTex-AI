<h1 align="center">LaTeX-CN</h1>

<table align="center">
  <tr>
    <td align="center" width="300">
      <h2><a href="./README.md">📘 简体中文</a></h2>
      <b>点击切换</b>
    </td>
    <td align="center" width="300">
      <h2><a href="./README_EN.md">🌐 English</a></h2>
      <b>Current version</b>
    </td>
  </tr>
</table>

<p align="center">A summary of common LaTeX editors: pros, cons and configuration tutorials (TeX Live / VS Code / Overleaf)</p>

---

## 1. VS Code + TeX Live + LaTeX Workshop + AI-assisted (recommended)

### 1.1 Installation and configuration

#### 1.1.1 Install TeX Live

- Installation reference: https://www.tug.org/texlive/

#### 1.1.2 Install VS Code

- Install the LaTeX Workshop extension

#### 1.1.3 Modify the VS Code settings file to configure the compiler

> **!!! The configuration below is NOT required for basic usage**

See the separate document for details: [Modify the VS Code Settings File to Configure the Compiler](./docs/vscode-latex-tools_EN.md)

#### 1.1.4 Preview and sync (built into LaTeX Workshop, no configuration needed)

> **!!! With recent versions of LaTeX Workshop, a browser can be used as the PDF viewer with built-in sync, so no extra installation or configuration is required**

- Tested: Microsoft Edge works as a PDF viewer.
- Forward sync from LaTeX to PDF: `Ctrl` + `Alt` + `J` (`Cmd` + `Option` + `J` on Mac).
- Inverse sync from PDF to LaTeX: `Ctrl` + left click (`Cmd` + left click on Mac).

The following covers the **legacy** setup of SumatraPDF on Windows for PDF preview and inverse search. Newer versions do not need it; it is kept for reference only: [Installing SumatraPDF on Windows for PDF Preview and Inverse Search](./docs/sumatrapdf-preview_EN.md)

#### 1.1.5 Install AI-assisted tools such as CodeX / GitHub Copilot

### 1.2 Pros and cons

- **Pros:** Highly extensible thanks to a rich extension ecosystem. For example, you can sync with GitHub at any time and combine it with Overleaf to keep online and local editing in sync; integrate Zotero to insert references directly; use extensions such as CodeX and GitHub Copilot, or local agent tools, for AI-assisted writing.
- **Cons:** The overall configuration is somewhat cumbersome (greatly improved in newer versions).

## 2. TeX Live + TeXstudio

### 2.1 Installation and configuration

- Installation reference: https://www.tug.org/texlive/

### 2.2 Pros and cons

- **Pros:** Easy to install, regularly updated, feature-complete, nice-looking interface.
- **Cons:** Poor Chinese language support.

## 3. Overleaf (online editing)

- Official site: https://www.overleaf.com/

### 3.1 Pros and cons

- **Pros:** Online compilation, view from any device at any time, supports collaborative editing.
- **Cons:** Slower compilation, harder to debug.

## 4. VS Code + GitHub + Overleaf

### 4.1 Workflow

- Write locally in VS Code, upload to GitHub, and sync via GitHub when editing online in Overleaf.
- After editing in Overleaf, sync to GitHub and then download to your local machine through GitHub.

### 4.2 Installation and configuration

- Install and configure VS Code + TeX Live + LaTeX Workshop.
- Download the Git for Windows installer from the official site (https://git-scm.com/download/win), then install it.
- Create a new project in Overleaf and sync the files to GitHub (a paid membership is required for new users).
- Open the GitHub-hosted repository folder in the VS Code sidebar, sign in to VS Code with your GitHub account, and clone the repository locally.
- Locally modified files can be committed to GitHub, and Overleaf can sync from GitHub at any time.

### 4.3 Pros and cons

- **Pros:** Makes it easy to keep online and local editing in sync.
- **Cons:** The overall workflow has more steps, and changes are easily overwritten during collaboration.
