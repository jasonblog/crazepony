
#  源代碼的文件編碼和文件格式


文件編碼
=============
原則上所有源代碼默認使用utf-8編碼。

網站源碼文件必須使用utf-8編碼。如果使用其它的編碼，例如中文中常見的gdb格式，會導致中文亂碼，或者網頁無法生成的問題。

文件編碼常識

Windows操作系統默認文件編碼是gbk，又叫做gb2312或者cp936。cp936是微軟發佈的用在文件系統中的編碼方式，而gb2313是中國國家標準，又叫做ANSI格式編碼。例如在notepad++編輯器上gb2312編碼的文件就顯示為ANSI格式編碼；使用Linux下的file命令，則顯示為ISO-8859；在Vim下使用`set fenc?`命令查看，則顯示為fileencoding=euc-cn。其實這三種都是表示gb2313編碼。

Linux操作系統默認文件編碼是utf-8，一般用系統宏$LANG表示。

~~~
$ echo $LANG
zh_CN.UTF-8
~~~

下面幾個crazepony固件代碼文件，就是使用的Windows下的默認編碼gb2313。為了在某些工具下（例如gitk工具）中文不顯示為亂碼，我們要求所有的文件都使用utf-8編碼。但是由於我們現在使用的Keil 4不支持utf-8編碼，所以utf-8編碼的中文在Keil 4下面會顯示為亂碼，所以這部分固件代碼沒有使用utf-8編碼。

~~~
$ file User_Src/*
User_Src/main.c:           ISO-8859 C++ program text
User_Src/Sys_Fun.c:        ISO-8859 C program text
User_Src/Sys_Fun.h:        ISO-8859 C program text
……
~~~



行結束符問題
=============
在Linux/Windows/Mac下，行結束符不一樣。這樣在多個平臺之間進行協作開發時，在checkin和checkout之後，會有很多行結束符不統一引起的問題。

添加.gitattribute文件，可以解決行結束符在多個平臺下不一致的問題。

~~~
# Explicitly declare text files we want to always be normalized and converted 
# to native line endings on checkout.
* text

# Denote all files that are truly binary and should not be modified.
*.png binary
*.jpg binary
*.gif binary
*.jar binary
*.so  binary
style/fonts/* binary
style/images/* binary
~~~

上面為現在使用的.gitattribute配置，解釋如下：

* 代碼庫中都為LF，也就是checkin的時候，會把所有文件的行結束符轉化為LF；
* 工作路徑下為所在OS的行結束符，也就是在checkout的時候，git回自動根據當前的OS將文件的行結束符做轉化；
* 對於圖片（以png/jpg/gif等結尾），jar庫，和so文件等二進制文件，不進行轉化；
