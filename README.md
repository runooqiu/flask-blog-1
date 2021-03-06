基于python flask实现的blog程序.

### 如何使用:

####Linux(ubuntu)
打开终端

安装pip,和virtualenv

```
$ sudo apt-get install python-pip
$ sudo apt-get install python-virtualenv
```

从仓库中clone程序

```
$ git clone https://github.com/gaotongfei/flask-blog.git
```

进入目录

```
$ cd flask-blog
```

创建python虚拟环境

```
$ virtualenv venv
```
*2015-05-08 18:49:02更新*

执行下面的命令之前最好先执行.下面两步

```
$ sudo apt-get install build-essential autoconf libtool pkg-config python-opengl python-imaging python-pyrex python-pyside.qtopengl idle-python2.7 qt4-dev-tools qt4-designer libqtgui4 libqtcore4 libqt4-xml libqt4-test libqt4-script libqt4-network libqt4-dbus python-qt4 python-qt4-gl libgle3 python-dev
```

`$ sudo apt-get install libmysqlclient-dev`

---

启动虚拟环境

```
$ source venv/bin/activate
```

安装依赖

```
(venv) pip install -r requirements.txt
```
数据库:mysql

创建名为blog的数据库

当然如果想要创建别的名字的数据库,只要把`app.py`中`SQLALCHEMY_DATABASE_URI`中的blog改为你创建的数据库名称.

默认mysql用户名为root,密码为123456

不是的话自己改一下`SQLALCHEMY_DATABASE_URI`中对应内容就好

```
mysql -u your-username -pyour-password
create database blog;
```

添加管理员账号

```
(venv) python app.py shell
```

```
>>>from app import db, User
>>>Admin = User(email=’name@example.com’,username=’name’,password=’your-password’)
# 把email,username,password换成你的.
>>>db.session.add(Admin)
>>>db.session.commit()
```

现在数据库里就有你的用户信息了.

运行程序

```
(venv) python app.py runserver
```

默认是在`http://127.0.0.1:5000/`打开.
点击`登录`,输入你的邮箱和密码

登录后你就可以开始写博客了.

目前支持markdown写作

### 截图

登录

![1](/screen_shot/1.png)

---

发表文章

![2](/screen_shot/2.png)

---

首页

![3](/screen_shot/3.png)

---

后台管理

![4](/screen_shot/4.png)

---

### license

 WTFP
