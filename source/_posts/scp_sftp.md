> **当上传文件过大（超过500M）时，可以通过ssh来上传与下载**

| 方式 | 特点 |
| ---- | ---- |
| scp | 较为方便，功能单一 |
| sftp | 支持传输中断后继续传输，一般传输大文件，使用较多 |

##### `scp`
    
> 直接打开终端, 输入如下命令, 登录远程后即可下载上传文件
```shell
ssh root@ip
```

| 操作 | 命令 |
| ---- | ---- |
| 下载 | scp root@ip:/usr/xxx/a.txt /documents |
| 上传 | scp /documents/a.txt root@ip:/usr/xxx |
| 文件夹时 | -r | scp 后面加 -r |

```shell
scp -r /documents/web root@ip:/usr/documents
```

##### `sftp(ftp)`
> 打开终端, 选择新建远程连接, 选择 sftp, 添加服务器 IP, 输入密码

![sftp连接](http://39.106.78.182/download/image/sftp.png)

| 操作 | 命令 | 描述 |
| ---- | ---- | ---- |
| 下载 | get /usr/local/a.text /documents | 前为服务器路径，后为本地下载路径 |
| 上传 | put /documents/a.text /usr/local  | 前为本地上传文件路径`如果找不到文件路径，直接拖动文件到终端`，后为服务器路径 |
| 文件夹时 | -r | get/put 后面加 -r |
