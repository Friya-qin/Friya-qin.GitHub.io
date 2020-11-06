## ubuntu企业微信和微信安装全过程

一、企业版微信

企业版微信的安装参考https://www.jianshu.com/p/b745f0d36253这个回答，很快就可以安装好

    git clone https://gitee.com/wszqkzqk/deepin-wine-for-ubuntu.git(拉取代码)

    cd deepin-wine-for-ubuntu进入上面下载的代码的位置

    ./install.sh 执行安装命令

4.wget http://mirrors.aliyun.com/deepin/pool/non-free/d/deepin.com.weixin.work/deepin.com.weixin.work_2.4.16.1347deepin0_i386.deb获取安装包

    sudo dpkg -i deepin.com.weixin.work_2.4.16.1347deepin0_i386.deb安装

    搜索企业微信，即可打开使用

### 微信安装

    在命令行中进入上面企业微信的那个目录

    cd deepin-wine-for-ubuntu

    或许安装包
    wget http://mirrors.aliyun.com/deepin/pool/non-free/d/deepin.com.wechat/deepin.com.wechat_2.6.8.65deepin0_i386.deb

3.执行微信的安装代码
sudo dpkg -i deepin.com.wechat_2.6.8.65deepin0_i386.deb

    执行上面的命令会报错：deepin.com.wechat:i386 依赖于 deepin-wine32-preloader；然而： 软件包 deepin-wine32-preloader:i386 尚未配置。
    看到这个问题不要慌！已经给解决了！！！
    看到这个问题不要慌！已经给解决了！！！
    看到这个问题不要慌！已经给解决了！！！

于是需要配置i386这个依赖，网上有几个参考的网页，其中综合了两个人的网页，成功安装，过程略掉，直接讲操作

4.1 进入上层目录：

    cd ..

4.2 创建一个新目录用于放置这些需要额外安装的软件包依赖,并进入这个目录

    mkdir deep
  
     cd deep

4.3 无脑复制下面这段内容到命令行

    wget http://mirrors.aliyun.com/deepin/pool/non-free/d/deepin-wine/deepin-wine_2.18-22~rc0_all.deb

    wget http://mirrors.aliyun.com/deepin/pool/non-free/d/deepin-wine/deepin-wine32_2.18-22~rc0_i386.deb

    wget http://mirrors.aliyun.com/deepin/pool/non-free/d/deepin-wine/deepin-wine32-preloader_2.18-22~rc0_i386.deb

    wget http://mirrors.aliyun.com/deepin/pool/non-free/d/deepin-wine-helper/deepin-wine-helper_1.2deepin8_i386.deb

    wget http://mirrors.aliyun.com/deepin/pool/non-free/d/deepin-wine-plugin/deepin-wine-plugin_1.0deepin2_amd64.deb

    wget http://mirrors.aliyun.com/deepin/pool/non-free/d/deepin-wine-plugin-virtual/deepin-wine-plugin-virtual_1.0deepin3_all.deb

    wget http://mirrors.aliyun.com/deepin/pool/non-free/d/deepin-wine-uninstaller/deepin-wine-uninstaller_0.1deepin2_i386.deb

    wget http://mirrors.aliyun.com/deepin/pool/non-free/u/udis86/udis86_1.72-2_i386.deb

    wget http://mirrors.aliyun.com/deepin/pool/non-free/d/deepin-wine/deepin-fonts-wine_2.18-22~rc0_all.deb

    wget http://mirrors.aliyun.com/deepin/pool/non-free/d/deepin-wine/deepin-libwine_2.18-22~rc0_i386.deb

    wget https://mirrors.aliyun.com/deepin/pool/main/libj/libjpeg-turbo/libjpeg62-turbo_1.5.1-2_amd64.deb

    wget https://mirrors.aliyun.com/deepin/pool/main/libj/libjpeg-turbo/libjpeg62-turbo_1.5.1-2_i386.deb

4.4 准备添加32位支持

    sudo dpkg --add-architecture i386

4.5 添加成功，准备刷新apt缓存信息

    sudo apt update

4.6安装上面4.3中提到了所有deb软件包

    sudo dpkg -i *.deb

回到微信安装包deb所在的目录,重新安装微信的软件

    cd ..

    cd deepin-wine-for-ubuntu

    sudo dpkg -i deepin.com.wechat_2.6.8.65deepin0_i386.deb

然后搞定了！
