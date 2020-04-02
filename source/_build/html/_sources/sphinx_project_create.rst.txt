=======
Sphinx
=======

介绍
-----

Sphinx 是一个强大的文档生成器，具有许多用于编写技术文档的强大功能，包括：

- 维护一份源文档，生成网页，可打印的PDF，用于电子阅读器（ePub）的文档等

- 支持 reStructuredText 或 Markdown 编写文档

- 被广泛使用的代码文档系统

- 代码示例语法高亮

- 活跃的官方和第三方扩展生态

这里举几个用到sphinx的开源文档链接:

1. `Cozmo SDK <http://cozmosdk.anki.com/docs/index.html>`_
2. `python 版本介绍 <https://docs.python.org/3/>`_
3. `RoboMaster EP <https://robomaster-dev.rtfd.io/>`_

安装教程
--------

这里简单演示window下的sphinx文档创建过程

安装Sphinx
**********

    .. code-block:: python
        :linenos:

        pip install sphinx


安装sphinx主题
**********************

`sphinx主题 <https://sphinx-themes.org/>`_ 有多种多样，可以根据自己的喜好去修改主题

.. image:: /picture/theme.PNG

这里安装的主题是sphinx_rtd_theme

    .. code-block:: python
        :linenos:

        pip install sphinx_rtd_theme

修改主题，要修改对应的配置文件，配置文件在 ``/source/conf.py``

.. image:: /picture/html_theme.PNG



文档的创建
-----------

运行 **sphinx_start** 进行文档创建

.. image:: /picture/sphinx_start.PNG

.. tip::
    1. 文档根目录(Root path for the documentation)，默认为当前目录(.)
    2. 是否分离文档源代码与生成后的文档(Separate source and build directories): y
    3. 模板与静态文件存放目录前缀(Name prefix for templates and static dir):_
    4. 项目名称(Project name) : EvaEngine
    5. 作者名称(Author name)：AlloVince
    6. 项目版本(Project version) : 1.0.1
    7. 文档默认扩展名(Source file suffix) : .rst
    8. 默认首页文件名(Name of your master document):index
    9. 是否添加epub目录(Do you want to use the epub builder):n
    10. 启用autodoc|doctest|intersphinx|todo|coverage|pngmath|ifconfig|viewcode：n
    11. 生成Makefile (Create Makefile)：y
    12. 生成windows用命令行(Create Windows command file):y

    一般只要设置 **项目名称** **作者** 即可，其他默认回车 

生成的文档有三个最重要的目录：

``/Makefile`` :编译文档，检测拼写和语法

``/source/conf.py`` :包含所有配置和设置信息

``/source/index.rst`` :文档索引的目录

编译
****
    .. code-block:: python
        :linenos:

        make html

查看生成的文档
****************

找到创建文档目录 ``/build/html`` 下的 ``index.html`` ,双击运行。

.. image:: /picture/html.PNG

这就是生成的文档内容。

.. tip:: 更详细了解和使用sphinx，可以参考：`sphinx教程 <https://www.sphinx.org.cn/index.html>`_

文档编辑
----------

reStructuredText，Markdown，Notebook有多种多样的标记语言来书写文档，这边介绍reStructuredText

.. tip:: 

    .. image:: /picture/table.PNG
        :scale: 30%

reStructuredText介绍
*********************

reStructuredText（RST、ReST或reST）是一种用于文本数据的文件格式，主要用于 Python 编程语言社区的技术文档。

它是Python Doc-SIG（Documentation Special Interest Group）的 Docutils 项目的一部分，旨在为 Python 创建一组类似于 Java 的 Javadoc 或 Perl 的 Plain Old Documentation（pod）的工具。Docutils 可以从 Python 程序中提取注释和信息，并将它们格式化为各种形式的程序文档

reStructuredText是一个轻量级的标记语言，它的语法十分简单，学习成本低，它利用简介的语法代替排版，像常见的word会有大量的排版和字体设置，reStructuredText能让我们更专心的来书写内容。

.. tip:: 使用markdown修改目录下的 ``/source/conf.py`` 文件

    .. image:: /picture/markdown.PNG
        :scale: 30%

    这里列一个教程 `reStructuredText入门教程 <http://www.bary.com/doc/a/228277572381775842/>`_ ，就不具体展开

reStructuredText文档编辑器
**************************

这里介绍vscode来编辑文档

安装 sphinx
...............

    .. code-block:: python
        :linenos:

        pip install sphinx sphinx-autobuild

安装 restructuredtext-lint
..............................

    .. code-block:: python
        :linenos:

        pip install restructuredtext-lint

安装vscode插件
...............

1.插件reStructuredText

.. image:: /picture/rst.PNG
    :scale: 30%

2.插件Table Formatter

由于reStructuredText做表格特别麻烦，这个插件可以帮助你做表格，只需要把关键的标记写对，其余的都会自动补全而且效果十分美观。

.. image:: /picture/table.PNG
    :scale: 30%

vscode进行编辑
..............

打开之前生成好的文件目录，点开预览窗口，即可边编辑文档边看效果

.. image:: /picture/preview.PNG


这里大概给讲几个语法：
***********************

**（1）标题：**

可以使用任意符号 # * - = 等等都可以，标题关系至上而下为一级二级三级，相同符号为同一级

**（2）列表：** 
有符号列表

**1. 列表1**

**2. 列表2**

无符号列表

**- 列表1**

**- 列表2**

（3）超链接 

**`链接名称 <https://链接地址/>`_**

（4）图片

**.. image:: /picture/rst.PNG**
    **align: center**
    **:scale: 30%**

（5）代码引用

.. code-block:: python
        :linenos:
