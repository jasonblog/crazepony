
#  系統流程框架


介紹系統的初始化流程，以及系統任務之間的關係。

## 系統任務

最關心的是系統中由多少個任務在運行。在FreeRTOS下，任務的初始化使用函數。所以，用grep命令參看一下源代碼，可以看到一共有下面這些系統初始化的任務：

~~~
$ grep -inIw 'xTaskCreate' -r ./hal/ ./modules/
./hal/src/eskylink.c:312:  xTaskCreate(eskylinkTask, (const signed char * const)"EskyLink",
./hal/src/pm.c:111:  xTaskCreate(pmTask, (const signed char * const)"PWRMGNT",
./hal/src/uart.c:145:  xTaskCreate(uartRxTask, (const signed char * const)"UART-Rx",
./hal/src/radiolink.c:237:  xTaskCreate(radiolinkTask, (const signed char * const)"RadioLink",
./modules/src/stabilizer.c:157:  xTaskCreate(stabilizerTask, (const signed char * const)"STABILIZER",
./modules/src/crtp.c:77:  xTaskCreate(crtpTxTask, (const signed char * const)"CRTP-Tx",
./modules/src/crtp.c:79:  xTaskCreate(crtpRxTask, (const signed char * const)"CRTP-Rx",
./modules/src/info.c:68:  xTaskCreate(infoTask, (const signed char * const)"Info",
./modules/src/log.c:171:  xTaskCreate(logTask, (const signed char * const)"log",
./modules/src/pidctrl.c:43:  xTaskCreate(pidCrtlTask, (const signed char * const)"PIDCrtl",
./modules/src/param.c:92:   xTaskCreate(paramTask, (const signed char * const)"PARAM",
./modules/src/system.c:68:  xTaskCreate(systemTask, (const signed char * const)"SYSTEM",

~~~

所有的任務在創建之後，都會進入`while(1)`的循環中，也就是任務一直循環運行。

## 任務之間的關係

那麼任務之間的關係是怎麼樣的呢，如何各司其職完成系統的控制呢。下面使用一個簡圖進行了說明，邏輯主線是控制數據的傳遞。

![crazyflie task](/assets/img/crazyflie-task.png)

