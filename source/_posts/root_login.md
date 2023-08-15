> **linux系统部分是默认禁用 SSHD 服务中root用户远程登录的，导致登录时提示用户名或密码错误**

1. 通过 VNC登录 开启 root 远程登录 - 初次进入需要重置密码 [密码限制-6位大小写]
2. 重置后 <span style="color:red">登录 VNC</span> , 默认维持300s左右时间, 超过无任何操作时会自动断开
3. 然后实例登录, 需要外面实例先进行实例密码重置, <span style="color:red">实例登录</span>: root + 密码 [不限位数大小写]
4. 进入VNC界面后，打开 SSH 配置文件

    ```shell
    vim /etc/ssh/sshd_config
    ```

    ![VNC界面](http://39.106.78.182/download/image/vnc%E7%95%8C%E9%9D%A2.png)
5. 按 i 进入编辑模式，将「PermitRootLogin」和「PasswordAuthentication」设为 yes

    ```vim
    PermitRootLogin yes
    PasswordAuthentication yes
    ```

    ![VNC界面](http://39.106.78.182/download/image/sshd%E9%85%8D%E7%BD%AE.png)

6. 按 esc 键退出 i 编辑模式，输入 :wq 保存修改退出
7. 重启SSHD服务 即可通过 ssh服务 root远程登录

    ```shell
    systemctl restart sshd.service
    ```

8. 本地开启 ssh 服务「需要有sshd服务才可以用ssh登录」

    ```
    ssh root@IP
    - 输入密码登录
    - ctrl + D 退出登录
    ```
