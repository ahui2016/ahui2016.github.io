# PyBoke 的 Markdown 语法与效果

参考: <https://support.typora.io/zh/Markdown-Reference/>

我的这个博客是用 [PyBoke](https://github.com/ahui2016/pyboke) 生成的,
PyBoke 采用 [mistune](https://github.com/lepture/mistune) 做从 Markdown 到 HTML 的转换,
mistune 注重速度，转换速度极快，但支持的特性、功能比较少，只支持 Markdown 的一部分特性。

下面是 PyBoke 支持的语法及其渲染效果的展示。

## 段落和换行符

```md
第一行，后面跟两个空格  
第二行。

第一行，后面没有空格
第二行。

第一行，后面跟空行

第二行。
```

第一行，后面跟两个空格  
第二行。

第一行，后面没有空格
第二行。

第一行，后面跟空行

第二行。

## 标题

标题在行的开头使用1-6个 `#` 字符，对应于标题级别1-6。例如：

```md
# 这是一级标题

## 这是二级标题

###### 这是六级标题
```

## 引用文字

```md
> 这是一个有两段的块引用。这是第一段。
>
> 这是第二段。Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.

> 这是另一个只有一个段落的块引用。有一个空行分隔两个块引用。
```

> 这是一个有两段的块引用。这是第一段。
>
> 这是第二段。Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.

> 这是另一个只有一个段落的块引用。有一个空行分隔两个块引用。


## 无序列表

输入 `* list item 1` 将创建一个无序列表，该 `*` 符号可以替换为 `+` 或 `-`.

```md
* 红色
* 绿色 长句看看自动换行的效果长句看看自动换行的效果长句看看自动换行的效果长句看看自动换行的效果长句看看自动换行的效果长句看看自动换行的效果长句看看自动换行的效果
* 蓝色
```

* 红色
* 绿色 长句看看自动换行的效果长句看看自动换行的效果长句看看自动换行的效果长句看看自动换行的效果长句看看自动换行的效果长句看看自动换行的效果长句看看自动换行的效果
* 蓝色

## 有序列表

输入 `1. list item 1` 将创建一个有序列表。

```md
1. 红色
2. 绿色 长句看看自动换行的效果长句看看自动换行的效果长句看看自动换行的效果长句看看自动换行的效果长句看看自动换行的效果长句看看自动换行的效果长句看看自动换行的效果
3. 蓝色
```

1. 红色
2. 绿色 长句看看自动换行的效果长句看看自动换行的效果长句看看自动换行的效果长句看看自动换行的效果长句看看自动换行的效果长句看看自动换行的效果长句看看自动换行的效果
3. 蓝色

## （栅栏式）代码块

行内代码用反引号进行包裹，例如

```md
使用 `<html>` 标签。
```

使用 `<html>` 标签。

代码块用三个反引号进行包裹 (PyBoke 不支持语法高亮)

```ruby
require 'redcarpet'
markdown = Redcarpet.new("Hello World!")
puts markdown.to_html
```

## 表格

```md
| First Header | Second Header |
|--------------|---------------|
| Content Cell | Content Cell  |
| Content Cell | Content Cell  |
```

| First Header | Second Header |
|--------------|---------------|
| Content Cell | Content Cell  |
| Content Cell | Content Cell  |


表格支持左对齐、居中、右对齐（注意表格标题下的冒号）

```md
| Left-Aligned  | Center Aligned  | Right Aligned |
|:--------------|:---------------:|--------------:|
| col 3 is      | some wordy text | $1600         |
| col 2 is      | centered        | $12           |
| zebra stripes | are neat        | $1            |
```

| Left-Aligned  | Center Aligned  | Right Aligned |
|:--------------|:---------------:|--------------:|
| col 3 is      | some wordy text |         $1600 |
| col 2 is      |    centered     |           $12 |
| zebra stripes |    are neat     |            $1 |

## 水平线

独立一行输入 `---` (三个或更多减号) 可绘制一条水平线。

---

## 脚注

```md
您可以像这样创建脚注 [^footnote]

[^footnote]: Here is the *text* of the **footnote**. (注意，实际使用中，这一行写在文章的底部。)

点击上标可查看脚注的内容。
```

您可以像这样创建脚注 [^footnote]

点击上标可查看脚注的内容。

## 水平线(2)

独立一行输入 `***` (三个或更多星号) 也可绘制一条水平线。

***

## 链接

```md
This is [an example](http://example.com/ "链接的提示/说明") inline link (鼠标悬停在链接上可看到提示).

[This link](http://example.net/) has no title attribute (没有提示).

简单链接可直接使用尖括号，例如 <https://v2ex.com>
```

This is [an example](http://example.com/ "链接的提示/说明") inline link (鼠标悬停在链接上可看到提示).

[This link](http://example.net/) has no title attribute (没有提示).

简单链接可直接使用尖括号，例如 <https://v2ex.com>

## 图片

图像与链接类似， 但在链接语法之前需要添加额外的 `!` 字符：

```md
![替代文字](/path/to/img.jpg)

![替代文字](/path/to/img.jpg "可选标题")
```

##  斜体、粗体、删除线

```md
好运*单个星号*好运

好运_单个下划线_好运

好运**两个星号**好运

好运~~123abc~~好运
```

好运*单个星号*好运

好运_单个下划线_好运

好运**两个星号**好运

好运~~123abc~~好运


[^footnote]: Here is the *text* of the **footnote**.
