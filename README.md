# Yi-s-Note

#### 1. 解压rar:
`brew install unrar`

`unrar x jar.rar`

#### 2. Run RabbitMQ Server
The RabbitMQ server scripts are installed into `/usr/local/sbin`. This is not automatically added to your path, so you may wish to 
add `PATH=$PATH:/usr/local/sbin` to your `.bash_profile` or `.profile`. The server can then be started with rabbitmq-server.
##### userName: guest; password: guest

#### 3. Memcached
`/usr/local/bin/memcached -d -p 11211`

##### memcached进入

`memcached –d #default 11211`

`memcached –d –p 11211`

##### 看看有没有跑起来：

```
ps aux | grep memcached
pidof memcached
kill -9 22376
```

##### memcached 登录

`telnet 127.0.0.1 11211`

```
set key flags exptime bytes
set bittiger 0 900 9
memcached
STORED
```

`quit`

#### 4. gPRC protoc schema -> code

```
/Users/Zoe/Desktop/后端/第六周codelab2/protoc-3/bin/protoc 
--plugin=protoc-gen-grpc-java=/Users/Zoe/Desktop/后端/第六周codelab2/protoc-gen-grpc-java-1.3.0-osx-x86_64.exe 
--grpc-java_out=/Users/Zoe/Desktop/后端/第六周codelab2/helloworld 
--java_out=/Users/Zoe/Desktop/后端/第六周codelab2/helloworld 
--proto_path=/Users/Zoe/Desktop/后端/第六周codelab2/grpc-java-master/examples/src/main/proto 
/Users/Zoe/Desktop/后端/第六周codelab2/grpc-java-master/examples/src/main/proto/helloworld.proto
```

#### 5. Spark 

**MapReduce:**
```
YideMacBook-Pro:week7_codelab1 Zoe$ 
export SPARK_HOME=/Users/Zoe/Desktop/后端/第七周实战课/spark-2.0.0-bin-hadoop2.7
YideMacBook-Pro:week7_codelab1 Zoe$ 
export PYTHONPATH=$SPARK_HOME/python/:$PYTHONPATH
YideMacBook-Pro:week7_codelab1 Zoe$ 
export PYTHONPATH=$SPARK_HOME/python/lib/py4j-0.10.4-src.zip:$PYTHONPATH
YideMacBook-Pro:week7_codelab1 Zoe$ 
python demo0.py demo1.txt

```
*RDD*
```
/Users/Zoe/Desktop/后端/第七周实战课/spark-2.0.0-bin-hadoop2.7/bin/spark-submit 
--master local[8] --driver-memory 1G 
/Users/Zoe/Desktop/后端/第七周codelab1/week7_codelab1/demo0.py /Users/Zoe/Desktop/后端/第七周codelab1/week7_codelab1/demo1.txt
```
---

```
pip install virtualenv
source ENV/bin/activate
```
---
#### 6. 方便部署

```
pip freeze > requirements.txt
cat requirements.txt
pip install –r requirements.txt
```
#### 7. 裁剪大小文件

```
cat proxylist.txt | head -n 15 > proxylist2.txt
```
