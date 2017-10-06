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
#### 8. Build Django project
##### 配置虚拟环境
```
mkdir project
cd project

python3 -m venv myvenv

#Start your virtual environment
source myvenv/bin/activate
```
##### 配置环境
```
pip install django~=1.10.0
```
##### create application
```
django-admin startproject mysite .
```
##### 创建更改的文件
```
python manage.py makemigrations
```
##### 将生成的py文件应用到数据库
```
python manage.py migrate
```
##### 启动server
```
python manage.py runserver
```
##### create superuser
```
python manage.py createsuperuser
```
##### 导出数据/导入数据
```
python manage.py dumpdata appname > appname.json
python manage.py loaddata appname.json
```
#### 9. Django Rest Framwork
pattern: **Model - Serializer - ViewSet**

*Regular Experssion*
```
^ for the beginning of the text
$ for the end of the text
\d for a digit
+ to indicate that the previous item should be repeated at least once
() to capture part of the pattern
```
*QuerySet*

`python manage.py shell`

*HTML*

"glyphicon glyphicon-plus" is provided by the bootstrap theme we are using, and will display a plus sign for us

{% csrf_token %} This is very important, since it makes your forms secure

#### 10. Git 
```
git init
git config --global user.name ""
git config --global user.email ...

want it to ignore -> create a file called .gitignore

git status
git add --all .
git commit -m ""

git remote add origin https://github.com/zoeds08/***.git
git push -u origin master
```
#### 11. install brew
`/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`

#### 12. install mongodb
```
brew install mongodb

//when run mongodb found permission error
sudo mkdir -p /data/db
sudo chown -R 'id -u' /data/db

//run mongodb
mongod

```
#### 13. install VM

VMWARE Fusion + Ubuntu (change default settings, memory, disk, processor, set static IP)

#### 14. Ubuntu terminal

解压
```
tar -xvf file.tar
tar -xzf file.tar
```

run .sh
```
sudo ./file.sh
```

删除
```
rm -rf file
```

可执行
```
chmod +x file
```

连接两个OS
```
ssh ip
```

convert文件from MAC to Ubuntu
```
scp -r ip:~/
```
