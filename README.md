

# 什么是Doxygen

Doxygen 是一个程序的文件产生工具，可将程序中的特定批注转换成为说明文件。通常我们在写程序时，或多或少都会写上批注，但是对于其它人而言，要直接探索程序里的批注，与打捞铁达尼号同样的辛苦。大部分有用的批注都是属于针对函式，类别等等的说明。所以，如果能依据程序本身的结构，将批注经过处理重新整理成为一个纯粹的参考手册，对于后面利用您的程序代码的人而言将会减少许多的负担。不过，反过来说，整理文件的工作对于您来说，就是沉重的负担。
Doxygen 就是在您写批注时，稍微按照一些它所制订的规则。接着，他就可以帮您产生出漂亮的文档了。

因此，Doxygen 的使用可分为两大部分。首先是特定格式的批注撰写，第二便是利用Doxygen的工具来产生文档。

# 安装Doxygen

在https://www.doxygen.nl/download.html#srcbin中，根据具体操作系统选择具体的Doxygen版本。

此处以windows为例说明https://doxygen.nl/files/doxygen-1.9.1-setup.exe。

# 配置Doxygen

## Doxygen主界面Project配置



![image-20210330204458962](C:\Users\yangpei\AppData\Roaming\Typora\typora-user-images\image-20210330204458962.png)

说明：

- Doxygen 工作目录，就是用来存放配置文件的目录。

- 递归搜索源文件目录需要选上。

## Doxygen主界面Output配置

![image-20210330205258652](C:\Users\yangpei\AppData\Roaming\Typora\typora-user-images\image-20210330205258652.png)

## Doxygen主界面Diagrams配置

![image-20210330205409127](C:\Users\yangpei\AppData\Roaming\Typora\typora-user-images\image-20210330205409127.png)

说明：

如果选择这个选项之前需要先安装了 Graphviz 工具包。

## Expert主界面Project配置

![image-20210330205856555](C:\Users\yangpei\AppData\Roaming\Typora\typora-user-images\image-20210330205856555.png)

说明：

编码格式，UTF-8 首选。如果需要显示中文则选择GB2312.



| 参数                  | 说明                                                         |
| --------------------- | ------------------------------------------------------------ |
| DOXYFILE_ENCODING     | Doxygen文件的编码方式，默认为UTF-8，若希望支持中文，最好设置为 GB2312 |
| PROJECT_NAME          | Project 的名字，以一个单词为主，多个单词请使用双引号括住。   |
| PROJECT_VERSION       | Project的版本号码。                                          |
| OUTPUT_DIRECTORY      | 输出路径。产生的文件会放在这个路径之下。如果没有填这个路径，将会以目前所在路径作为输出路径。 |
| OUTPUT_LANGUAGE       | 输出语言, 默认为English 。                                   |
| EXTRACT_ALL           | 为NO，只解释有doxygen格式注释的代码；为YES，解析所有代码，即使没有注释 |
| EXTRACT_PRIVATE       | 是否解析类的私有成员                                         |
| EXTRACT_STATIC        | 是否解析静态项                                               |
| EXTRACT_LOCAL_CLASSES | 是否解析源文件（cpp文件）中定义的类                          |
| INPUT                 | 指定加载或找寻要处理的程序代码文件路径。这边是一个表列式的型态。并且可指定档案及路径。 |
| FILE_PATTERNS         | 如果您的INPUT Tag 中指定了目录。您可以透过这个Tag来要求Doxygen在处理时，只针对特定的档案进行动作。例如：您希望对目录下的扩展名为.c, .cpp及.h的档案作处理。您可设定FILE_PATTERNS = *.c, *.cpp, *.h。 |
| RECURSIVE             | 这是一个布尔值的Tag，只接受YES或NO。当设定为YES时，INPUT所指定目录的所有子目录都会被处理. |
| EXCLUDE               | 如果您有某几个特定档案或是目录，不希望经过Doxygen处理。您可在这个Tag中指定。 |
| EXCLUDE_PATTERNS      | 类似于FILE_PATTERNS的用法，只是这个Tag是供EXCLUDE所使用。    |
| SOURCE_BROWSER        | 如果设定为YES，则Doxygen会产生出源文件的列表，以供查阅。     |
| INLINE_SOURCES        | 如果设定为YES ，则函数和类的实现代码被包含在文档中           |
| ALPHABETICAL_INDEX    | 如果设定为YES，则一个依照字母排序的列表会加入在产生的文件中。（有很多类、结构等项时建议设为YES） |
| GENERATE_HTML         | 若设定为YES ，就会产生HTML版本的说明文件。HTML文件是Doxygen预设产生的格式之一。 |
| HTML_OUTPUT           | HTML文件的输出目录。这是一个相对路径，所以实际的路径为OUTPUT_DIRECTORY加上HTML_OUTPUT。这个设定预设为html。 |
| GENERATE_HTMLHELP     | 是否生成压缩HTML格式文档（.chm）                             |
| HTML_FILE_EXTENSION   | HTML文件的扩展名。预设为.html。                              |
| HTML_HEADER           | 要使用在每一页HTML文件中的Header。如果没有指定，Doxygen会使用自己预设的Header。 |
| HTML_FOOTER           | 要使用在每一页HTML文件中的Footer。如果没有指定，Doxygen会使用自己预设的Footer。 |
| HTML_STYLESHEET       | 您可给定一个CSS 的设定，让HTML的输出结果更完美。             |
| GENERATE_HTMLHELP     | 如设定为YES，Doxygen会产生一个索引文件。这个索引文件在您需要制作windows 上的HTML格式的HELP档案时会用的上。 |
| GENERATE_TREEVIEW     | 若设定为YES，Doxygen会帮您产生一个树状结构，在画面左侧。这个树状结构是以[JavaScript](https://www.oschina.net/action/GoToLink?url=http%3A%2F%2Flib.csdn.net%2Fbase%2Fjavascript)所写成。所以需要新版的Browser才能正确显示。 |
| TREEVIEW_WIDTH        | 用来设定树状结构在画面上的宽度。                             |
| GENERATE_LATEX        | 设定为YES 时，会产生LaTeX 的文件。不过您的系统必需要有安装LaTeX 的相关工具。 |
| LATEX_OUTPUT          | LaTeX文件的输出目录，与HTML_OUTPUT用法相同，一样是指在OUTPUT_DIRECTORY之下的路径。预设为latex。 |
| LATEX_CMD_NAME        | LaTeX程序的命令名称及档案所在。预设为latex。                 |
| GENERATE_RTF          | 若设定为YES ，则会产生RTF 格式的说明档。                     |
| RTF_OUTPUT            | 与HTML_OUTPUT 用法相同，用来指定RTF 输出档案路径。预设为rtf。 |
| GENERATE_MAN          | 若设定为YES ，则会产生Unix Man Page 格式的说明文件。         |
| MAN_OUTPUT            | 与HTML_OUTPUT 用法相同，用来指定Man Page的输出目录。预设为man。 |
| GENERATE_XML          | 若设定为YES ，则会产生XML 格式的说明文件。                   |
| ENABLE_PREPROCESSING  | 若设定为YES ，则Doxygen 会激活C 的前置处理器来处理原始档。   |
| PREDEFINED            | 可以让您自行定义一些宏。类似于gcc 中的-D选项。               |
| CLASS_DIAGRAMS        | 这个标记用来生成类继承层次结构图。要想生成更好的视图，可以从 Graphviz 下载站点 下载 dot 工具。Doxyfile 中的以下标记用来生成图表： |
| HAVE_DOT              | 如果这个标记设置为 Yes，doxygen 就使用 dot 工具生成更强大的图形，比如帮助理解类成员及其[数据结构](https://www.oschina.net/action/GoToLink?url=http%3A%2F%2Flib.csdn.net%2Fbase%2Fdatastructure)的协作图。注意，如果这个标记设置为 Yes，<CLASS_DIAGRAMS> 标记就无效了 |
| CLASS_GRAPH           | 如果 <HAVE_DOT> 标记和这个标记同时设置为 Yes，就使用 dot 生成继承层次结构图 |
| GRAPHICAL_HIERARCHY   | 设置为YES时，将会绘制一个图形表示的类图结构                  |

## Expert主界面Build配置

Build页面：生成帮助信息中比较关键的配置页面：

| 参数               | 说明                                                         |
| ------------------ | ------------------------------------------------------------ |
| EXTRACT_ALL        | 输出所有的函数，但是private和static函数不属于其管制。        |
| EXTRACT_PRIVATE    | 输出private函数。                                            |
| EXTRACT_STATIC     | 输出static函数。同时还有几个EXTRACT，相应查看文档即可。      |
| HIDE_UNDOC_MEMBERS | 那些没有使用doxygen格式描述的文档（函数或类等）就不显示了。当然，如果EXTRACT_ALL被启用，那么这个标志其实是被忽略的。 |
| INTERNAL_DOCS      | 是否输出注解中的@internal部分。如果没有被启动，那么注解中所有的@internal部分都将在目标帮助中不可见。 |
| CASE_SENSE_NAMES   | 是否关注大小写名称，注意，如果开启了，那么所有的名称都将被小写。对于C/C++这种字母相关的语言来说，建议永远不要开启。 |
| HIDE_SCOPE_NAMES   | 域隐藏，建议永远不要开启。                                   |
| SHOW_INCLUDE_FILES | 是否显示包含文件，如果开启，帮助中会专门生成一个页面，里面包含所有包含文件的列表。 |
| INLINE_INFO        | 如果开启，那么在帮助文档中，inline函数前面会有一个inline修饰词来标明。 |
| SORT_MEMBER_DOCS   | 如果开启，那么在帮助文档列表显示的时候，函数名称会排序，否则按照解释的顺序显示。 |
| GENERATE_TODOLIST  | 是否生成TODOLIST页面，如果开启，那么包含在@todo注解中的内容将会单独生成并显示在一个页面中，其他的GENERATE选项同。 |
| SHOW_USED_FILES    | 是否在函数或类等的帮助中，最下面显示函数或类的来源文件。     |
| SHOW_FILES         | 是否显示文件列表页面，如果开启，那么帮助中会存在一个一个文件列表索引页面。 |



![image-20210330210511537](C:\Users\yangpei\AppData\Roaming\Typora\typora-user-images\image-20210330210511537.png)

## Expert主界面Input配置



![image-20210330211028511](C:\Users\yangpei\AppData\Roaming\Typora\typora-user-images\image-20210330211028511.png)

说明：

输入的源文件的编码，要与源文件的编码格式相同。如果源文件不是UTF-8编码最好转一下。

## Expert主界面HTML配置

![image-20210330211321604](C:\Users\yangpei\AppData\Roaming\Typora\typora-user-images\image-20210330211321604.png)

说明：

1. CHM_FILE文件名需要加上后缀（xx.chm）。
2. 如果在 Wizard 的 Output Topics 中选择了 prepare for compressed HTML (.chm)选项，此处就会要求选择 hhc.exe 程序的位置。在 windows help workshop 安装目录下可以找到 hhc.exe。



# Run doxygen

点击 Run doxygen 按钮， Doxygen 就会从源代码中抓取符合规范的注释生成你定制的格式的文档

![image-20210330211459455](C:\Users\yangpei\AppData\Roaming\Typora\typora-user-images\image-20210330211459455.png)



![image-20210330212141528](C:\Users\yangpei\AppData\Roaming\Typora\typora-user-images\image-20210330212141528.png)

在output目录下可以看到html和letex文件夹

![image-20210330211934508](C:\Users\yangpei\AppData\Roaming\Typora\typora-user-images\image-20210330211934508.png)

