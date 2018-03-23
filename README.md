# gitblit

> 使用gitblit在windows环境下搭建git服务
### 安装java（未测试）
  1. 下载[java](http://www.java.com/zh_CN/)
  2. 安装完成后到'我的电脑'右键=>'高级系统设置'=>'高级'=>'环境变量',在'系统变量'中插入或修改以下变量
    * 变量名：‘JAVA_HOME’，变量值：‘C:\Program Files\Java\jdk1.8.0_151’(这这个看自己的jdk安装路径)
    * 变量名：‘CLASSPATH’，变量值：‘.;%JAVA_HOME%\lib;%JAVA_HOME%\lib\dt.jar;%JAVA_HOME%\lib\tools.jar’
    * 变量名：‘PATH’，变量值：‘;%JAVA_HOME%\bin;%JAVA_HOME%\jre\bin’
    * 配置完成，一路点击确定
  3. 进入cmd输入java -version，java，javac来验证是否安装成功
### 安装gitblit
  1. 进入[gitblit官网](http://www.gitblit.com/)下载gitblit<br />
  ![image](/images/gitblit.png)
  2. 解压压缩包，这里是解压在E盘根目录(这个路径可自行修改)
  3. 在E:/gitblit-1.8.0中新建个文件夹叫code用于存储资料(配置中会用到，这个路径可自行修改)
  4. 找到gitblit/data文件夹下的gitblit.properties文件，使用记事本或者任何代码编辑器打开，插入或者修改以下配置
    * git.repositoriesFolder(资料库路径)
    * server.httpPort(设定http协议端口号)
    * server.httpBindInterface(设定服务器IP地址)
    * server.httpsBindInterface(设定为localhost)
    * 保存，关闭文件<br />
  ![image](/images/config.png)
  5. 找到gitblit/gitblit.cmd文件，双击运行
  6. 运行结果如下表示搭建成功<br />
  ![image](/images/success1.png)
  7. 浏览器就可以直接访问gitblit了<br />
  ![image](/images/success2.png)
  8. 默认超级管理员账户：admin，密码：admin，登录成功之后就可以进行相关操作了
### 设置以windows service启动gitblit
  1. 找到gitblit-1.8.0/installService.cmd，使用记事本或者任何代码编辑器打开，修改ARCH
    * 32位系统：SET ARCH=x86
    * 64位系统：SET ARCH=amd64
  2. 添加CD为程序目录
    * SET CD=E:/gitblit-1.8.0（你的实际目录）
  3. 修改‘StartParams’里的启动参数为空
  4. 保存，关闭文件<br />
  ![image](/images/windows-service-config.png)
  5. 找到gitblit-1.8.0/installService.cmd文件，右键以管理员身份运行
  6. 这时进入'我的电脑'=>'管理'=>'服务和应用程序'=>'服务'
    * 找到gitblit，选中（如果没有，请关闭后重新打开）
    * 选中后点击'启动'此服务
    * 等待一段时间后，浏览器就可以直接访问gitblit了<br />
  ![image](/images/windows-service.png)