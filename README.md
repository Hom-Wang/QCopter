##[QCopterFC v2.0](https://github.com/QCopter/QCopterFlightControl)
QCopterFC 是一個基於 STM32F4 的飛行控制器，可以應用於固定翼、旋翼飛行器上面，用來實現濾波、平衡、控制等演算法的平台。板子上有 9 個自由度的慣性測量元件 MPU-9150，可以讀取加速度、角速度、磁力資訊，計算出當下的姿態角度、氣壓計 MS5611， 讀取環境氣壓，計算高度、工作於 2.4GHz 頻段的無線傳輸模組 nRF24L01，傳輸飛行器上相關資訊，同時也可以藉由該模組從外部接收飛行控制指令，另外還有 Micro USB 與 Micro SD，並且引出了 ADC、PWM、SPI、UART，使的 QCopterFC 可以有更多的應用、擴充。
> QCopterFC v2.2 預計修改：  
> 1. 減少 2 個 PWM 通道，並新增 1 個 CAN BUS ( 該 PIN 還是可以使用 PWM )  
> 2. IMU_10-DOF 改為 SmartIMU，使用 SPI 操作的 MPU-9250，來增加讀取速度。  
> 3. 將 PWM 部分的電源線連接起來，以增加擴展裝置的方便性。  
> 4. 體積將小幅度縮小。  
> 5. 更改 CamSPI 為 FFCSPI，並修改腳位，使其可以連接 QMV v2.0、QRC、TFT_2.2 等裝置。  

<br>
##[QCopterMV v1.2](https://github.com/QCopter/QCopterMachineVision)
QCopteMV 是一個機系視覺開發板，用來實現影像處理的裝置，目前 QCopterMV 搭配 MT9V022 灰階的攝像頭模組，用以實現光流、特徵辨識等演算法，板子上引出 FSMC，可以外接 3.5-inch TFT 螢幕模組，實現照相機功能。
> QCopterMV v2.0 預計修改：  
> 1. 微控制器改為 LQFP144 的 STM32F42xZ 或 STM32F43xZ，增加運算速度及功能。  
> 2. 加入 SDRAM，透過 FMC 操作，用以增加影像處理時所需的 RAM 空間。  
> 3. 加入 SPI 操作的 6DOF IMU，並預計新增影像自動水平的功能。  
> 4. 加入 Microphone 來做聲音紀錄，並預計加入聲控的功能，同時也可以用來做飛行器間的溝通。  
> 5. 更改 CamSPI 名稱為 FFCSPI，並修改腳位，使其可以連接 QFC v2.2、QRC、TFT_2.2 等裝置。  
> 6. 設計 Camera 模組，使用 MT9V034 8bit DCMI，預計會有灰階和彩色兩種版本，方便做不同的演算法實現。  
> 7. 設計類似 Boscam HD19 雲台的裝置，用來攜帶 QCopterMV。 ( 該結構預計透過 3D Printer 製做 )。  

<br>
##[QCopterRC v1.1](https://github.com/QCopter/QCopterRemoteControl)
QCopteRC 是一個遙控器，用來與 QCopterFC 溝通、控制，是四軸飛行器的控制裝置，搭載感測器，有體感功能，板子上外接 3.5 吋螢幕，可以將四軸上的回傳回來的資訊顯示出來，並且建立操作介面。
> QCopterRC v2.0 預計修改：    
> 1. 微控制器改為 LQFP144 的 STM32F42xZ 或 STM32F43xZ，增加運算速度及功能。  
> 2. 加入 SDRAM，透過 FMC 操作，增加靈活與擴充性。  
> 3. 改成使用 4 吋 800*480 螢幕，增加解析度及畫質。  
> 4. 由於改成 4 吋螢幕，所以會修改整體位置，並增減部分輸入裝置功能或數量，像是按鍵數等。  
> 5. 考慮將乙太網路功能直接透過 STM32 本身硬體實現。  

Design
========

##[QCopterWP](https://github.com/QCopter/QCopterWirelessPower)
QCopter WirelessPower 是一個具有無線電力傳輸功能的電源管理裝置，可以無線充電並管理以及計算電量等資訊。
> 目前進度：  
> 無線電力已完成，整體架構設計中 ... 
> 可以參考 https://github.com/Wayne-Weng/Wireless-Power

<br>
##[QCopterESC](https://github.com/QCopter/QCopterElectronicSpeedControl)
QCopter ElectronicSpeedControl 是一個無刷馬達的電子調速器。
> 目前進度：  
> QCopterESC PCB v1.0 版本完成，焊接測試中 ... 

<br>
<a rel="license" href="http://creativecommons.org/licenses/by-sa/3.0/tw/deed.zh_TW"><img alt="創用 CC 授權條款" style="border-width:0" src="http://i.creativecommons.org/l/by-sa/3.0/tw/88x31.png" /></a><br /><span xmlns:dct="http://purl.org/dc/terms/" property="dct:title"> QCopter_Family </span>由<a xmlns:cc="http://creativecommons.org/ns#" href="https://github.com/QCopter" property="cc:attributionName" rel="cc:attributionURL"> QCopter </a>製作，以<a rel="license" href="http://creativecommons.org/licenses/by-sa/3.0/tw/deed.zh_TW">創用CC 姓名標示-相同方式分享 3.0 台灣 授權條款</a>釋出。
