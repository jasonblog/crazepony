
#  windows下github的配置

git for Windows下載地址[http://msysgit.github.io/](http://msysgit.github.io/);

之後我們能看到有GitBash和GitGUI兩個程序，打開GitBash

為了生成一個sshkey輸入 ssh-keygen -t rsa


![](/assets/img/ssh-keygen.jpg)

去生成路徑下可以看到以下兩個文件：

![](/assets/img/id-rsa.jpg)

打開id_rsa.pub把裡面的內容全部複製出來。

打開GitHub點擊右上角的小扳手，在SSHKEY裡添加剛才複製的內容。提交就OK!

看到多了一個SSHKEYS。名字可以隨便寫。。

![](/assets/img/rsa-github.png)

下一步把GitHub上的源碼Clone到本地：

輸入git clone git@github.com:Crazepony/crazepony.github.io.git

連敲幾個回車

![](/assets/img/git-clone.jpg)

內容有點多，耐心等待一會。。。

進入crazepony的目錄:cd crazepony.github.io

也可以使用git gui來管理我們的版本庫：

![](/assets/img/git-gui.jpg)
