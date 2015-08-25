
#  Crazepony Android客戶端


Crazepony的Android客戶端源代碼也是託管在github的crazepony項目下，點擊[這裡](https://github.com/Crazepony/crazepony-android-client)查看。可以直接下載zip壓縮包，也可以通過git clone到本地。

```
git clone git@github.com:Crazepony/crazepony-android-client.git

```

## Android開發環境搭建
Crazepony的Android客戶端開發需要搭建Android APP開發環境。最簡單的辦法是使用Google Android提供的一站式開發包[ADT Bundle](http://developer.android.com/sdk/index.html)。ADT Bundle提供了Android APP開發所需的所有工具，包括Eclipse IDE，ADT (Android Developer Tools) 插件，java庫等等。

> 下載地址：[http://developer.android.com/sdk/index.html](http://developer.android.com/sdk/index.html)


下載解壓縮到任意目錄，就可以使用，無需安裝。

## 配置說明

Crazepony的Android客戶端默認編譯的Android SDK API版本為15（對應Android 4.0.3），支持的Android版本為4.0.0或以上。

![](/assets/img/Android-SDK-Manager.png)

![](/assets/img/Properties-for-CrazyflieControll.png)

## 關於通信

使用藍牙和主控上的藍牙透傳模塊通信，APP為主設備（master），主控上的藍牙透傳模塊為從設備（slave）。具體協議參考《通信協議》一文。

APP發送操作命令的頻率為20Hz，也就是說50ms發送一個操作命令包。

暫時沒有添加《通信協議》中提到的Packet length字段和checksum字段。原因是我覺得他們如此有點兒混亂，和其它數據包的處理不一致。

下面為藍牙透傳模塊接收到的數據截圖：

![](/assets/img/uart-rc.png)
