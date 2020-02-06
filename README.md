# 前言

本模板（包括thesis-swufe.cls和thesis-swufe.bst）完全复制自[swufe模板]((https://github.com/sierxue/ThesisSWUFE)

感谢[swufe模板]((https://github.com/sierxue/ThesisSWUFE)的开发/维护者Pro.Gan提供的补充信息。

- 几个注意事项

1. 本模板的额front cover和back cover使用word生成，将做好的cover保存成pdf放到pic/pdf文件夹下，替换成对应文件即可。

2. 参考文献不要使用bookdown的原生写法即`[@XXX]`应使用`\cite{}`或者`\citing{}`.

3. 如果你更熟悉latex而不是R和Rstudio那么可以移步[sierxue/ThesisSWUFE](https://github.com/sierxue/ThesisSWUFE)

4. 经测试，bookdown预定义好的`theorem`block与本模板有冲突，需要使用定理的，建议阅读[sierxue/ThesisSWUFE](https://github.com/sierxue/ThesisSWUFE)的使用问帮

5. 更详细的注意事项请移步[sierxue/ThesisSWUFE]((https://github.com/sierxue/ThesisSWUFE)

6. 本模板亲测在win10和centos7（centos会出现字体缺失，需手动安装对应字体）下编译通过。


This is a template thesis of SWUFE(Southwestern University of Finance and Economics). Thanks to the **bookdown**(https://github.com/rstudio/bookdown), now you can write your thesis using the Rmarkdown syntax.

# Usage

## Latex Environment

If you do not have Latex installed, I highly recommend you to use the `tinytex` package.

```r
install.packages('tinytex')
tinytex::install_tinytex()
```

When using this template, you probabily missing some latex packages. `tinytex` will try to install them automatically. However, there are some packages that automatically installing will fail. Here are the commands to install them manually: 
```
# 自动安装失败的宏包会提示XXX.sty cannot find
tinytex::tlmgr_install("XXX")
```


## Thesis 

Set the basic infomation in the `index.Rmd` file.

```yaml
site: bookdown::bookdown_site
documentclass: book
output:
  bookdown::pdf_book:
    includes:
      in_header: misc/preamble.tex
    latex_engine: xelatex
    dev: "cairo_pdf"
    keep_tex: true
    pandoc_args: "--top-level-division=chapter"
    toc_depth: 3
    template: misc/main.tex
    quote_footer: ["\\begin{flushright}", "\\end{flushright}"]
# bachelor、master、promaster、doctor、engdoctor
classoption: "master"
chineseabstract: "中文摘要: 这里是中文摘要"
englishabstract: "This is a English abstract."
acknowledgement: "这里是致谢：在攻读硕士/博士学位期间，首先衷心感谢我的导师XXX"  
baseinfo:
  chinesekeyword: ["贸易战, 经济， 很关键"]
  englishkeyword: ["Trade War, economics, very important"]
bibliography: reference.bib
bibliography_all: true
link-citations: true
appendix: false
translate_original: false
translate_chinese: false
```

# 致谢

- 感谢[sierxue/ThesisSWUFE](https://github.com/sierxue/ThesisSWUFE)开发维护了西财论文的xelatex模板

- 感谢 RStudio/bookdown(https://github.com/rstudio/bookdown)提供了使用 R Markdown 进行文档编辑的可能

- 感谢[MelodyRen1998/bookdown-ruc](https://github.com/MelodyRen1998/bookdown-ruc),本文主要参照了该项目的结构，并复制了该项目的`preamble.tex`.

