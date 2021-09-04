# MatrixDB--summarize
主要介绍作者使用过的MatrixDB技术,欢迎大家交流


# MatrixDB新版本跟踪

1、[MatrixDB 4.0发布会实录](https://mp.weixin.qq.com/s/jx8PdZ8HgdkhOJ4oG14oLg)

2、[MatrixDB 4.1发布--加字段不再需要改表](https://mp.weixin.qq.com/s/xu5S0mg-Ww6BPtjg5oXdPg)

| 序号 | 新特性 | 说明 | 
|:----:|:----:|:----:|
| 1 | mxkv自定义数据类型 | mxkv为企业版用户提供了kv自定义数据类型，主要应用于如下几个场景：1、要采集的指标过多，超过了PostgreSQL的最多1600列限制2、不同型号设备采集指标集合差别较大，导致在回传数据时有大量值为NULL的列3、无法预知指标集，即表schema可能要经常变 |
| 2 | Kafka数据接入 | MatrixDB 4.1.0新增Kafka无缝连接功能，可将Kafka数据持续接入到MatrixDB表中。不仅接入性能高，同时还支持图形化操作。 |
| 3 | 分区自动化管理函数 | 自动化分区管理是在做冷热分级存储的过程中，在之前版本手动调用分区管理函数的基础上，将该过程自动化。用户只要创建好分区策略，后台进程将会自动帮您完成。 1、分区自动创建与删除 2、分区数据热转冷3、默认分区自动切分|

3、[MatrixDB 4.2 版本正式发布：这4个新特性你需要了解下！](https://mp.weixin.qq.com/s/gZ-IpYEAji4IZB_eiB9CgQ)

| 序号 | 新特性 | 说明 | 
|:----:|:----:|:----:|
| 1 | Mars 引擎再优化 | 1、智能压缩算法上线，根据数据类型和特征判断是否启用压缩。使用新编码压缩后，存储占用空间下降70%。2、查询性能提升，基于时间戳排序的特定查询，时延下降千倍，从秒级降到“毫秒级”。3、查询内存使用量大大的降低，SELECT语句，内存使用率下降90%。|
| 2 | MatrixGate 支持 upsert  | MatrixGate 工具支持 upsert 语义，适用于如下场景：1、设备可能重复发送数据或更正错误时序数据 2、不同类别的指标数据分批发送，实现自动合并|
| 3 | 冷热分级转换支持归并压缩 | 为方便用户在分区表做热转冷的数据转换，可以将多个分区表合并到一起。一来能降低分区管理的压力，也利于DBA进行维护。 |
| 4 | 并行备份恢复“工具”首度公开亮相 | MatrixDB隆重推出mxbackup和mxrestore两大工具，相比继承自PostgreSQL的pg_dump和pg_restore，支持并行处理，备份恢复效率更高。 |

3.1 [5分钟带你了解MatrixDB 4.2新特性 — UPSERT](https://mp.weixin.qq.com/s/82pwqgne9J5sQGi9hZQPqw)

| 序号 | 定义 | 说明 | 
|:----:|:----:|:----:|
| 1 | 什么是UPSERT? | UPSERT 就是 UPDATE 和 INSERT 的结合。实现一条SQL内自动插入或者更新：如果记录不存在则插入，如果记录存在则更新。 |
| 2 | UPSERT的使用方法 | 为了数据库能够使用UPSERT功能，记得要在表的“设备id+时间戳”上创建UNIQUE约束。 |
| 3 | 如何使用UPSERT语义的SQL方式？ | 如何通过直接执行SQL语句的方式进行UPSERT，对于使用libpq或JDBC等来连接数据库的用户，可以直接参考如下SQL语法来操作。 |
| 4 | 如何使用UPSERT语义的MatrixGate方式？ | MatrixGate作为MatrixDB高性能数据接入工具，在4.2版本中也加入了对UPSERT语义的支持，所以在生产环境中，更加推荐用户选择使用MatrixGate方式接入，性能可以提升百倍。 |


# 学习资料汇总

1、[时序数据库插入性能评测：MatrixDB是InfluxDB的78倍，TDEngine的38倍](https://zhuanlan.zhihu.com/p/374151291)

2、[8大类49小类：史上最全的时序数据库选型指南](https://zhuanlan.zhihu.com/p/379500168)

3、[时序数据库的4个误区，你踩了几个？](https://zhuanlan.zhihu.com/p/366991013)

4、[从InfluxDB到MatrixDB -- 重新定义时序数据库](https://mp.weixin.qq.com/s/UVpmEIppGZKocLVxbmf9Pg)

5、[“胖数据库，瘦中台”：超融合数据库让工程师做更有意义的事](https://mp.weixin.qq.com/s/pplb4IATD5waFpVd8BThfg)

6、[mxkv自定义数据类型](https://mp.weixin.qq.com/s/N2sOtsP4nsM3mJ-3XuHZEg)

7、[图文解读MatrixDB自研存储引擎](https://mp.weixin.qq.com/s/NPkeEbLEuicTGl_UWaeOsg)

