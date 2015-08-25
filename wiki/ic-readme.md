
#  Crazepony器件總覽及選型說明


## 電機
716有刷空心杯電機（4.1版本）。

720有刷空心杯電機（5.0版本及以後），中心軸直徑1mm。淘寶購買地址：[地址1](http://item.taobao.com/item.htm?ut_sk=1.U5nfk/5pPyADAHT9gIoKBhWX_21380790_1416310719.Copy.ShareSceneItemDetail&id=41176268103)。

## 槳葉
直徑為45mm槳（4.1版本）。

直徑為75cm槳葉，槳葉中心孔直徑為1mm，正好配上面的720電機。淘寶購買地址：[地址1](http://item.taobao.com/item.htm?spm=a230r.1.0.0.ZZNieR&id=35723782642&ns=1&abbucket=7#detail)。

## 電池
飛機電池為350mAh，3.7V，25C航模電池。購買[地址](http://detail.1688.com/offer/1234287135.html)（建議自己上淘寶上尋找，這個鏈接是阿里巴巴鏈接，需要批量拿貨）。

購買時需要注意電池接口。

## 2.4G模塊
遙控器上使用市面上的2.4G模塊，根據遙控距離的不同，有下面兩種可以選擇。

加PA的鞭狀天線，最大發送功率20dBm，可以遙控距離100米。購買[地址](http://detail.tmall.com/item.htm?spm=a230r.1.14.1.6SuQ2w&id=40504364189&ad_id=&am_id=&cm_id=140105335569ed55e27b&pm_id=&abbucket=13)。

![](/assets/img/rm-ctrl-8.png)

不加PA的發射模塊，最大發射功率0dBm，可以遙控距離10米。購買[地址](http://detail.tmall.com/item.htm?spm=a230r.1.14.1.qbCmu0&id=41587731684&ad_id=&am_id=&cm_id=140105335569ed55e27b&pm_id=&abbucket=13)。

![](/assets/img/rm-ctrl-7.jpg)

## 主控MCU（單片機）
STM32f103T8U6，內核為ARM Cotex-M3，72MHz主頻，AD/硬件I2C/硬件PWM。

![](/assets/img/stm32-ic.jpg)

## 電機驅動
SI2302，N溝道增強型MOS，導通電阻82mΩ，2.2v低GS電壓。

## 陀螺儀加速度計
MPU6050，三軸陀螺儀+三軸加速度計，自帶DMP四元數輸出，內部溫度補償。

![](/assets/img/mpu-6050-ic.jpg)

## 氣壓計
MS5611，10cm精度氣壓計。

## 電子羅盤（磁力計）
HMC5883L，電子羅盤。

![](/assets/img/HMC5883L-ic.jpg)

## 2.4G無線射頻芯片
nRF24L01，2.4G無線射頻收發芯片。

![](/assets/img/nRF24L01-ic.jpg)

## 藍牙透傳模塊
HM-06

淘寶購買[地址](http://item.taobao.com/item.htm?spm=a230r.1.14.1.xYrzTD&id=17278839073&ns=1&_u=j1omdar17efa#detail)，僅此一家。

## USB轉串口芯片
cp2102，USB轉串口芯片，用於固件下載，參數調試。

## 鋰電池充電管理
LT4054，鋰電充電管理芯片。


## 搖桿電位器
淘寶購買[地址](http://item.taobao.com/item.htm?spm=a1z09.2.9.163.18Dk2I&id=38490983640&_u=m205fe4p579e)。

我們對油門搖桿的要求是推左右自動回中，推上下不回，可停留在另意位置。根據這個要求，我們只找到了這種**拆機**的搖桿物料。

5.1版本即以後，油門搖桿使用自動回中的電位器，不再使用上面的拆機搖桿，所有搖桿都是新物料。

## 陶瓷天線
飛機上2.4G使用了陶瓷天線，型號為：rainsun An9520-245。
