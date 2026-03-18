# 115年科專-雲科程式碼交接事項

## 1. 完整程式碼與相關檔案

### (1)  源碼
* 包含所有的程式碼檔案 
ex: 
```
.
├── src/                # 原始程式碼
├── tests/              # 測試腳本
├── docs/               # 技術文件、操作手冊
├── config/             # 配置文件（如 .env ）
├── models/             # 預訓練模型
├── data/               # 範例數據
├── requirements.txt    # Python 環境與套件
└── README.md           # 專案概述
```
### (2) 註解與說明
* 每個函式的解釋邏輯
```
ex:
'''
a add b

Parameters:
    a : int number
    b : int number
'''
def function1(int a,int b):
    return a+b
```

### (3) 依賴與環境
* 版本套件 : requirements.txt 或 package.json
* 環境設定 : .env 或 docker-compose.yml
以上版本已所需為主，未用到之套件請別加入~

### (4) 資料收集&處理
* 環境變數
ex:
![LINE_ALBUM_2024.05.24_240524_1](https://hackmd.io/_uploads/BkCX2Jt81g.jpg)
    * 鏡頭 : FX17，垂直拍攝樣本
    * 燈光 : 6顆鹵素燈，與地面夾角65度
    * 與樣本距離 : 19公分
    * 平台移動速度 : 每秒5公分
    * 其他外在因素 : 有加玻璃蓋住樣本 或 無

* 資料型態與標記
ex:
    1. 高光譜掃描後取得raw、hdr檔案
    2. 選取特徵區域，轉成npy檔案 (請附上方法、參數)
    3. 轉mat讀取訓練模型 (請附上方法、參數)
    4. 資料筆數
    
## 2. 技術文件 (Word、ppt)
### (1) 系統說明書
* 簡介系統功能、架構、模組設計與邏輯流程
```
ex:
a.py : 前處理 (PCA)
b.py : 模型訓練 (CNN)
c.py : 介面應用 (flask)
操作順序是a.py -> b.py -> c.py
```
### (2) API文件 (Word、ppt、READMD.md)
* 需附上完整的API規範，包括端點、請求參數、返回值
* 訓練當下的GPU型號、記憶體空間

#### ex: 輸入 train.py 

```
cmd : python3 train.py .\a.png .\b.png --size 259 --epoch 100 --batch_size 50

* 參數 : 輸入a、b圖片，輸出大小(--size)259，epoch 100次...
* 更多參數說明可參閱train.py註解
```
#### 輸出 output.json
```
{
    "data": [
        {
            "id": 1,
            "name": "example",
            "value": 123
        },
        {
            "id": 2,
            "name": "test",
            "value": 456
        }
    ],
    "total": 2
}
* 參數 : id 編號
        name 名稱
        value 辨識結果
        total 總筆數
```
### (3) 操作手冊 (Word、ppt、READMD.md)
* 詳細說明如何安裝、配置和執行程式
* 包括啟動系統所需的指令與步驟

#### 1. 如果是用EXE檔案操作 : 

ex : 五鈴操作儀器為例
![image](https://hackmd.io/_uploads/Sywx-AuUyg.png)
![image](https://hackmd.io/_uploads/BJn3fRd8yl.png)
![image](https://hackmd.io/_uploads/S1-RGROUyl.png)
* 從開起到操作結束

#### 2. 如果是用web網頁操作 : 

ex: Visdom服務器為例
* cmd : python -m visdom.server 然後訪問 http://localhost:8097 
* 從開起到操作結束

#### 3. 介面功能說明
![S__31465489](https://hackmd.io/_uploads/BJHYPhPqbg.jpg)
示範網站:
https://yoyoisaboy.github.io/NYUST_CodeRule_For_PTRI/conductive_board_inspector.html

### (4) 測試報告 (Word、ppt、READMD.md)
* 測試的環境:電腦版本、GPU、CPU、使用的套件(requirement.txt)
* 提供測試結果說明
執行後如下圖顯示，左圖為原始圖像，右圖為訓練的標準答案(Ground truth)...
![messageImage_1735107506382](https://hackmd.io/_uploads/BJLBECdU1g.jpg)
以我們的資料fx12_Fianl hamida的辨識結果，辨識率達99%，辨識速度為5s左右
![messageImage_1735107421091](https://hackmd.io/_uploads/rJFZUR_L1x.jpg)

## 3. 交接紀錄
### (1) 交接會議
* 舉行交接會議，講解程式碼整個SOP流程
* 共兩次: 期中、期末
### (2) 後續回饋
* 提供一段時間的技術回饋（如 1~3 個月），協助處理交接方可能出現的問題
### (3) 交接清單
* 詳列所有交付內容（如程式碼、文檔、模型等），雙方簽字確認

p.s. 網站用GPT做的，我前端沒很強都可以刻成這樣，別告訴我不會歐~~ 加油!!
# 注意事項!!
* 以上內容請統一個版本，請勿分開繳交多個版本
