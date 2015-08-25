
> 本教程適合Crazepony-II 5.1版本

## 整機物料列表

* Crazepony四軸飛行器，電機已經安裝（1個）
* 正反槳葉（各2只）
* Crazepony遙控器，搖桿已經安裝（1個）
* 搖桿帽（2個）
* 遙控器用2.4G無線模塊（1個）
* 備用螺絲，墊片，硅膠墊若干

## 機身安裝
四軸飛行器的槳葉分為兩種，正槳和反槳。安裝的時候不能夠搞混淆。槳葉上標示有R的安裝到M2，M4兩個機臂的電機上。標示有L槳葉安裝到M1，M3兩個機臂電機上。

![](/assets/img/user-guide-5-0-1.jpg)
![](/assets/img/user-guide-5-0-2.jpg)

發貨清單中有黑色和透明兩種硅膠墊，用於緩衝飛機降落時的撞擊，並且起到保護電機線的作用，請自行選擇一種安裝。效果如下圖所示。

![](/assets/img/user-guide-5-1-0.jpg)

## 遙控器安裝
你拿到Crazepony的包裹的時候，需要自行安裝遙控器搖桿帽，沒有左右之分。

將2.4G模塊安裝到遙控器上的排針插座上。模塊方向向外。

## 遙控器操作
* 將遙控器開關推到ON。
* 將飛機的開關推到ON，LED開始進入一系列的閃爍變化，飛控開始初始化。最後如果尾部兩個LED閃爍，則可以進入下面的解鎖試飛。否則，請進入異常處理部分，具體查看下面的Crazepony燈語章節。
* 解鎖試飛。左手油門低到最低同時右手橫滾拉到最左邊，解鎖油門。解鎖成功，飛機電機將怠速旋轉。
* 解鎖成功後，默認是定高飛行模式，油門通道控制垂直方向的速度，緩慢推油門，四軸將開始上升，拉到油門中位以下則下降。
* 降落操作，可以使四軸下降至地面，然後，按“+”號鍵上鎖，關閉電機。

注意：默認飛行模式為無頭、定高飛行模式（飛機記錄起飛的方向，飛行過程中，飛機響應搖桿的方向，始終以起飛時的方向為準，即俯仰角打前，飛機就往前飛，沒有機頭機尾的區別）


## 安卓手機操作
官網下載app，並且安裝。

* 將飛機的開關推到ON，LED開始進入一系列的閃爍變化，飛控開始初始化。
* 打開app，點擊連接
* 查找設備，第一次連接crazepony，設備名是一個叫null的設備，點擊連接此設備，會顯示出完整設備名：crazepony，PIN碼為：**1234**，連接成功後，機身的藍牙提示燈常亮
* 點擊校準按鈕，此時M1和M2臂上的led燈會常亮，校準陀螺儀和加速度計，校準完成後開始閃爍，等待解鎖
* 點擊定高按鈕
* 點擊解鎖按鈕，四個電機怠速旋轉，推動油門，飛機起飛，鬆開油門，飛機懸停
* 點擊起飛/降落按鍵，可以手動降落飛機（起飛按鍵目前不支持此功能，降落按鍵有功能）

注意：用app操作時，飛行模式需要手動設置，即需要點定高和無頭才能實現相應的功能

遙控和app控制，都支持失控自動降落功能，控制距離建議不要大於20米，最好在室內練習熟練以後再去室外飛

## Crazepony燈語

Crazepony的4個臂膀各有一個藍色的LED。我們規定了部分LED閃爍的方式（燈語），用於指示飛機的狀態。燈語分為指示類型和異常類型，指示類型用於開發和調試，異常類型則必須要處理才能夠使用飛機。

* 4個LED旋轉狂閃（異常燈）
**未接收到遙控信號**。解決辦法，開啟遙控器。如果開啟遙控器未能解決，則需要先開啟遙控器，再開啟飛機重試（重燒固件時會遇到）。

* M1 M2和M3 M4交替閃爍（異常燈）
**IMU未校準提示**，需要將飛機水平放置地面上，按遙控器上“-”號鍵（或者APP上的校準按鈕）進行IMU校準。

* 4燈快閃（異常燈）
**低電壓**提示，需要充電。

* M1 M2常亮（提示燈）
**IMU啟動中**

* M1 M2快閃（提示燈）
**正常工作**

* M1臂上的LED燈會閃爍8次（提示燈）
**配置藍牙模塊**，機身的M1臂上的LED燈會閃爍8次，這裡是在檢測藍牙模塊是否正常；如果藍牙設備波特率不是設定值（115200），那麼會進入寫藍牙設備名，寫波特率，寫PIN碼的邏輯，M1,M3和M2，M4臂上的燈會交替閃爍，配置藍牙參數成功後，四個燈一起點亮1秒

* 機身的M1和M2臂上的燈會常亮3秒（提示燈）
機身的M1和M2臂上的燈會常亮3秒，此時**校準陀螺儀**


## 電量檢測和充電
飛機的四個機臂LED同時出現快速閃爍，則表示飛機電池需要充電。將飛機開關撥到Charge位置，連上usb線則可以充電。可以使用電腦，充電寶，手機充電器等為飛機進行充電。

![](/assets/img/charge.jpg)

充電時紅色LED亮起，滅掉的時候則表示充電完成。

## 常見問題

##Crazepony的遙控是屬於美國手還是日本手？
 
答：美國手。也就是說左手搖桿負責油門和偏航，右手搖桿負責俯仰和橫滾。左手搖桿上下為油門控制，左右是偏航控制；右手搖桿上下為俯仰控制，左右為橫滾控制

> 有必要科普下什麼是日本手：左手搖桿負責俯仰和偏航，右手搖桿負責油門和橫滾。是不是很彆扭？將俯仰和橫滾的控制分離開這種設計太反人類了個人覺得，但是它就是這樣一個標準沒辦法，日本人通常都會做些我們難以理解的事大家都知道的。
 

## 為什麼Crazepony的電機臀部老是被戳穿？（有人會在這個時候開始一個勁兒亂噴罵娘，我也很無奈）

答：這麼說吧，正常情況下100次起落，都不會對飛機造成任何物理結構上不可逆的毀壞。那麼，電機臀部被戳穿這種事情，屬於飛機臉先著地的意外，他的臀部是被那根軸頂穿的，空心杯電機其實很脆弱，這個我沒辦法控制，我已經盡力了。我看了國內的那些用空心杯電機的小四軸，好像都有這個問題...所以，大家提高飛行技術，是對Crazepony最直接的保護。當然，電機壞了，這種事情太好處理了，多準備些空心杯電機，只要主板沒壞，隨便怎麼折騰都可以...


## 無法垂直起飛的問題
答：小夥伴在拿到四軸飛行器試飛的時候，遇到無法垂直起飛的問題，可以從下面4個方面循序漸進，依次改進。

* 電機是否裝正了，是否有偏的問題，或者電機軸位置被纏住了（一般是頭髮，我們就遇到）。
* 整個四軸的重心問題，主要是由於電池位置。你可以根據情況稍稍移動電池位置，改變其重心。
* 通過上面辦法要做到完全的垂直起飛還是比較難。但是你可以再起飛的時候稍稍帶一點方向遙杆，體驗飛行應該是沒有問題。我們基本上是做到這一步。
* 進一步的調試方法，那就是遙杆的歸中值。也就是說，微調遙杆中間值。有一個上海的夥伴已經這樣做了，並且和我們進行了溝通，他在飛控固件中對遙感數據的接收，加入了一個校正偏移量。另外一個方法就是到遙控器上修改，其實很多玩具四軸就是這樣做的。就是在遙控器上有4個小按鍵，用於微調遙感歸中值。在我們crazepony遙控器的左下角有幾個按鍵沒有焊接，那就可以預留這個作用的。