Crazepony四軸飛行器
========

這是配套Crazepony四軸飛行器項目的書籍。使用了[GitBook](https://www.gitbook.com/)管理和發佈。

書籍的內容來自Crazepony網站[百科wiki](http://www.crazepony.com/wiki.html)，這裡只進行了整理和發佈，給大家提供在線查看的[Web版本](http://www.crazepony.com/book/)以及可供下載的[PDF版本]()。

Web版本書籍調試命令：

> gitbook serve ./

在瀏覽器下輸入[http://0.0.0.0:4000](http://0.0.0.0:4000)就可以查看修改效果。

Web版本書籍生成命令：

> gitbook build ./ --output=./outputFolder

在Crazepony網站的[Book目錄](http://www.crazepony.com/book/)下的就是使用該命令生成的靜態Web版本書籍。

書籍內容來自Crazepony網站wiki，我們會定期將wiki的更新同步到書籍中來。雖然網站wiki和gitbook書籍都是使用markdown語言寫成，但是還是有部分頭文件不相同。我們專門寫了一個python腳本批量將網站wiki的md文件轉化為適合gitbook的文件。進入./wiki目錄，運行：

> ./deleteline.py

2015-2-7 ，第一次發佈，0.1版本。


