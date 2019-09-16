# kylin

使用的配置环境介绍：
	三台虚拟机：虚拟机为Centos 7(1804)
	虚拟机配置介绍：
		双CPU
		8G内存

配置内容：
	zookeeper	

	完全分布式的HDFS
	YARN
	mrhistory

	HBASE(虽然支持主从切换HBASE MASTER，但实际应用中多次尝试让人恶心了，最后没有启动备用MASTER)

	HIVE(mariadb)

	kylin(单结点kylin，本阶段以尝试为主，未做kylin集群)

	sqoop(导入数据)

配置方式：
	非docker
	非cdh
	自己准备脚本（历史数据删除脚本，数据获取脚本，快速启动脚本，开机脚本）

配置补录：
	可以正常开启和关闭
	对于灾难性处理方案  ---  这个就暂时不理会了

配置问题：
	gc
	hbase资源分配 
	hive和mysql的定义区别







