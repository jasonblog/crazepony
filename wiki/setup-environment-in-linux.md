
#  STM32開發環境搭建-linux


Crazepony飛控主板使用STM32作為主控制器，下面主要介紹如何在ubuntu系統下進行STM32固件的開發/編譯/下載。

對STM32處理器代碼的開發需要在ubuntu系統下搭建arm嵌入式開發的交叉編譯工具鏈。測試的系統為ubuntu 14.04。

## 交叉編譯工具鏈安裝方法一
STM32處理器使用gcc-arm-none-eabi-交叉編譯鏈。使用wget下載交叉編譯工具鏈到本地，並且解壓縮到`~/bin/`目錄下。

```
wget https://launchpad.net/gcc-arm-embedded/4.7/4.7-2013-q1-update/+download/gcc-arm-none-eabi-4_7-2013q1-20130313-linux.tar.bz2
mkdir ~/bin
tar xjf gcc-arm-none-eabi-4_7-2013q1-20130313-linux.tar.bz2 -C ~/bin
```

修改~/.bashrc文件，將交叉編譯工具鏈的路徑添加到當前用戶的默認搜索路徑下。並且使用source命令使其馬上生效。

```
echo -e "\nPATH=\$PATH:$HOME/bin/gcc-arm-none-eabi-4_7-2013q1/bin" >> ~/.bashrc
source ~/.bashrc
```

可以使用type命令檢測交叉編譯工具是否安裝成功。例如檢測其`arm-none-eabi-gcc`命令，可以看到其在剛才安裝的~/bin目錄下檢測到。

```
type arm-none-eabi-gcc
arm-none-eabi-gcc 是 /home/ny/bin/gcc-arm-none-eabi-4_7-2013q1/bin/arm-none-eabi-gcc
```

## 交叉編譯工具鏈安裝方法二
方法一需要手動下載gcc-arm-none-eabi-工具鏈壓縮包，解壓縮，然後手動配置工具鏈的地址系統默認路徑下。該方法適合幾乎所有的Linux系統，例如fedora/ubuntu/debian等。對於ubuntu用戶，可以直接使用apt包管理工具進行安裝。

* 由於gcc-arm-none-eabi-沒有包含在ubuntu默認支持的包內，需要添加一個支持gcc-arm-none-eabi-的源：

```
sudo add-apt-repository ppa:terry.guo/gcc-arm-embedded
```

* 更新添加的源：

```
sudo apt-get update
```

* 安裝gcc-arm-none-eabi-工具鏈

```
sudo apt-get install gcc-arm-none-eabi
```

使用type命令檢查是否安裝成功，如果出現下面的提示，那麼就說明安裝成功，可以使用。

```
$ type arm-none-eabi-gcc
arm-none-eabi-gcc 是 /usr/bin/arm-none-eabi-gcc
```

## arm-none-eabi說明
arm相關的交叉編譯工具鏈由很多，例如arm-linux-eabi，arm-none-eabi。STM32處理器使用的是arm-none-eabi。

```
arm-none-eabi和arm-linux-eabi等的區別：
arm-linux-eabi 用於編譯arm linux內核代碼。
arm-none-eabi 不指名操作系統，可以是linux, 也可以是vxworks等，arm-none-eabi 不包含 __linux__ 等特定宏，所以往往編譯linux 內核的時候通不過，不支持那些跟操作系統關係密切的函數，比如fork(2)，使用的是newlib這個專用於嵌入式系統的C庫。
arm-none-linux-eabi 用於Linux的，使用Glibc。
```

## 硬件開發工具
Crazyflie電路原理圖使用的KiCad，KiCad以一個開源的EDA工具，並且跨平臺，在windows和linux下都能夠使用。

KiCad的home page：[http://www.kicad-pcb.org/](http://www.kicad-pcb.org)。在ubuntu下的安裝：

```
sudo apt-get install kicad
```
