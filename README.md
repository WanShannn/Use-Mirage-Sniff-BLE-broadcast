# Use-Mirage-Sniff-BLE-broadcast
使用 Mirage 搭配 HackRF One 搜尋 BLE 的 broadcast 封包。

## **環境&工具**
* 一台DragonOS Linux
* 一台HackRF One

## **工具使用方法**
* step1：到Mirage的資料夾下並執行程式
    > ```shell
    > cd /usr/src/mirage/
	> sudo ./mirage_launcher
    > ```
    > ![image](https://github.com/WanShannn/Use-Mirage-Sniff-BLE-broadcast/blob/main/result/1.png)
* step2：列出模組清單
    > ```shell
    > list
    > ```
    > ![image](https://github.com/WanShannn/Use-Mirage-Sniff-BLE-broadcast/blob/main/result/2-1.png)
	
## **查看與設備相關的資訊**
* step1：重複執行`工具使用方法`的步驟
* step2：尋找到bluetooth模組
    > ![image](https://github.com/WanShannn/Use-Mirage-Sniff-BLE-broadcast/blob/main/result/2-2.png)
* step4：使用ble_info模組
    > ```shell
    > load ble_info
    > ```
    > ![image](https://github.com/WanShannn/Use-Mirage-Sniff-BLE-broadcast/blob/main/result/3-1.png)
* step5：查看模組所需的參數
  * 在Name中會有此模組所有的參數清單，可根據需求做設定  
    > ```shell
    > args
    > ```
    > ![image](https://github.com/WanShannn/Use-Mirage-Sniff-BLE-broadcast/blob/main/result/3-2.png)
* step6：設定參數
  * 這邊將hackrf設備設定到INTERFACE上  
    > ```shell
    > set INTERFACE hackrf
    > ```
    > ![image](https://github.com/WanShannn/Use-Mirage-Sniff-BLE-broadcast/blob/main/result/3-3.png)
* step7：執行 
    > ```shell
    > run
    > ```
    > ![image](https://github.com/WanShannn/Use-Mirage-Sniff-BLE-broadcast/blob/main/result/4.png)

## **查看附近得藍芽設備**
* step1：重複執行`工具使用方法`的步驟
* step2：尋找到bluetooth模組
    > ![image](https://github.com/WanShannn/Use-Mirage-Sniff-BLE-broadcast/blob/main/result/2-2.png)
* step4：使用ble_scan模組
    > ```shell
    > load ble_scan
    > ```
    > ![image](https://github.com/WanShannn/Use-Mirage-Sniff-BLE-broadcast/blob/main/result/5-1.png)
* step5：查看模組所需的參數
  * 在Name中會有此模組所有的參數清單，可根據需求做設定  
    > ```shell
    > args
    > ```
    > ![image](https://github.com/WanShannn/Use-Mirage-Sniff-BLE-broadcast/blob/main/result/5-2.png)
* step6：設定參數
  * 這邊將hackrf設備設定到INTERFACE上  
    > ```shell
    > set INTERFACE hackrf
    > ```
    > ![image](https://github.com/WanShannn/Use-Mirage-Sniff-BLE-broadcast/blob/main/result/5-3.png)
* step7：執行
    > ```shell
    > run
    > ```
    > ![image](https://github.com/WanShannn/Use-Mirage-Sniff-BLE-broadcast/blob/main/result/6-1.png)
	
## **scan BLE 的 broadcast方法 (使用ble_sniff模組)**
* step1：重複執行`工具使用方法`的步驟
* step2：尋找到ble模組
    > ![image](https://github.com/WanShannn/Use-Mirage-Sniff-BLE-broadcast/blob/main/result/2-3.png)
* step4：使用ble_sniff模組
    > ```shell
    > load ble_sniff
    > ```
    > ![image](https://github.com/WanShannn/Use-Mirage-Sniff-BLE-broadcast/blob/main/result/7-1.png)
* step5：查看模組所需的參數
  * 在Name中會有此模組所有的參數清單，可根據需求做設定  
    > ```shell
    > args
    > ```
    > ![image](https://github.com/WanShannn/Use-Mirage-Sniff-BLE-broadcast/blob/main/result/7-2.png)
* step6：設定參數
  * 這邊將hackrf設備設定到INTERFACE上，並設定SNIFFING的模式  
    > ```shell
    > set INTERFACE hackrf
    > set SNIFFING_MODE advertisements
    > ```
    > ![image](https://github.com/WanShannn/Use-Mirage-Sniff-BLE-broadcast/blob/main/result/7-3.png)
* step7：執行  
    > ```shell
    > run
    > ```
    > ![image](https://github.com/WanShannn/Use-Mirage-Sniff-BLE-broadcast/blob/main/result/8.png)
	
## **References**
* https://www.youtube.com/watch?v=uGsAbTMsYME
* https://homepages.laas.fr/rcayre/mirage-documentation/blemodules.html#id91
