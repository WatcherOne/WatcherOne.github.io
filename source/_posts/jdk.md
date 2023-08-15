1. 安装 jdk8 [官网资源包](https://www.oracle.com/java/technologies/javase/javase8-archive-downloads.html) ｜ [已下好的资源包](http://39.106.78.182/download/package/jdk-8u371-linux-x64.tar.gz)

2. 上传压缩包到指定目录下, 并解压

    ```shell
    tar -zxvf jdk-8u221.tar.gz -C /usr/local/java
    ```

3. 配置环境变量

    ```shell
    vim /etc/profile
    
    export JAVA_HOME=/usr/local/java/jdk-8      // 安装的JDK路径
    export JRE_HOME=/usr/local/java/jdk-8/jre   // JDK中JRE路径
    export CLASSPATH=".:$JAVA_HOME/lib:$JRE_HOME/lib"
    export PATH=$JAVA_HOME/bin:$PATH            // 其它环境变量用 : 连接
    ```

    > 为了防止所有命令找不到时加的，其实用上面的配置即可

    ```shell
    export PATH=/usr/local/sbin:/usr/local/bin:/sbin:/bin:/usr/sbin:/usr/bin:/root/bin
    ```

4. 读取并执行配置

    ```shell
    source /etc/profile
    ```

5. 查看JDK是否安装成功

    ```shell
    java -version
    ```
