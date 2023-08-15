
# 1 环境

- linux: Ubuntu 22.04 LTS
- python: 3.10.12 (> 3.7.8)

```
sudo apt-get install python3
```

- conda: 安装 && 配置

1. 下载安装
```
wget https://repo.anaconda.com/archive/Anaconda3-2023
.07-2-Linux-x86_64.sh
bash Anaconda3-2023.07-2-Linux-x86_64.sh 
```

2. conda: 配置环境变量`vim ~/.bashrc`，光标移到最后面，写入：

```
export ANACONDA_HOME=/root/anaconda3
export PATH=$ANACONDA_HOME/bin:$PATH
```

3. 输入`source ~/.bashrc`刷新配置文件，输入`conda -V`查看版本



# 2 安装jupyter

> 所有操作都在`root`下进行
> 确保服务器已安装python3

- 安装jupyter模块：

```
conda install ipython
conda install jupyter
conda list
conda install requests
conda update requests
```

# 3 配置jupyter

- 生成jupyter配置：

```
jupyter notebook --generate-config
```

- 打开`ipython`设置密码：

```
from notebook.auth import passwd
passwd()
```

- 输入两次密码后会得到一串码，将其放入c.NotebookApp.password = ''里面。
```
'argon2:$argon2id$v=19$m=10240,t=10,p=8$egu5LR+jb6H1wmuB7cavnQ$69tpuNPr/nv5nIXMSfFTg95rRkflFdNS6Lv3vrMwOTY'
```

- 使用`ifconfig`查看自己ip地址。

- 修改文件`vim /root/.jupyter/jupyter_notebook_config.py`，写入文件稳步:
```
c.NotebookApp.ip = '172.29.71.103'     # 设置访问IP
c.NotebookApp.open_browser = False    # 默认不自动打开浏览器
c.NotebookApp.password = 'xxxxxxxx'			# 输入刚刚生成的密钥
c.NotebookApp.port = 8888			# 设置端口， 其他端口应该也是可以的
c.NotebookApp.notebook_dir = 'jupyter_contain'     # 设置Jupyternotebook 打开的根目录

```

- 在Linux控制台输入命令启动服务：

```
jupyter notebook --allow-root --no-browser --port=80 --ip=0.0.0.0
```

# 4 问题

- 已经挂载了服务但是无法访问？



# 5 git

```
git add .
git commit -m "first"
git status
git push -u origin main
```




---


## 计算机行业
算法(5%) - AI

web, exe（本质上是一样的）

软件(80%) - 前端（工程师） --> web（网页）: 
        - 后端（工程师）
        - 网安（工程师）
        - 运维（工程师）
        - 测试（工程师）
        - ...
        - ChatGPT --> [ac 硬件适配（加速） --> ai 算法移植 -->] os 运行维护 --> software 软件架构 --> test 测试 --> 营销

os / ac (3 + 2%)

ac - 前端 scanner, interpreter
    - 中端 opt 
    - 后端 --> x86_64, arm


## 其他行业
杂（无人机、车机、手表、嵌入式） - fpga


---


## 写论文
1. word (富文本编辑器：国内普刊)
2. markdown (富文本标记语言：记笔记)
3. latex （富文本标记语言：专业写论文：外刊）


