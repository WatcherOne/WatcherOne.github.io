1. 查看可安装的版本

    ```shell
    yum list nginx*
    ```

2. 安装某一个版本

    ```shell
    yum install -y nginx.x86_64  # 表示自动同意安装
    ```

3. nginx配置文件

    ```shell
    vim /etc/nginx/nginx.conf
    ```
    > 注意 root 与 alias 的区别【路径配置 root /xxx/xx/ 最后一个是否有/；配置太难啦！】

    ![nginx配置](http://39.106.78.182/download/image/nginx配置.png)

4. 启动 `nginx` 服务

    ```shell
    nginx -t [-c /etc/nginx/nginx/conf]  # 查看nginx配置文件是否正确
    
    start nginx
    systemctl start nginx    # 两种方式都可以
    ```

5. nginx常用命令

    ```shell
    systemctl status nginx  # 查看nginx状态
    nginx -s reload         # 重启nginx（每次修改了配置文件都需要重启）
    nginx -s stop           # 关闭nginx
    ```
    ![nginx状态](http://39.106.78.182/download/image/nginx状态.png)

6. nginx 权限问题

    ![nginx-auth](http://39.106.78.182/download/image/nginx-auth.png)
    ```json
    [0]: 权限【读写类】
    [2]: 连结
    [3]: 拥有者
    [4]: 群组
    [5]: 文件容量
    [6]: 修改日期
    [7]: 文件或目录
    ```
    ```shell
    chmod 755 /xxx/xx          # * 修改当前文件下所有文件的权限 755: rwx 全放开
    chmod 所有者:所属组 /xxx/xx  # 修改后面文件夹或文件的所有者与所属者
    chmod -r 所有者:所属组 /xxx  # 修改子目录下的所有
    ```

7. 配置后端服务接口

    ```shell
    location /api {
        proxy_set_header Host $http_host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header REMOTE-HOST $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_pass http://localhost:8080/api;
    }
    ```
