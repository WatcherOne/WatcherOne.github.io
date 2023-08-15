1. 下载对应的安装包

    ```shell
    wget https://dev.mysql.com/get/mysql57-community-release-el6-9.noarch.rpm
    ```

2. 安装用来配置mysql的 yum源的rpm包

    ```shell
    yum localinstall -y mysql57-community-release-el6-9.noarch.rpm
    ```
    > 安装成功后, 会在/etc/yum.repos.d/下会多出几个mysql的yum源的配置

    ![配置文件](http://39.106.78.182/download/image/yum-mysql.png)
    
3. 安装 mysql

    ```
    yum install -y mysql-community-server --nogpgcheck  # nogpgcheck 不校验数字签名
    ```
    > 如果遇到报错可能是: 配置源版本不对！将 6 -> 7   1 -> 0

    ```
    vim /etc/yum.repos.d/mysql-community.repo
    ```
    ![安装mysql-server报错](http://39.106.78.182/download/image/yum-mysql-bug.png)

4. 启动 mysql

    ```
    systemctl status mysqld          # 查看状态
    systemctl start mysqld.service   # 启动 mysql
    ```

5. 查看初始密码

    ```
    grep "password" /var/log/mysqld.log
    ```
    ![查看mysql初始密码](http://39.106.78.182/download/image/mysql-password.png)

6. root 连接数据库

    > mysql 命令台命令一定以 ';' 结尾
    ```
    mysql -u root -p  # 登录root账号
    alter user 'root'@'localhost' identified by '密码';   # 修改密码[有密码策略要求的]
    flush privileges;   # 刷新权限
    exit;               # 退出mysql命令台
    ```

7. 修改 mysql 权限类问题

    ```
    show databases;              # 显示所有数据库
    use mysql;                   # 使用mysql这个数据库来修改管理员权限
    select user,host from user;  # 从mysql这个数据库中的user表中取出 user,host字段
    ```
    ![mysql配置](http://39.106.78.182/download/image/mysql-init.png)
    > localhost 表示允许本地登录, 想要远程登录mysql, 需要修改权限为 %

    ```
    update user set host='%' where user = 'root';
    flush privileges;   # 设置了一定要刷新
    ```
    > 更新密码加密规则以适应低版本连接
    > 授权root远程登录, 后面密码代表登录密码

    ```
    alter user 'root'@'%' IDENTIFIED WITH mysql_native_password BY '登录密码';
    ```
