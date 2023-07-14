

本仓库fork原作者：https://github.com/wuheyi/vits-uma-genshin-honkai （原作者版本有bug已在本仓库修复）

# 安装

如果有conda环境，先创建conda：


```
conda craeate -n v python=3.9
```



# cuda加速推理，Nvidia显卡（可选）

```
用cuda推理速度能加快，本步骤也可以跳过
根据当前显卡实际情况下载cuda，我这里用12.2自己根据实际情况选择
https://developer.nvidia.com/cuda-12-2-0-download-archive
下载后得到cuda_12.2.0_535.54.03_linux.run
执行sh cuda_12.2.0_535.54.03_linux.run 具体过程可以网上查类似全部下一步...
配置环境变量到当前用户
vi /root/.profile
export PATH=$PATH:/usr/local/cuda/bin
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/local/cuda/lib64
可以下载最新的cuDNN能起到更好的优化（可选）
https://developer.nvidia.com/cudnn （点下方Download cuDNN,需要有nvidia账号登陆下载)
linux下载 Local Installer for Linux x86_64 (Tar)
下载后tar -zxvf cudnn-linux-x86_64-8.9.2.26_cuda12-archive.tar.xz
进入解压后的lib目录
cp ./lib/* /usr/local/cuda/lib64/
cp ./include/*  /usr/local/cuda/include/
```



# 安装依赖包

```
pip install -r requirements.txt
```


# model目录下数据文件


|D_0-p.pth | 187 MB|
| ------- | ------- |
|D_0.pth  | 561 MB|
| G_0-p.pth |  159 MB| 
| G_0.pth |  479 MB| 
| G_953000.pth |  479 MB| 


数据文件大概2G，github没法直接克隆，需要去：

https://huggingface.co/spaces/zomehwh/vits-uma-genshin-honkai/tree/main/model

下载，下载后文件放到model目录下

# 使用方法


```
python app.py --device cuda
```


--device 不带默认是cpu

启动完成访问http://127.0.0.1:7860


# 本手册只是对原版本bug进行修正和增加安装方式，其他


---
license: apache-2.0
title: ' vits-uma-genshin-honkai'
sdk: gradio
sdk_version: 3.7
emoji: 🐨
colorTo: yellow
pinned: false
app_file: app.py
---