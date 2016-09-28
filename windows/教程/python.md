# python

## 进入hadoop目录

```
cd $HADOOP_PREFIX
```

## 创建mapper

```
vi mapper.py
chmod +x mapper.py
echo "foo foo quux labs foo bar quux" | ./mapper.py

# foo 1
# foo 1
# quux 1
# labs 1
# foo 1
# bar 1
# quux 1
```

```python
#!/usr/bin/env python  
import sys  
    
for line in sys.stdin:    
    line = line.strip()   
    words = line.split()    
    for word in words:   
        print '%s\t%s' % (word, 1)   
```

## 创建reducer

```
vi reducer.py
chmod +x reducer.py
echo "foo foo quux labs foo bar quux" | ./mapper.py | sort | ./reducer.py

# bar 1
# foo 3
# labs 1
# quux 2
```

```python
#!/usr/bin/env python  
from operator import itemgetter  
import sys  
  
current_word = None  
current_count = 0  
word = None  
 
for line in sys.stdin:   
    line = line.strip()  
    
    word, count = line.split('\t', 1)  
    
    try:  
        count = int(count)  
    except ValueError:  
        continue  
   
    if current_word == word:  
        current_count += count  
    else:  
        if current_word:   
            print '%s\t%s' % (current_word, current_count)  
        current_count = count  
        current_word = word  
 
if current_word == word:  
    print '%s\t%s' % (current_word, current_count)  
```

## 创建input

```
vi test.txt

# Hello Edison Chou
# Hello Hadoop RPC
# Hello Wncud Chou
# Hello Hadoop MapReduce
# Hello Dick Gu
```

## 上传hdfs

```
bin/hadoop fs -put mapper.py
bin/hadoop fs -put reducer.py
bin/hadoop fs -put test.txt
```

## 查看hdfs

```
bin/hadoop fs -ls
```

## 运行mapreduce

```
bin/hadoop jar share/hadoop/tools/lib/hadoop-streaming-2.7.0.jar \
-mapper mapper.py \
-reducer reducer.py \
-input test.txt \
-output output \
-file mapper.py \
-file reducer.py \
-file test.txt
```

## 查看结果

```
bin/hadoop fs -cat output/*

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