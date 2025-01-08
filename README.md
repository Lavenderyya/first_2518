# first_2518
按照autodl教程配置好基础镜像后,进入终端,输入conda env list可以看见conda中存在的虚拟环境，一般最开始只有base这一个

如果输入conda activate base（该命令用于进入base环境），会发现报错，因为conda还没初始化

这时输入source activate，应该就会进入base环境（行头出现（base）），如果没有进入base，就conda activate base

将env.yml上传到存储空间：
 
选取主机所在地,点击上传
 
上传的文件会进入autodl-fs:
 
进入base环境以后，直接输入conda env create -f /root/autodl-fs/env.yml
其中env.yml就是发到微信, /root/autodl-fs/env.yml为文件路径

然后conda开始创建环境，会需要十几分钟，中途会卡很正常，不用管，等它自己下载完就OK

创建完虚拟环境以后conda env list
会看见出现icm_new的虚拟环境
 

输入conda activate icm_new 进入虚拟环境，之后跑代码都是在该环境中
 

下面需要用Xftp把项目工程上传到autodl-fs中

上传以后，autodl-fs中即会有显示。
