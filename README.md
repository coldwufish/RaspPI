# Raspberry PI - 上課資料
取之於網路, 還之於網路

相關網路資源都有附上來源位址 (如果有遺漏再麻煩提醒)

持續更新中, 先放上PDF檔案. 之後會陸續寫每個檔案的大綱

# related tools
Raspbian
* offical: https://downloads.raspberrypi.org/raspbian_latest
* ubuntu mirror: http://ftp.ubuntu-tw.org/mirror/raspbian-downloads/raspbian_full/images/raspbian_full-2018-11-15/2018-11-13-raspbian-stretch-full.zip
* ubuntu mirror folder: http://ftp.ubuntu-tw.org/mirror/raspbian-downloads/raspbian_full/images/
* Google drive分流: https://drive.google.com/drive/u/1/folders/1FvYGCJkXdjXpv2uayGnVs9Mp_cPM_Ywv

SD Formatter (清除SD卡舊有的檔案系統)
 * https://www.sdcard.org/cht/downloads/formatter_4/

寫入映像檔到SD卡
* Etcher, https://www.balena.io/etcher/
  * 這個會顯示即將寫入的SD卡大小, 可以避免寫入到錯誤的磁碟 (我的隨身硬碟 QQ))
* Win32 image writer, https://sourceforge.net/projects/win32diskimager/
  * 這個除了寫入以外, 也可以讀取. 適合用來做整個系統的備份. 但寫入時要注意磁碟代號.

Notepad ++ (編輯開機設定檔)
* https://notepad-plus-plus.org/downloads/

USB TTL driver (TTL控制線驅動程式)
* http://www.prolific.com.tw/US/ShowProduct.aspx?p_id=225&pcid=41

Putty (終端機程式)
* https://the.earth.li/~sgtatham/putty/latest/x86/putty.exe

# PI4 + TTL 的 config.txt設定 
加上下面三行可以用 (裡面的檔案是PI3的設定)
```
enable_uart=1
core_freq=250
dtoverlay=miniuart-bt
```

# todo list
MQTT
* Python 用戶端程式設計 http://rocksaying.tw/archives/2016/MQTT-3-Python-clients.html
* 使用 MQTT 傳遞資料 https://jerrynest.io/using-mqtt-on-intel-edison

# 注意事項
PI3 B+ (內建wifi是2.4G/5G雙頻), 使用馬達擴充版會有硬體上的問題

(好像是內建的3.3V線路會有短路問題, 當PI3 B+ 與 馬達 一起使用會把板子燒壞 QQ

最新版的opencv在PI上面會有錯誤訊息, 可以用pip移除再安裝舊版
```
pip3 uninstall opencv-python
pip3 install opencv-python==3.4.6.27
Ref: https://github.com/EdjeElectronics/TensorFlow-Object-Detection-on-the-Raspberry-Pi/issues/67
```

# Nvidia Jetson Nano 設定心得
Nano用起來跟PI有一點像(!?), 就順便附個筆記連結在這裡 XD
https://hackmd.io/KGdNHN-lTIKqOqDiGnFVhQ?view

上次用它來做影像辨識的測試, 內容只有 環境設定+物件辨識 這兩個功能


裸機的時候要注意GPIO短路問題 (camera模組也要注意不要碰到pin腳)
