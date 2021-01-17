# python2

## 进入hadoop目录

```
cd $HADOOP_PREFIX
```

## 创建input

```
vi test.txt

# 0067011990999991950051507004+68750+023550FM-12+038299999V0203301N00671220001CN9999999N9+00001+99999999999

# 0043011990999991950051512004+68750+023550FM-12+038299999V0203201N00671220001CN9999999N9+00221+99999999999

# 0043011990999991950051518004+68750+023550FM-12+038299999V0203201N00261220001CN9999999N9-00111+99999999999

# 0043012650999991949032412004+62300+010750FM-12+048599999V0202701N00461220001CN0500001N9+01111+99999999999

# 0043012650999991949032418004+62300+010750FM-12+048599999V0202701N00461220001CN0500001N9+00781+99999999999
```

## 创建mapper

```
vi mapper.py
chmod +x mapper.py
cat test.txt | ./mapper.py

# 011990-99999 19500515 +0000
# 011990-99999 19500515 +0022
# 011990-99999 19500515 -0011
# 012650-99999 19490324 +0111
# 012650-99999 19490324 +0078
```

```python
#!/usr/bin/env python
import re
import sys

for line in sys.stdin:
    val = line.strip()
    usaf, wban, date, temp, q = val[4:10], val[10:15], val[15:23], val[87:92], val[92:93]
    if temp != '+9999' and re.match('[01459]', q):
      print '%s-%s\t%s\t%s' % (usaf, wban, date, temp)
```

## 创建reducer

```
vi reducer.py
chmod +x reducer.py
cat test.txt | ./mapper.py | sort | ./reducer.py

# 011990-99999 19500515 22
# 012650-99999 19490324 111 
```

```python
#!/usr/bin/env python
import sys

last_key = None
max_val = 0

for line in sys.stdin:
    (station, date, temp) = line.strip().split('\t')
    key = '%s\t%s' % (station, date)
    if last_key and last_key != key:
        print '%s\t%s' % (last_key, max_val)
        (last_key, max_val) = (key, int(temp))
    else:
        (last_key, max_val) = (key, max(max_val, int(temp)))

if last_key:
    print '%s\t%s' % (last_key, max_val)
```

## 上传hdfs

```
bin/hadoop fs -put test.txt
bin/hadoop fs -put mapper.py
bin/hadoop fs -put reducer.py
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

# 011990-99999 19500515 22
# 012650-99999 19490324 111
```