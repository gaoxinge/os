# wordcount

## 创建本地文件

```
vi test.txt

# Hello Edison Chou
# Hello Hadoop RPC
# Hello Wncud Chou
# Hello Hadoop MapReduce
# Hello Dick Gu
```

## 进入hadoop目录

```
cd $HADOOP_PREFIX
``` 

## 创建hdfs目录

```
bin/hadoop fs -mkdir wordcountinput
```

## 上传hdfs文件

```
bin/hadoop fs -put /test.txt wordcountinput
```

## 查看hdfs

```
bin/hadoop fs -ls wordcountinput
```

## 运行mapreduce

```
bin/hadoop jar share/hadoop/mapreduce/hadoop-mapreduce-examples-2.7.0.jar wordcount wordcountinput wordcountoutput
```

## 查看结果

```
bin/hadoop fs -cat wordcountoutput/*

# result
# chou 2
# Dick 1
# Edison 1
# Gu 1
# Hadoop 2
# Hello 5
# MapReduce 1
# RPC 1
# Wncud 1
```