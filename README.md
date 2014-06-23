##[QCopterFC v2.2](https://github.com/QCopter/QCopterFlightControl)
QCopterFC 是一個基於 STM32F4 的飛行控制器，可以應用於固定翼、旋翼飛行器上面，用來實現濾波、平衡、控制等演算法的平台。感測器部分使用 SmartIMU，其集成微控制器 STM32F401C、9 DOF 慣性測量元件 MPU9250 以及氣壓計 MS5611，SmartIMU 提供了兩種操作模式，讀取感測器原始資料與讀取當下姿態角度，可以透過指令選擇，無線傳輸部分使用工作於 2.4GHz 頻段的無線傳輸模組 nRF24L01P，傳輸飛行器上相關資訊，同時也可以藉由該模組從外部接收飛行控制指令，另外板上還有 Micro USB 與 Micro SD，並且引出獨立的 UART、SPI、ADC、PWM、CAN，使的 QCopterFC 可以有更多的應用、擴充。

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

##[QCopterPM](https://github.com/QCopter/QCopterPowerManage)
QCopter PowerManage 是一個電源管理裝置，預計具有無線電力傳輸的功能，可以無線充電並管理以及計算電量等資訊。
> 目前進度：  
> 目前暫停設計...  
> 可以參考 https://github.com/Wayne-Weng/Wireless-Power

<br>
##[QCopterESC](https://github.com/QCopter/QCopterElectronicSpeedControl)
QCopter ElectronicSpeedControl 是一個無刷馬達的電子調速器。
> 目前進度：  
> 目前暫停設計...  
