<h1 align="center">Windows 安装 SumatraPDF 用于预览 PDF 和反向搜索</h1>

<table align="center">
  <tr>
    <td align="center" width="260">
      <h2><a href="./sumatrapdf-preview.md">📘 简体中文</a></h2>
      <b>当前版本</b>
    </td>
    <td align="center" width="260">
      <h2><a href="./sumatrapdf-preview_EN.md">🌐 English</a></h2>
      <b>Click to switch</b>
    </td>
    <td align="center" width="260">
      <h2><a href="../README.md">⬅ 返回主文档</a></h2>
      <b>Back</b>
    </td>
  </tr>
</table>

<p align="center">旧版本方案，仅供参考</p>

---

> **！！！新版本的 LaTeX Workshop 不需要该配置，本文仅供参考**

参考链接：

- https://blog.csdn.net/yuehenmiss/article/details/102915332
- https://github.com/James-Yu/LaTeX-Workshop/wiki/View#using-synctex-with-an-external-viewer

## 1. 在 VS Code 中设置 SumatraPDF 用于预览 PDF

```json
"latex-workshop.view.pdf.viewer": "external",
"latex-workshop.view.pdf.ref.viewer":"external",
"latex-workshop.view.pdf.external.viewer.command": "C:/Users/gyguo/AppData/Local/SumatraPDF/SumatraPDF.exe",
"latex-workshop.view.pdf.external.viewer.args": ["%PDF%"],
```

在 VS Code 中设置正向搜索（从 VS Code 到 SumatraPDF），注意修改为自己的地址：

```json
"latex-workshop.view.pdf.external.synctex.command": "C:/Users/gyguo/AppData/Local/SumatraPDF/SumatraPDF.exe",
"latex-workshop.view.pdf.external.synctex.args": [
 "-forward-search",
 "%TEX%",
 "%LINE%",
 "%PDF%"
 ],
```

## 2. 在 SumatraPDF 中设置反向搜索（从 SumatraPDF 到 VS Code）

**2.1.** 进入 设置 → 选项 → 设置反向搜索命令行：

```
"Code.exe" "resources\app\out\cli.js" --ms-enable-electron-run-as-node -r -g "%f":"%l"
```

**2.2.** 根据 VS Code 具体的安装位置，将 `Code.exe` 和 `resources\app\out\cli.js` 换成 VS Code 在自己的电脑上的安装位置，例如 `C:\Users\gyguo\AppData\Local\Programs\Microsoft VS Code\Code.exe` 以及 `C:\Users\gyguo\AppData\Local\Programs\Microsoft VS Code\resources\app\out\cli.js`：

```
"C:\Users\gyguo\AppData\Local\Programs\Microsoft VS Code\Code.exe" "C:\Users\gyguo\AppData\Local\Programs\Microsoft VS Code\resources\app\out\cli.js" --ms-enable-electron-run-as-node -r -g "%f":"%l"
```

如果找不到“设置反向搜索命令行”选项，打开 SumatraPDF → 点击左上角三条杠设置 → 高级选项，在代码末尾插入两条代码：

```
InverseSearchCmdLine = "C:\Users\gyguo\AppData\Local\Programs\Microsoft VS Code\Code.exe" "C:\Users\gyguo\AppData\Local\Programs\Microsoft VS Code\resources\app\out\cli.js" --ms-enable-electron-run-as-node -r -g "%f":"%l"
EnableTeXEnhancements = true
```
