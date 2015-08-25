
#  Windows下開發環境搭建


## 環境配置說明
目前採用Keil+gcc+jlink是最好的編譯與調試方法。Keil內部有自己的編譯工具鏈，但是Keil自帶的編譯器不支持目前代碼的許多語法，所以建議使用gcc工具鏈。等代碼穩定未來可以直接移植到Keil自帶的編譯器上。

## 安裝arm-none-eabi gcc工具鏈
arm-2013.11-24-arm-none-eabi的[下載地址](http://url.cn/Q47CUQ)

* 為了後面配置的方便，在其中的"Next"菜單中選擇 “添加參數到環境變量” (菜單提示的是英文)
* 路徑請注意中間不要有空格。比如我的根路徑是：D:\MentorGraphics\Sourcery_CodeBench_Lite_for_ARM_EABI

## 使用Keil4
若Keil4能配置成功，選擇Keil4將是最方便的辦法。安裝Keil4並配置gcc的方法：

* 打開工程
* 點擊菜單 Project->Manage->Component,Envrenment,Book。選擇Folders/Entensions，選擇勾中gcc
* 把路徑設置為工具鏈的根目錄，比如我的環境設置為：D:\MentorGraphics\Sourcery_CodeBench_Lite_for_ARM_EABI
* 如圖所示：

![keil gcc配置方法](http://jannson.github.io/images/keil_gnu.jpg)

## 使用Keil5
若Keil4通過以上配置，編譯工程的時候提示找不到gcc或認不出來編譯文件的名字，那麼請安裝Keil5。Keil5的安裝文件是Keil4的幾倍，很多組件與模板都需要分開來安裝，安裝稍微比較麻煩。

* 下載並安裝：[mdk510.exe](http://url.cn/RpNDSG)
* 下載並安裝：[mdkcm510.exe](http://url.cn/OnByyf)
* 下載並安裝：[Keil.ARMCortex_D...0.0.1.pack Cortex相關模板文件](http://url.cn/OzaCAP)
* 下載並安裝：[Keil.STM32F1xx_D...1.0.4.pack STM32F1xx相關模板](http://url.cn/PHqblw)
* 下載[破解程序](http://url.cn/R2Pxw1)
打開keil5-->FILE-->Lisence Managerment 用破解程序生成序列號並輸入到keil5裡。破解成功。
* 下載：http://url.cn/O3oSQL 解壓並替換keil5根目錄開始的C:\Keil_v5\ARM\Segger壓縮包裡的兩個文件，以進行jlink調試：
* 配置gcc如同Keil的方法。
* 注意jlink的驅動：win7 x64與win7/winxp x86可能不一樣（TODO提供鏈接下載）

## 使用原生態的make編譯
使用原生態的make編譯也很方便，並且也可以通過keil來下載並調試

* 安裝arm-none-eabi工具鏈
修改工具鏈根目錄下的cs-make.exe為make.exe，cs-rm.exe為rm.exe
* 安裝python2.7並把其加入到環境變量
* 下載MyGit，並得到Git的windows版工具
* 下載crazyflie的默認python-client代碼，與此版本代碼在同一級目錄
* 打開MyGit，cd到項目代碼目錄並：
`make`

