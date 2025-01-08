# first_2518
按照autodl教程配置好基础镜像后：
点击进入终端：
 
刚开始进入终端时，输入conda env list可以看见conda中存在的虚拟环境，一般最开始只有base这一个

如果输入conda activate base（该命令用于进入base环境），会发现报错，因为conda还没初始化

这时输入source activate，应该就会进入base环境（行头出现（base）），如果没有进入base，就conda activate base

将env.yml上传到存储空间：
 
选取主机所在地
 
点击上传：
 
上传的文件会进入autodl-fs:
 


进入base环境以后，直接输入conda env create -f /root/autodl-fs/env.yml
其中env.yml就是发到微信, /root/autodl-fs/env.yml为文件路径

然后conda开始创建环境，会需要十几分钟，中途会卡很正常，不用管，等它自己下载完就OK

创建完虚拟环境以后conda env list
会看见出现icm_new的虚拟环境
 

输入conda activate icm_new 进入虚拟环境，之后跑代码都是在该环境中
 

下面需要把项目工程上传到autodl-fs中，可以用教程中的Xftp来传输
不过我遇到的一个问题就是
 
按照他的操作以后，最近的会议这里没有显示。
不过在这个界面里面按照教程新建会话，下面列表会有显示。
然后按照教程上传文件即可，上传到autodl-fs中即可。
 

上传以后，autodl-fs中会有显示：
 

但是github上下载的项目部分不全(可能后续学长也补全了)，需要补全：
1、datasets
 
Datasetsl里面依次为：
 
 
保持一样应该就没有问题了

2、预训练模型
 
这个群里有

3、稳定扩散模型
 
这个就是在网站上下载的十几个G的文件，不过是压缩成zip利用Xftp上传过来的（Xftp上传相对快一点，两节课才传完）

因为autodl-fs的免费空间为20G，所以将这个大压缩包解压到autodl-tmp中
先进入到压缩包所在的文件夹中，上传的位置不一样所在文件夹也不同
输入cd /root/autodl-fs/in-context-matting_2
再输入unzip -d /root/autodl-tmp 文件名.zip

因为解压的位置不同，所以config文件夹中的eval.yaml文件里面需要修改
 

4、trimaps
 
如果trimap上传之前已经解压到项目中对应位置，就不用改了

如果没有，就把trimap按上面的操作一遍，解压到对应位置

5、eval.py
 
这里修改了一下默认值

运行eval.py代码：
进入eval.py所在的文件夹：cd /root/autodl-fs/in-context-matting_2
 
输入python eval.py
 
