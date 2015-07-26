##[QCopterFamily](https://github.com/Hom-Wang/QCopterFamily)
QCopter，主要為打造一個適用於學術研究、學習四軸飛行器的平台，為了使平台可以實現更多元、更有效率的演算法，平台以 STM32 系列的微控制器為主，平台包含飛行控制 Flight Control、無線遙控 Remote Control、機械視覺 Machine Vision、電源管理 Power Management、電子調速 Electronic Speed Control 五大部分，並預計以不同大小機型做不同研究領域的實現。

<br>
##[QCopterFC v2.2](https://github.com/QCopter/QCopterFlightControl)
QCopterFC 是一個基於 STM32F4 的飛行控制器，可以應用於固定翼、旋翼飛行器上面，用來實現濾波、平衡、控制等演算法的平台。感測器部分使用 SmartIMU，其集成微控制器 STM32F401C、9 DOF 慣性測量元件 MPU9250 以及氣壓計 MS5611，SmartIMU 提供了兩種操作模式，讀取感測器原始資料與讀取當下姿態角度，可以透過指令選擇，無線傳輸部分使用工作於 2.4GHz 頻段的無線傳輸模組 nRF24L01P，傳輸飛行器上相關資訊，同時也可以藉由該模組從外部接收飛行控制指令，另外板上還有 Micro USB 與 Micro SD，並且引出獨立的 UART、SPI、ADC、PWM、CAN，使的 QCopterFC 可以有更多的應用、擴充。
 > QCopterMV v2.4 預計更新：  
 > ．更換微控制器 [STM32F446](http://www.st.com/web/en/catalog/mmc/SC1169/SS1577/LN1875?sc=stm32f446) 以增加處理效能  
 > ．無線傳輸部分改用 [nRF51422](https://www.nordicsemi.com/eng/Products/ANT/nRF51422) 傳輸，以相容 BLE & ANT+  
 > ．更換部分感測器，預計採用 MPU9250 + LPS25HB，詳細參考 [SmartIMU](https://github.com/Hom-Wang/SmartIMU) 更新說明。  
 > ．飛行方向標示  
 > ．微調元件間距  
 
<br>
##[QCopterMV v1.2](https://github.com/QCopter/QCopterMachineVision)
QCopteMV 是一個機系視覺開發板，用來實現影像處理的裝置，目前 QCopterMV 搭配 MT9V022 灰階的攝像頭模組，用以實現光流、特徵辨識等演算法，板子上引出 FSMC，可以外接 3.5-inch TFT 螢幕模組，實現照相機功能。
> QCopterMV v2.0 預計修改：  
>1. 微控制器改為 LQFP144 的 STM32F42xZ 或 STM32F43xZ，增加運算速度及功能。  
>2. 加入 [SDRAM](http://www.issi.com/WW/pdf/42-45S16400J.pdf)，透過 FMC 操作，用以增加影像處理時所需的 RAM。  
>3. 加入 SPI 操作的 6DOF IMU，並預計新增影像自動水平的功能。  
>4. 加入 [Microphone](http://www.analog.com/en/audiovideo-products/mems-microphones/admp522/products/product.html) 來做聲音紀錄，並預計加入聲控的功能，同時也可以用來做飛行器間的溝通。  
>5. 更改 CamSPI 名稱為 FFCSPI，並修改腳位，使其可以連接 [QFC v2.2](https://github.com/QCopter/QCopterFlightControl)、[QRC](https://github.com/QCopter/QCopterRemoteControl)、[TFT_2.2](https://github.com/OpenPCB/TFT_2.2-inch) 等裝置。  
>6. 設計 Camera 模組，使用 [MT9V034](https://www.aptina.com/products/image_sensors/mt9v034c12stc/) 8bit DCMI，預計會有灰階和彩色兩種版本，方便做不同的演算法實現。  
>7. 設計類似 [Boscam HD19 雲台](http://www.dronesvision.net/en/fpv/1333-boscam-hd19-explorerhd-fpv-camera-pan-tilt-mount-for-fixwing-aircrafts.html)的裝置，用來攜帶 QCopterMV。 ( 該結構預計透過 3D Printer 製做 )  

<br>
##[QCopterRC v1.1](https://github.com/QCopter/QCopterRemoteControl)
QCopteRC 是一個遙控器，用來與 QCopterFC 溝通、控制，是四軸飛行器的控制裝置，搭載感測器，有體感功能，板子上外接 3.5 吋螢幕，可以將四軸上的回傳回來的資訊顯示出來，並且建立操作介面。
> QCopterRC v2.0 預計修改：  
>1. 微控制器改為 LQFP100 的 STM32F42xV 或 STM32F43xV，增加運算速度。  
>2. 無線傳輸部分改用 [nRF51422](https://www.nordicsemi.com/eng/Products/ANT/nRF51422) 傳輸，以相容 BLE & ANT+。  
>3. 改成使用 [TFT_4.0-inch](https://github.com/KitSprout/TFT_4.0-inch) 800*480 螢幕，增加解析度及畫質。  
>4. 由於改成 4 吋螢幕，所以會修改整體位置，並增減部分輸入裝置功能或數量，像是按鍵數等。  
>5. 去除乙太網路功能，可能透過 FFCSPI 接口方式來擴充乙太網路模組。  

<br>
##[QCopterNano](https://github.com/QCopter/QCopterNano)
QCopterNano 是一個基於Cortex-M4 的微型四軸飛行器，飛控採用 SmartIMU，搭載 STM32F401CU 和 MPU9250，並透過 nRF24L01P 來做無線的資料傳輸、遙控，馬達座採用 3D Printer 製作。  

Design
========

##[QCopterPM](https://github.com/QCopter/QCopterPowerManage)
QCopter PowerManage 是一個電源管理裝置，預計具有無線電力傳輸的功能，具有充電管理、電壓電流檢測以及電量計算等功能。
> 目前進度：  
> 目前暫停設計...  
> 可以參考 https://github.com/Wayne-Weng/Wireless-Power

<br>
##[QCopterESC](https://github.com/QCopter/QCopterElectronicSpeedControl)
QCopter ElectronicSpeedControl 是一個無刷馬達的電子調速器，預計使用提供 CAN BUS、UART、PWM 等方式控制。
> 目前進度：  
> 目前暫停設計...  
