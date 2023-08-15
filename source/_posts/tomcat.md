1. 去 Apache 官网下载 压缩包（或 [tomcat-8.5](http://39.106.78.182/download/package/apache-tomcat-8.5.88.tar.gz)）
2. 将源码包上传到服务器上并解压

    ```shell
    tar -xzvf tomcat-8.5.tar.gz
    ```

3. 将解压的文件夹移到指定位置（或在指定位置解压）

    ```shell
    mv tomcat-8.5.tar.gz /usr/local/tomcat
    ```

4. 拷贝文件 catalina.sh 到 init.d 下, 并在 init.d 开头添加下面语句

    > 是为了方便启动和停止 tomcat (自启动)

    ```vim
    # chkconfig: 112 63 37
    # description: tomcat server init script
    # Source Function Library
    . /etc/init.d/functions
    
    JAVA_HOME=/usr/local/java/       # jdk安装路径
    CATALINA_HOME=/usr/local/tomcat  # tomcat安装路径
    ```

5. 保存后，执行下面语句

    > chkconfig --list # 查看系统服务 (下面命令执行后可查看是否包含了tomcat)

    ```shell
    chmod 755 /etc/init.d/tomcat  # 修改文件或文件夹权限 755 权限
    chkconfig --add tomcat        # 将tomcat添加到系统服务中（方便自启动）
    chkconfig tomcat on           # on 设置开机自启动 off 关闭自启动
    ```

    ![查看系统服务](http://39.106.78.182/download/image/service-list.png)
6. 配置环境变量

    ```shell
    vim /etc/profile
    
    export CATALINA_HOME=/usr/local/tomcat/tomcat-8.5     // 配置 tomcat 路径别名
    export PATH=$PATH:$JAVA_HOME/bin:$CATALINA_HOME/bin   // 将 别名/bin 添加到 环境变量PATH 中
    ```

7. 读取并执行配置

    ```shell
    source /etc/profile
    ```

8. 启动 Tomcat

    > <span style="color:rgb(241, 123, 123)">/usr/local/tomcat/bin/startup.sh</span>

    ```shell
    ./startup.sh          // 进入 bin 目录下, 执行 = 开启 tomcat 服务
    ./shutdown.sh         // 进入 bin 目录下, 执行 = 关闭 tomcat 服务
    startup.sh            // 当配有环境变量时, 任何位置执行 [好像不太行,还是需要进入/bin]
    service tomcat start  // 任何位置开启 tomcat 服务
    service tomcat stop   // 任何位置关闭 tomcat 服务
    ```

    > 因为加入了系统服务中所有可以 service 启动; 因为 /etc/rc.d/init.d 下设置有 tomcat 启动脚本; service 命令执行时linux去 /etc/rc.d/init.d 找对应的脚本

9. 查看 Tomcat 状态

    ```shell
    ps -ef|grep java
    
    // # 当出现如下一行结果表示 tomcat 服务关闭状态, 否则开启
    // root 7010 1 0 Oct19 ? 00:30:30 [java]
    ```

10. Tomcat 对应 8080 端口服务能访问需要以下两点
    1. 防火墙关闭
    2. 云服务器完全组设置有入方向的 8080 端口
    3. /tomcat/conf/server.xml 配置文件 \<Connector port="8080"... />
    ![tomcat配置](http://39.106.78.182/download/image/tomcat%E9%85%8D%E7%BD%AE.png)
