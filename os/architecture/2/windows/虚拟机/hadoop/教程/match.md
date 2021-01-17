# match

## 进入hadoop目录

```
cd $HADOOP_PREFIX
``` 

## 查看hdfs

```
bin/hadoop fs -ls input
```

## 运行mapreduce

```
bin/hadoop jar share/hadoop/mapreduce/hadoop-mapreduce-examples-2.7.0.jar grep input output 'dfs[a-z.]+'
```

## 查看结果

```
bin/hadoop fs -cat output/*

# result
# 6 dfs.audit.logger
# 4 dfs.class
# 3 dfs.server.namenode.
# 2 dfs.period
# 2 dfs.audit.log.maxfilesize
# 2 dfs.audit.log.maxbackupindex
# 1 dfsmetrics.log
# 1 dfsadmin
# 1 dfs.servers
# 1 dfs.replication
# 1 dfs.file
```