# 四軸飛行器算法講解

本章主要是Crazepony核心的算法講解。其中最重要的就是姿態解算部分內容。

姿態解算是指把陀螺儀、加速度計、羅盤等數據融合在一起，得出飛行器的空中姿態，也叫做姿態融合。姿態解算的過程，涉及到傳感器數據讀取與濾波，四元數與旋轉，姿態解算框架，長期融合/快速融合。
