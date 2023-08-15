1. 后端项目先打包，通过执行 package 或 mvn package

   ![java打包](http://39.106.78.182/image/service-nohup.png)

2. 将 .jar 压缩包放到 服务器 /usr/local/tomcat/webapps/
3. 进去打包文件位置，执行启动命令
    ```shell
    nohup java -jar xxx.jar &
    # nohup: no hang up; 不挂起，用于在系统后台不挂断地运行命令，退出终端不会影响程序的运行
    # 执行相应的配置
    nohup java -jar xxx.jar --spring.profiles.active=prod
    ```
