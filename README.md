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



<h4> 配置方式： </h4>
<ul>
	<li>非docker</li>
	<li>非cdh</li>
	<li>自己准备脚本（历史数据删除脚本，数据获取脚本，快速启动脚本，开机脚本,自己处理zk,数据导入失败处理脚本）</li>
</ul>
<br />

<h4>配置补录：  </h4>
<ul>
	<li> 可以正常开启和关闭</li>
	<li>对于灾难性处理方案  ---  这个就暂时不理会了</li>
</ul>
<br />

<h4> 配置问题： </h4>
<ul>
	<li>gc</li>
	<li>hbase资源分配</li>
	<li>hive和mysql的定义区别</li>
	<li>时间延迟</li>
	<li>系统资源问题</li>
	<li>（说到底虚拟机没资源，要是有资源，搭建一个TICK什么的监控资源分配，肯定是爽爆了。听说es很会抢资源，很想一起跑着试一试，哈哈哈哈）</li>
</ul>
<br />


<h4> 建议： </h4>
<ul>
	<li>建议熟悉数据库知识</li>
	<li>建议先了解下phoenix，对cube优化有帮助</li>
</ul>
<br />

<h4> 实际操作问题： </h4>
<ul>
	<li>sqoop 数据问题.--自己创建数据库比较好，sqoop默认创建会导致date类型变成string等</li>
	<li>cube设计问题</li>
	<li> kybot你值的拥有，一个用于优化cube设计的在线工具</li>
</ul>
<br />

<h4> 语句效率 </h4>
<ul>
	<li>mysql快速</li>
			<p>
				单结构表，简单查询，索引优势.    select nid from node_file_viruses group by nid
			</p>
	<li>kylin快速</li>
			<p>
				单结构表，复杂查询，无法直接索引.    select nid, virus_name from node_file_viruses group by nid, virus_name
			</p>
</ul>
<br />

<h4> 几个常用概念 </h4>
<ul>
	<li>cube 和 cuboid</li>
	<li>cube的增量导入(build与merge)</li>
	<li>HBASE表结构与kylin</li>
</ul>
<br />

<h4> cube构建的3种途径</h4>
<ul>
	<li>Kylin Web</li>
	<li>命令行工具(未使用)</li>
	<li>RESTful API(未使用)</li>
</ul>
<br />
















