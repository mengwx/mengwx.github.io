---
layout: post
title: "Jupyter Notebooks"       
category: notes
author: "孟文霞"

---

**简介**：[[.ipynb文件简介]](https://my.oschina.net/lionets/blog/274760)    
**语法**：[[Jupyter Notebooks 快速入门]](http://codingpy.com/article/getting-started-with-jupyter-notebook-part-1/)    
**发布**：[[如何将 ipynb 发布到 blog 中?]](https://segmentfault.com/a/1190000002399058)   
**格式转换**：[[Converting notebooks to other formats]](https://ipython.org/ipython-doc/3/notebook/nbconvert.html)    
## Jupyter Notebooks 较 Markdown 优点
* 插入公式和图片方便(包括科学计算常用的图像)
* 可以插入 .md 和 .tex 格式的内容
* 可以直接用命令转成其他格式的文件
* 可以直接插入代码，自动生成执行结果    

### 打开.ipynb文件方式
* 命令行进入包含`.ipynb`文件的目录
* 执行命令`jupyter notebook`
* 网页自动弹出目录文件，对应位置双击即可

之前 blog 上的文章直接用 .md 文件编写，在需要插入公式和图片的时候十分繁琐。并且有时候 blog 的内容还需要生成 .pdf 文件来交作业和周报，.md 文件转 .pdf 格式也很麻烦，今天发现了 Jupyter Notebooks 写起来十分方便，还可以直接用命令转成其他格式的文件，相关命令如下：    

    $ ipython nbconvert --to FORMAT notebook.ipynb
    --to html
    --template full (default)
    --template basic
    --to latex
    --template article (default)
    --template report
    --template basic
    --to pdf
    --to latex.
    --to slides
    --to markdown
    --to rst
    --to script
    --to notebook

**注意**：如果要把生成的文件转移到其他文件夹编译的话，需要把对应的图片也一起放到正确的相对路径位置。