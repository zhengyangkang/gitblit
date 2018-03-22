# gitblit

> 使用gitblit在windows环境下搭建git服务
### 安装java
  1. 下载[java](http://www.java.com/zh_CN/)
  2. 具体安装及环境变量配置自行百度
### 安装gitblit
  1. 进入[gitblit官网](http://www.gitblit.com/)下载gitblit
  ![image](/images/gitblit.png)
  2. 解压压缩包，这里是解压在E盘根目录(这个路径可自行修改)
  3. 在E:/gitblit-1.8.0中新建个文件夹叫code用于存储资料(配置中会用到，这个路径可自行修改)
  4. 找到gitblit/data文件夹下的gitblit.properties文件，使用记事本或者任何代码编辑器打开，插入或者修改以下配置
    > git.repositoriesFolder(资料库路径)
    > server.httpPort(设定http协议端口号)
    > server.httpBindInterface(设定服务器IP地址)
    > server.httpsBindInterface(设定为localhost)
    > 保存，关闭文件
  ![image](/images/config.png)
  5. 找到gitblit/gitblit.cmd文件，双击运行
  6. 运行结果如下表示搭建成功
  ![image](/images/success1.png)
  7. 浏览器就可以直接访问gitblit了
  ![image](/images/success2.png)