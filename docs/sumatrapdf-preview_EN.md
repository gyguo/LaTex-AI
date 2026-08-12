<h1 align="center">Installing SumatraPDF on Windows for PDF Preview and Inverse Search</h1>

<table align="center">
  <tr>
    <td align="center" width="260">
      <h2><a href="./sumatrapdf-preview.md">📘 简体中文</a></h2>
      <b>点击切换</b>
    </td>
    <td align="center" width="260">
      <h2><a href="./sumatrapdf-preview_EN.md">🌐 English</a></h2>
      <b>Current version</b>
    </td>
    <td align="center" width="260">
      <h2><a href="../README_EN.md">⬅ Back</a></h2>
      <b>Main document</b>
    </td>
  </tr>
</table>

<p align="center">Legacy approach, for reference only</p>

---

> **!!! Recent versions of LaTeX Workshop do NOT need this configuration. This page is for reference only.**

References:

- https://blog.csdn.net/yuehenmiss/article/details/102915332
- https://github.com/James-Yu/LaTeX-Workshop/wiki/View#using-synctex-with-an-external-viewer

## 1. Configure SumatraPDF as the PDF viewer in VS Code

```json
"latex-workshop.view.pdf.viewer": "external",
"latex-workshop.view.pdf.ref.viewer":"external",
"latex-workshop.view.pdf.external.viewer.command": "C:/Users/gyguo/AppData/Local/SumatraPDF/SumatraPDF.exe",
"latex-workshop.view.pdf.external.viewer.args": ["%PDF%"],
```

Configure forward search in VS Code (from VS Code to SumatraPDF). Remember to replace the path with your own:

```json
"latex-workshop.view.pdf.external.synctex.command": "C:/Users/gyguo/AppData/Local/SumatraPDF/SumatraPDF.exe",
"latex-workshop.view.pdf.external.synctex.args": [
 "-forward-search",
 "%TEX%",
 "%LINE%",
 "%PDF%"
 ],
```

## 2. Configure inverse search in SumatraPDF (from SumatraPDF to VS Code)

**2.1.** Go to Settings → Options → Set inverse search command-line:

```
"Code.exe" "resources\app\out\cli.js" --ms-enable-electron-run-as-node -r -g "%f":"%l"
```

**2.2.** Replace `Code.exe` and `resources\app\out\cli.js` with the actual VS Code installation paths on your own machine, for example `C:\Users\gyguo\AppData\Local\Programs\Microsoft VS Code\Code.exe` and `C:\Users\gyguo\AppData\Local\Programs\Microsoft VS Code\resources\app\out\cli.js`:

```
"C:\Users\gyguo\AppData\Local\Programs\Microsoft VS Code\Code.exe" "C:\Users\gyguo\AppData\Local\Programs\Microsoft VS Code\resources\app\out\cli.js" --ms-enable-electron-run-as-node -r -g "%f":"%l"
```

If the “Set inverse search command-line” option cannot be found, open SumatraPDF → click the three-bar menu in the top-left corner → Advanced Options, and append the following two lines at the end of the file:

```
InverseSearchCmdLine = "C:\Users\gyguo\AppData\Local\Programs\Microsoft VS Code\Code.exe" "C:\Users\gyguo\AppData\Local\Programs\Microsoft VS Code\resources\app\out\cli.js" --ms-enable-electron-run-as-node -r -g "%f":"%l"
EnableTeXEnhancements = true
```
