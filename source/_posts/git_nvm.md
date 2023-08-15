1. 安装 `git`

    ```shell
    yum install -y git
    ```

2. 配置 git

    ```shell
    git --version # 查看版本

    git config --global user.name "xxx"   # 配置git
    git config --global user.email "xxx"  # 配置git
    git config -l  # 查看配置
    ```

4. 安装 `nvm`

    > 通过 git 来安装 nvm
    ```shell
    git clone https://github.com/cnpm/nvm.git ~/.nvm && cd ~/.nvm && git checkout `git describe --abbrev=0 --tags`
    ```
    > ~/.nvm 表示创建你的本地项目目录

5. 配置 nvm 环境

    ```shell
    echo ". ~/.nvm/nvm.sh" >> /etc/profile
    ```

6. 读取并执行配置

    ```shell
    source /etc/profile
    ```

7. 查看nvm

    > nvm [常用命令](http://39.106.78.182/detail/2)
    ```shell
    nvm --version
    ```