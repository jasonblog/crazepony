
#  固件燒寫


編譯好STM32的代碼，得到hex格式的固件文件，如何燒寫到主控中？

首先從crazepony的百度雲盤中下載開發工具，點擊[這裡](http://pan.baidu.com/s/1eQ1kfPw)。解壓壓縮文件得到3個文件夾。

## 安裝cp2102驅動
cp2102是Crazepony上使用的USB轉串口芯片。cp2102和STM32芯片以串口相連，和電腦PC以USB接口相連，這是Crazepony能夠接上USB線對飛控/遙控器進行固件燒寫編程和調試信息打印的原因。

首先要把cp2102的驅動在電腦PC上裝好，這樣電腦作為Host才能夠識別到cp2102。這個驅動在32位windows xp系統/64位 windows 7系統下都測試通過。

![](/assets/img/cp2102.jpg)

## 燒入hex文件
打開下載器，然後用這個下載器下載hex文件。如果無法燒入成功，可以重新插拔一下。

![](/assets/img/download.jpg)

下載成功的標註。

![](/assets/img/download-done.jpg)

對於Crazepony-II 5.0及以後的版本，實現了連續下載固件功能，直接使用cp2102復位STM32並且引導進入串口升級固件的ISP下載模式。所以必須選擇左下角的“RTS的高電平復位，DTR高電平進Bootloader”，如下圖所示：

![](/assets/img/download-1.jpg)

## 查看打印信息

連上usb線，打開壓縮包的裡的串口助手，波特率115200，查看調試參數，確認hex燒入成功，並且正常運行。注意選擇正確的串口。如果沒有信息，可以按下復位鍵復位飛行器主控（對於5.0版本之後，沒有復位按鍵）。

![](/assets/img/uart-info.jpg)
