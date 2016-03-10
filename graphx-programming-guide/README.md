# GraphX编程指南

&emsp;&emsp;`GraphX`是一个新的`Spark API`，它用于图和分布式图(`graph-parallel`)的计算。`GraphX`通过引入[Resilient Distributed Property Graph](property-graph.md)：
顶点和边均有属性的有向多重图，来扩展`Spark RDD`。为了支持图计算，`GraphX`公开一组基本的功能操作以及一个优化过的`Pregel API`。另外，`GraphX`包含了一个日益增长的图算法和图`builders`的
集合，用以简化图分析任务。

&emsp;&emsp;从社交网络到语言建模，不断增长的规模以及图形数据的重要性已经推动了许多新的分布式图系统（如[Giraph](http://giraph.apache.org/)和[GraphLab](http://graphlab.org/)）的发展。
通过限制可表达的计算类型和引入新的技术来划分和分配图，这些系统可以高效地执行复杂的图形算法，比一般的分布式数据系统（`data-parallel`，如`spark`、`mapreduce`）快很多。

![data parallel vs graph parallel](../img/data_parallel_vs_graph_parallel.png)

&emsp;&emsp;然而，通过限制可表达的计算类型可以提高性能，但是很难表示典型的图分析途径（构造图、修改它的结构或者表示跨多个图的计算）中很多重要的`stages`。另外，我们如何看待数据取决于我们的目标，并且同一原始数据可能有许多不同表和图的视图。

![表和图](../img/tables_and_graphs.png)

&emsp;&emsp;结论是，图和表之间经常需要能够相互移动。然而，现有的图分析管道必须组成`graph-parallel`和`data- parallel`系统`，从而实现大数据的迁移和复制并生成一个复杂的编程模型。

![图分析路径](../img/graph_analytics_pipeline.png)

&emsp;&emsp;`GraphX`项目的目的就是将`graph-parallel`和`data-parallel`统一到一个系统中，这个系统拥有一个唯一的组合API。GraphX允许用户将数据当做一个图和一个集合（RDD），而不需要数据移动或者复制。通过将最新的进展整合进`graph-parallel`系统，GraphX能够优化图操作的执行。

* [开始](getting-started.md)
* [属性图](property-graph.md)
* [图操作符](graph-operators.md)
* [Pregel API](pregel-api.md)
* [图构造者](graph-builders.md)
* [顶点和边RDDs](vertex-and-edge-rdds.md)
* [图算法](graph-algorithms.md)
* [例子](examples.md)
