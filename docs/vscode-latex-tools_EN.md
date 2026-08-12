<h1 align="center">Modify the VS Code Settings File to Configure the Compiler</h1>

<table align="center">
  <tr>
    <td align="center" width="260">
      <h2><a href="./vscode-latex-tools.md">📘 简体中文</a></h2>
      <b>点击切换</b>
    </td>
    <td align="center" width="260">
      <h2><a href="./vscode-latex-tools_EN.md">🌐 English</a></h2>
      <b>Current version</b>
    </td>
    <td align="center" width="260">
      <h2><a href="../README_EN.md">⬅ Back</a></h2>
      <b>Main document</b>
    </td>
  </tr>
</table>

---

> **!!! The configuration below is NOT required for basic usage**

Open `settings.json`: click the “Settings” button in the bottom-left corner → Command Palette → Preferences: Open User Settings (JSON).

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
