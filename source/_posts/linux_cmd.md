> **vim / vi 命令**

| 命令 | 操作 | 说明 |
| --- | --- | --- |
| vim/vi 文件地址 |  | 当文件存在时, 进入vim模式；否则新建文件并进入vim模式 |
|  | 按 i | 进去insert编辑模式 |
|  | 按 esc | 退出某种编辑模式 |
|  | :q | 在退出模式下未修改时直接退出 |
|  | :q! | 在退出模式下强制退出 [放弃修改并退出] |
|  | :wq | 在退出模式下保存修改并退出vim/vi |

> **常用命令**

| 命令 | 说明 |
| --- | --- |
| chkconfig --list | 列出所有的系统服务 |
| mkdir xxx | 在当前位置新建文件夹 xxx |
| kill -9 pid | 杀死 pid 的进程 |
| firewall-cmd --state | 查看防火墙状态 |
| systemctl start firewalld.service | 开启防火墙 |
| systemctl stop firewalld.service | 关闭防火墙 |
| mv xx.text /home/xx | 移动文件到指定目录下 |
| systemctl start mysqld | 启动mysql服务 |
| systemctl stop mysqld | 关闭mysql服务 |
| systemctl restart mysqld | 重启mysql服务 |
| ls -l | 查看当前路径的所有文件以及文件夹的权限 |
| ps -ef | grep java | 查看java运行进程 ｜
