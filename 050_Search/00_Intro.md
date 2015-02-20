## 搜索——基本的工具

到目前为止，我们已经学会了如何使用elasticsearch作为一个简单的NoSQL风格的分布式文件存储器——我们可以将一个JSON文档扔给Elasticsearch，也可以根据ID检索它们。但Elasticsearch真正强大之处在于可以从混乱的数据中找出有意义的信息——从大数据到全面的信息。

这也是为什么我们使用结构化的JSON文档，而不是无结构的二进制数据。Elasticsearch不只会**存储(store)**文档，也会**索引(indexes)**文档内容来使之可以被搜索。

**每个文档里的字段都会被索引并被查询**。而且不仅如此。在简单查询时，Elasticsearch可以使用**所有**的索引，以非常快的速度返回结果。这让你永远不必考虑传统数据库的一些东西。

A _search_ can be:
**搜索(search)**可以：

* 在类似于`gender`或者`age`这样的字段上使用结构化查询，`join_date`这样的字段上使用排序，就像SQL的结构化查询一样。
* 全文检索，可以使用所有字段来匹配关键字，然后按照**关联性(relevance)**排序返回结果。
* 或者结合以上两条。

很多搜索都是开箱即用的，为了充分挖掘Elasticsearch的潜力，你需要理解以下三个概念：


| 概念                            | 解释                                                                  |
| ------------------------------- | ----------------------------------------- |
| **映射(Mapping)**               | 数据在每个字段中的解释说明                                            |
| **分析(Analysis)**              | 全文是如何处理的可以被搜索的                                           |
| **领域特定语言查询(Query DSL)** | Elasticsearch使用的灵活的、强大的查询语言 |


以上提到的每个点都是一个巨大的话题，我们将在《深入搜索》一章阐述它们。本章节我们将介绍这三点的一些基本概念——仅仅帮助你大致了解搜索是如何工作的。

我们将使用最简单的形式开始介绍`search` API.

> ### 测试数据

> 本章节测试用的数据可以在这里被找到[https://gist.github.com/clintongormley/8579281](https://gist.github.com/clintongormley/8579281)

> 你可以把这些命令复制到终端中执行以便可以实践本章的例子。