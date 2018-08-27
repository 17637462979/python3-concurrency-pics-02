![](http://www.madmalls.com/admin/medias/uploaded/mzitu-c3bd6a45.png)
![](http://www.madmalls.com/admin/medias/uploaded/async-mzitu-02-75e2c01f.png)
![](http://www.madmalls.com/admin/medias/uploaded/mzitu-022a41aa.jpg)


# 1. 理论

- [Python3爬虫系列01 (理论) - I/O Models 阻塞 非阻塞 同步 异步](http://www.madmalls.com/blog/post/io-models/)
- [Python3爬虫系列02 (理论) - Python并发编程](http://www.madmalls.com/blog/post/concurrent-programming-for-python/)
- [Python3爬虫系列06 (理论) - 可迭代对象、迭代器、生成器](http://www.madmalls.com/blog/post/iterable-iterator-and-generator-in-python/)
- [Python3爬虫系列07 (理论) - 协程](http://www.madmalls.com/blog/post/coroutine-in-python/)
- [Python3爬虫系列08 (理论) - 使用asyncio模块实现并发](http://www.madmalls.com/blog/post/asyncio-howto-in-python3/)


# 2. 实验

- [Python3爬虫系列03 (实验) - 同步阻塞下载](http://www.madmalls.com/blog/post/sequential-download-for-python/)
- [Python3爬虫系列04 (实验) - 多进程并发下载](http://www.madmalls.com/blog/post/multi-process-for-python3/)
- [Python3爬虫系列05 (实验) - 多线程并发下载](http://www.madmalls.com/blog/post/multi-thread-for-python/)
- [Python3爬虫系列09 (实验) - 使用asyncio+aiohttp并发下载](http://www.madmalls.com/blog/post/aiohttp-howto-in-python3/)


# 3. 使用方法

## 3.1 下载代码

```bash
# git clone https://github.com/wangy8961/python3-concurrency-pics-02.git
```

## 3.2 准备环境

爬虫客户端所在的操作系统如果是`Linux`:

```bash
# pip install -r requirements-linux.txt
```

爬虫客户端所在的操作系统如果是`Windows`:

```bash
# pip install -r requirements-win32.txt
```

## 3.3 测试

由于图片有13万多张，所以测试的时候你可以只指定下载100个图集来对比同步下载、多线程下载和异步下载的效率区别，修改以下三个脚本中的`TEST_NUM = 100`

建议每次测试完，都删除相关目录：

```bash
# rm -rf downloads/ logs/ __pycache__/
```

删除数据库记录：

```bash
[root@CentOS ~]# mongo
MongoDB shell version v3.6.6
connecting to: mongodb://127.0.0.1:27017
...
> show dbs
admin   0.000GB
config  0.000GB
local   0.000GB
mzitu   0.036GB
> use mzitu
switched to db mzitu
> db.dropDatabase()
{ "dropped" : "mzitu", "ok" : 1 }
> show dbs
admin   0.000GB
config  0.000GB
local   0.000GB
> 
```

### (1) 依序下载

```python
# python3 sequential.py
```

### (2) 多线程下载

```python
# python3 threadpool.py
```

### (3) 异步下载

```python
# python3 asynchronous.py
```