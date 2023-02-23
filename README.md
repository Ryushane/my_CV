# 一份简洁的中英文简历

分别有中文版本，英文版本，以及中英文版本。

主要参考了以下项目：
- [billryan/resume](https://github.com/billryan/resume)
- [Htallone/myCV](https://github.com/Htallone/myCV)

## 简介

该简历模板使用 XeLaTeX 编译，支持中文。靠这份简历找了NVIDIA、字节和几个金融央企的工作。对于一个应届毕业生来讲比较简洁好用。

## 预览

![resume-zh_CN](https://user-images.githubusercontent.com/48601190/220899907-35daa00b-51b6-4c1d-8039-117ee01a8ac9.jpg)

![resume](https://user-images.githubusercontent.com/48601190/220899913-bdb54fa6-8d0f-45dd-8802-e23f7a0e5350.jpg)

## 使用方法

使用TeX发行版本地编译
```
xelatex resume.tex % 编译英文简历
xelatex resume-zh_CN.tex % 编译中文简历
xelatex resume-en&zh_CN.tex % 编译中英文简历
```

注意，需要自行调整tikz照片的边距以适合自己照片大小（下面这段代码的-1.5cm, -0.6cm 就是用来调整照片距离页边的横向距离和纵向距离的）。

```
\begin{tikzpicture}[remember picture, overlay] 
  \node[anchor = north east] at ($(current page.north east)+(-1.5cm,-0.6cm)$) {\includegraphics[height=3cm]{avatar}};
\end{tikzpicture}%
```

页脚部分使用了tikz定位，需要编译两次才能排布到正确位置。

### Font Awesome的使用方法
首先在 Font Awesome Icons 上选中自己想使用的图标，然后在 fontawesomesymbols-generic.tex 中找到相应的宏, 将其作为普通文本一样使用。 如果不需要使用 FontAwesome 字体的把那些宏去掉即可。 其他的可以自行参考相应 cls 和 tex 文件。(这段直接从billryan的文档偷过来了)

## License

[The MIT License (MIT)](http://opensource.org/licenses/MIT)

字体仅供学习交流使用，请勿用于商业用途。
