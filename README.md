# ECDICT

Free English to Chinese Dictionary Database.

## 简介

这是一份英文->中文字典的双解词典数据库，根据各类考试大纲和语料库词频收录 20万条各类单词的英文和中文释义，并按照各类考试大纲和词频进行标注。

最初开发看书软件时需要给软件添加一个内嵌字典，在网上找到了一份别人提供的 EDictAZ.txt 的文本文件，里面有差不多两万英文单词的释义，于是开始用这个文件来提供字典查询，用着用着不够用了，又找到一份四六级到 GRE 包含释义的词汇表，但是缺少音标，于是写了个爬虫从各种资料里面把音标给爬下来，外加自己补充了一些组成了一份三万基本词汇的数据库。

其后数年根据各种资料和网友贡献词库增长到10万左右，又找到 Linux 下面的 cdict-1.0-1.rpm 这个开源字典数据（mdict的主词库也是根据 cdict转换得到），并按照英国国家语料库的前16万单词进行校对，补全很多语料库里词频较高但是却没有收录的词条。


## 选词

很多网上词典（如简明英汉词典，朗道词典）号称收词量大（40万），但是很多是些专业名词，光医学名词和化学名词就接近20万，这些平时用的并不多。

而平时用的很多的，如中考高考到 GRE的一万五千核心词汇，他们居然能缺少两千左右。对比英国国家语料库（BNC）的词频数据，前十万高频词汇缺少一万二多；同时对比美国当代语料库前六万高频词汇，任然缺少一万多。

国内词库制作之不严谨，由此可见一斑，大家常用的40万词条朗道字典（GoldenDict / StarDict配套的那个），居然没有收录 “learn” 这个单词，搞笑吧？我不知道是 bug还是什么。号称收词量最大的简明英汉词典，居然没有 “longtime”，当然他有词组“long time”，但是近年来 longtime已经链接为一个词了，并且词频很高。词频上升比较快的还有 Taliban ，这些他们都没收收录。

包括不限于国内某些著名的商业词典，很多号称收词量多，但是他们把词给收偏了，所以我们需要更科学的根据各类考试大纲和语料库对选词进行矫正。

OALD和朗文等也才8万左右的收词量，不要被那几十万乱七八糟的来自医学化学电力机械化工等专业的词条搞花了眼，从最初的中高考各类考试大纲开始，到各种语料库和词频库，补全真正重要的词，选词工作参考如下资料：

| 语料库 | 解释 |
|--------|------|
| 考试大纲 | 中考大纲，高考大纲，四六级大纲，托福雅思GRE大纲，等，必须覆盖到位 |
| BNC 词频数据 | 英国国家语料库（British National Corpus）是目前世界上最具代表性的当代英语语料库之一。该语料库书面语与口语并重，其光盘版词次超过一亿，其中书面语语料库9千余万词，口语语料库1千余万词。 |
| Oxford 3K | 《牛津3000词》是“由语言专家和经验丰富的教师根据词频和词意覆盖范围精心挑选的3000词，由于他们的重要性和有用性，被认为是应该最先学习的 |
| 华尔街日报 | 根据近20年华尔街日报语库整理而成的杂志类词频顺序表进行选词 |
| 柯林斯星级 | 柯林斯从语料库中将单词在日常生活中的使用频率统计出来，按照频率的高低将单词分级，五星的就是日常生活中最常用的，依次类推。|
| 美国当代语料库 | 前面的 BNC语料库主要收录了近几百年的英文单词，而当代语料库主要收录近20年的电影电视，报刊，谈话记录，文献，小说 等 |
| Urban Dictionary | 俚语俗语等词汇 |



## 双解释义

当然要双解，诸如 WordNet，wiktionary.org 等提供了大量开放的释义资料。同时针对各类考试大纲词汇，网上有不少带释义的单词表供人下载，这些数据有的有错误，有的格式不统一，有的缺音标，有的缺英文释义，有的却中文释义，质量层次补齐，需要书写必要的代码来一次次整理统计，纠正和补全。

索性类似 NodeBox, WordNet 之类的开放语料库提供了针对 Python 的自然语言处理工具包，可以 pip下载下来，直接分析词汇和定义，还有词形变化，反义词近义词等。

释义参考了大量资料，包括不限于：

| 名称 | 解释 |
|------|------|
| 各类资料 | 各类网上开源资料，小的有 EDictAZ.txt ，大的有 cdict-1.0-1.rpm 等 |
| 考试大纲 | 网上各种带释义的考试大纲词表 |
| NodeBox | 自然语言工具包，带 11487个动词，4600个副词，2万个形容词及 11万个名词的资料 |
| WordNet | 普林斯顿自然语言处理资料库和工具包 |
| Wiktionary | 多种语言的释义维基百科资料，由各国用户贡献的各类词条 |
| Wikepedia | 维基百科收录了大量词条解释 |
| CEDIT | 中文到英文的开放词典数据库，根据中文到英文的释义，反解出英文到中文的释义 |
| TheFreeDictionary.com | 多语言开放词典 |
| Google | Google Cloud Translation | 
| foldoc.org | Free Online Dictionary Of Computing |
| linguee.com | 数亿词条解释 |
| Babylon | 各类词条数据来源聚合 |
| Urban Dictionary | 俚语俗语释义 |
| Plain Text English Dictionary | 提供免费开放的纯文本格式的 16万英文单词释义 |

大量资料需要整合编辑校对，幸好有各种自然语言处理的开发包，可以用来做这件事情，制定评分标准，一个词语多个出处，选择最恰但准确的，核心词汇进行人工校对，部分不全的词条使用英翻中来解决。

## 单词标注

给数据库中每个单词标注：是否是各类考试大纲词汇？以及他们在 BNC和其他语料库里的词频顺序。BNC词频统计的是最近几百年的历史各类英文资料，而当代语料库只统计了最近20年的，为什么两者都要提供呢？

很简单，quay（码头）这个词在当代语料库里拍两万以外，你可能觉得是个没必要掌握的生僻词，而BNC里面却排在第 8906名，基本算是一个高频词，为啥呢？可以想象过去航海还是一个重要的交通工具，所以以往的各类文字资料对这个词提的比较多，你要看懂19世纪即以前的各类名著，你会发现BNC的词频很管用。

而你要阅读各类现代杂志，当代语料库的作用就体现出来了，比如 Taliban（塔利班），在 BNC词频里基本就没收录（没进前 20万词汇），而在当代语料库里，它已经冒到 6089 号了，高频中的高频。

BNC较为全面和传统，针对性学习能帮助你阅读各类国外帝王将相的文学名著，当代语料库较为现代，和实事以和科技紧密相关。所以两者搭配，干活不累。

经过标注后，你查任何一个单词，都会告诉你这个词汇是不是四六级词汇？雅思词汇？柯林斯星级是多少？是否是牛津3000核心词汇？传统词频和现代词频各是多少？这样单词的重要程度你就能了解个大概了。

其次是标注动词的各个时态，每个动词有现在分词，过去式，过去分词，第三人称现在时等四种时态，用 NodeBox 和 WordNet 工具包可以方便的查询每个动词的变化形式，如此你查单词时能够给你显示出来各种变体，同时将这些变体作为新的生词再次加入到字典中，大部分字典都没法查询动词的各种时态，ECDICT可以让你方便的查询一万多个动词（几乎所有动词）的所有派生词。

## 数据格式

采用 CSV文件存储所有词条数据，用 UTF-8进行编码，用 Excel的话，别直接打开，否则编码是错的。在 Excel里选择数据，来自文本，然后设定逗号分割，UTF-8编码即可。

| 字段 | 解释 |
|------|------|
| word | 单词名称 |
| phonetic | 音标，以英语英标为主，好听嘛 |
| definition | 单词释义（英文） |
| translation | 单词释义（中文）|
| pos | 词语位置，（待添加）|
| collins | 柯林斯星级 |
| oxford | 是否是牛津三千核心词汇 | 
| tag | 字符串标签：zk/中考，gk/高考，cet4/四级 等等标签，空格分割 |
| bnc | 英国国家语料库词频顺序 |
| frq | 当代语料库词频顺序 |
| exchange | 时态复数等变换，目前已经添加一万多个动词的变化形式 |
| detail | json 扩展信息 |
| audio | 读音音频 url （待添加）|

提供一段 Python 程序来读取这些数据，可以用它转换到 SQLite 和 MySQL 的数据库里，方便你用更高级的方法筛选查询。词条数据大小写不敏感，不论从查询还是排序，还是编程接口。

## 编程接口

代码 stardict.py 用于操作该数据（兼容 Python 2/3），同时实现三个类：

| 类名 | 说明 |
|------|------|
| DictCsv | 用于读写 ecdict.csv 数据格式文件 |
| StarDict | 用来读写 SQLite 词典数据文件，数据字段和上面相同，接口也和 CSV版本相同 |
| DictMySQL | MySQL版本的数据文件读写，同样字段和接口和上面两者相同 |

以上三个类都统一提供如下接口：

| 接口 | 说明 |
|------|------|
| query | 查询单词，可以查整数id（CSV里id为行号，其他两者是自增量）或单词字符串，返回Python字典 | 
| match | 单词匹配，匹配最相似的前 N个单词 |
| query_batch | 批量查询 |
| count | 返回数据库词条总数 |
| register | 注册新单词 |
| update | 更新单词数据，除了 id, word两个字段外其他都可以更新 |
| remove | 删除单词 |
| commit | 提交更改 |

在 stardict.tools 下面还有很多帮助类的接口，便于你维护词典数据：
1. 导出两个字典数据的差异
2. 导入差异数据到一个字典
3. 导出成 StarDict（星际译王）的原格式（用于 DictEditor生成字典）
4. 导出成 mdict 的 .mdx 的源文件（用于 MdxBuilder 生成 mdx字典）


## 欢迎贡献

采用 CSV格式正是为了方便 GITHUB上提交 PR，管理 differ，欢迎大家提交各类词条增补。

## TODO

* ~~搜索并校对：所有动词（3月21日根据 NodeBox 工具包校对完成）~~
* ~~搜索并校对：所有副词（3月22日完成校对）~~
* ~~搜索并校对：所有形容词（3月22日完成校对）~~
* 搜索并校对：所有动物名词（http://lib.colostate.edu/wildlife/atoz.php?letter=all）
* 搜索并校对：所有植物名词（http://davesgarden.com/guides/botanary/vbl/a/）
* 搜索并校对：所有地理名词（http://www.itseducation.asia/geography/a.htm）
* 搜索并校对：所有地名（https://wenku.baidu.com/view/5436f80876c66137ee0619c9.html）
* 补充完成非核心词汇的英文释义
* 补充各个单词的位置信息
* ~~补充动词的时态语态变种信息~~
* 继续修订核心两万词汇的释义准确性

## HISTORY

* 2017-3-23 继续使用 WordNet 补全约 1万个新增单词的英文定义。
* 2017-3-22 使用 NodeBox 校对完成所有副词和形容词。
* 2017-3-21 使用 NodeBox 校对完所有动词，并且添加动词各种时态。


