<h1 align="center">修改 VS Code 配置文件，设置编译程序</h1>

<table align="center">
  <tr>
    <td align="center" width="260">
      <h2><a href="./vscode-latex-tools.md">📘 简体中文</a></h2>
      <b>当前版本</b>
    </td>
    <td align="center" width="260">
      <h2><a href="./vscode-latex-tools_EN.md">🌐 English</a></h2>
      <b>Click to switch</b>
    </td>
    <td align="center" width="260">
      <h2><a href="../README.md">⬅ 返回主文档</a></h2>
      <b>Back</b>
    </td>
  </tr>
</table>

---

> **！！！简单使用不需要进行下方配置**

打开 `settings.json`：点击左下角“设置”按钮 → Command Palette → Preferences: Open User Settings (JSON)（参考： https://www.jb51.net/softjc/730336.html ）。

```json
"latex-workshop.latex.tools": [
     {
         "name": "xelatex",
         "command": "xelatex",
         "args": [
           "-synctex=1",
           "-interaction=nonstopmode",
           "-file-line-error",
           "%DOC%"
         ]
     },
     {
         "name": "pdflatex",
         "command": "pdflatex",
         "args": [
           "-synctex=1",
           "-interaction=nonstopmode",
           "-file-line-error",
           "%DOC%"
         ]
     },
     {
         "name": "bibtex",
         "command": "bibtex",
         "args": [
           "%DOCFILE%"
         ]
     }
 ],

 "latex-workshop.latex.recipes": [
   {
     "name": "pdflatex -> bibtex -> pdflatex*2",
     "tools": [
       "pdflatex",
       "bibtex",
       "pdflatex",
       "pdflatex"
     ]
   },
     {
       "name": "XeLaTeX",
       "tools": [
         "xelatex"
       ]
     },
     {
       "name": "PDFLaTeX",
       "tools": [
         "pdflatex"
       ]
     },
     {
       "name": "latexmk",
       "tools": [
         "latexmk"
       ]
     },
     {
       "name": "BibTeX",
       "tools": [
         "bibtex"
       ]
     },
     {
       "name": "xelatex -> bibtex -> xelatex*2",
       "tools": [
         "xelatex",
         "bibtex",
         "xelatex",
         "xelatex"
       ]
     }
 ],
```
