
#  介紹幾個常用的宏的作用


在Crazyflie的固件代碼中，宏一般都定義在文件Makefile中。使用`CFLAGS += -D`的方式添加。

~~~
# Flag that can be added to config.mk
CFLAGS += -DUSE_UART_CRTP        # Set CRTP link to UART
CFLAGS += -DUSE_ESKYLINK         # Set CRTP link to E-SKY receiver
CFLAGS += -DENABLE_UART          # To enable the uart
CFLAGS += -DDEBUG_PRINT_ON_UART  # Redirect the console output to the UART
~~~


## ENABLE_UART
啟用串口打印功能。要想調試期間把信息打印到串口，還需要加上宏：DEBUG\_PRINT\_ON\_UART 

## USE\_UART\_CRTP
crtp模塊為：Crazy Realtime Transfer Protocol stack，是crazy flie的通信協議棧。通信鏈路可以2.4G 遙控信息，可以使用USE_ESKYLINK，也可以使用串口。若要使用藍牙模塊作為通信鏈路，應該開啟此宏。

## DEBUG\_PRINT\_ON\_UART
使用串口調試。在平衡算法當中進行調試的時候，串口打印顯得尤為重要，通過此宏可以開啟串口調試。注意：開啟串口調試的時候不能開啟宏USE\_UART\_CRTP，串口作為通信鏈接。

## BOARD_2
此宏在drivers/i2c_gpio.c文件中。因為版本2與版本3的i2c部分引腳有區別，去掉此宏定義適用於第三版的硬件


