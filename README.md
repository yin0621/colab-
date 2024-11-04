113-1南華大學跨領域-人工智慧
主題:google-colab跑項目

報告學生
11220016陳靖尹
11218102蘇韋綾

第一步:我們初始目錄顯示

![image](https://github.com/user-attachments/assets/9fc05739-4601-47b7-bb85-464358dae454)

點開文件(左方工具欄位圖標，參考上圖)

第二步: 

再點選檔案名稱為「..」的資料夾，滑鼠放上去顯示的名稱叫做上一級目錄(參考下圖)

![image](https://github.com/user-attachments/assets/2d6652e4-ec59-4774-9fc9-67e918b350c8)

看到我們的初始位置在 /content 的資料夾裡(參考上圖)
![image](https://github.com/user-attachments/assets/6368176e-13a9-4410-87ab-d5d3d7c91a02)

能看到自己的文件路徑在/content下方，但沒辦法運行(上圖)
![image](https://github.com/user-attachments/assets/e21a2204-bbf0-40bf-92c7-d92c487fd7c9)

第三步:

但是如果要裝載文件進去，必須加上/content(參考上圖，裝載google雲端到/content下方)
所以我們運用的代碼是:

from google.colab import drive 

drive.mount('/content/drive') 

但如果是用:

from google.colab import drive 

drive.mount('/drive') 

則會造成雲端沒有在/content(參考下圖)
![image](https://github.com/user-attachments/assets/9117d3b4-6ed8-49b9-ac06-48ca11d8c022)

第四步

現在問題來了，我們清楚如何掛載文件到目錄裡面。但現在要回去打代碼，點不進去了怎麼辦?

可以輸入:/content/drive

![image](https://github.com/user-attachments/assets/f77018c1-09e8-4de0-b64e-5f1da0889f58)

看到下方有黑色底線，使用ctrl+滑鼠點擊
![image](https://github.com/user-attachments/assets/690666cb-3efd-40e9-bab2-01aa900fcd0c)

就會進去到drive裡面啦~

第五步

import os

from google.colab import drive

drive.mount('/content/drive')

![image](https://github.com/user-attachments/assets/e47fcc58-a786-490d-84e6-47770fa607c9)
上圖為colab掛載google雲端之代碼

接下來介紹一些colab使用的命令:

![image](https://github.com/user-attachments/assets/e7cc83fd-90d3-47b3-a044-05c4a991103d)

如何對項目上傳並執行

![image](https://github.com/user-attachments/assets/8e900676-0abb-42d9-8539-168f32a7e3f3)

修改筆記本設定啟用gpu

![image](https://github.com/user-attachments/assets/9d99d76a-1f42-435c-a5ac-33ece8fefe67)

![image](https://github.com/user-attachments/assets/b1ff1a6b-d7e2-4224-88a5-b9c3aa09d29e)


接著我將zip文件類型上傳到/content文件底下(上圖)

想要解壓文件可以輸入:

!unzip /content/yolov5-master.zip -d /content/yolov5

(下圖)
![image](https://github.com/user-attachments/assets/c333b4c0-41f3-4505-972f-a479ce24050a)



如果想將已上傳的文件刪除可以運用此代碼:

!rm -rf 文件夾路勁

(備註:文件夾路徑可以右鍵點選文件夾後有一個複製路徑)

![image](https://github.com/user-attachments/assets/f103ce52-5779-4bfe-b657-66b8dc91c2f0)

我的文件就被刪除啦(上圖)

接著進入到已解縮的檔案的目錄下

輸入代碼(呈現下圖):

%cd /content/yolov5

![image](https://github.com/user-attachments/assets/9d3598f7-1ec0-444d-82db-b2e56427669c)

接著是安裝環境，輸入:

!pip install -r /content/yolov5/yolov5-master/requirements.txt

![image](https://github.com/user-attachments/assets/481ad48d-2ab3-448b-a5bb-f68ae17d8fac)

則會呈現上圖

接下來我們添加插件:%load_ext tensorboard

依照剛剛學會的再來一次(解壓、打開目錄)【下圖】

![image](https://github.com/user-attachments/assets/c5f69f02-b95f-4fb1-ad9d-a505ed5eafe5)

![image](https://github.com/user-attachments/assets/128fdf3b-b8c3-4d64-883e-8b4974e122a1)

接著輸入:%tensorboard --logdir=runs/train 運行程式(下圖)

注意!!中間不能有空格

開啟tensorboard再運行train.py程序

![image](https://github.com/user-attachments/assets/0af1a1a7-8f1e-46b3-b121-4aa44909936d)

接著我們輸入:!python train.py --rect
啟動矩陣推理訓練【顯示下圖】

![image](https://github.com/user-attachments/assets/7db23751-4aab-4e15-8d18-44bcf424d3f7)

刷新tensorboard【代碼為 : %tensorboard --logdir=runs/train】

![image](https://github.com/user-attachments/assets/2d29518e-0cbe-4a4a-890f-ba3b8314c4e1)

如果一開始tensorboard不顯示，是因為上傳的zip檔案裡面runs資料夾下train資料夾下沒有exp文件

我們在通過【!python train.py --rect】運行

![image](https://github.com/user-attachments/assets/232a9fb0-3be0-4335-b202-633c97011db8)

我們將此次訓練的內容保存在名為【exp8】的文件夾中【下圖】

![image](https://github.com/user-attachments/assets/0a6af76b-8d3c-4764-8b0f-36b0cfde1685)

tensorboard裡顯示loss的變化【下圖】

![image](https://github.com/user-attachments/assets/d524cb5b-cde8-4b28-b6af-244578660fdb)

tensorboard資料：runs/train/exp/events.out.tfevents.1678366117.03e634abd4f1.7156.0

超參數：hyp.yaml

類別實例：labels.jpg 即每個類別出現的次數

訓練結果：results.csv

**更改訓練的資料集**

運用程式碼:【!python train.py --data=data/coco.yaml】

![image](https://github.com/user-attachments/assets/c67db6e6-cc41-4c4c-b814-8c8cc3d5a847)

把得到的best.pt下載下來在yolov5專案中，把detect.py 中main函數第一個參數weights對應的權重參數檔改成這個best.pt，就可以測試結果

在Colab上運行YOLOv5模型的步驟如下：

上傳YOLOv5模型的壓縮文件（yolov5-5.0.zip）到Colab。

解壓縮文件：使用命令 !unzip /content/yolov5-5.0.zip。

切換到解壓後的目錄：使用命令 %cd /content/yolov5-5.0。

安裝依賴庫：執行 !pip install -r requirements.txt 來安裝所需的庫。

啟動TensorBoard工具來可視化學習曲線，訓練的loss等結果會記錄在 runs/train 文件夾中。

這些步驟可以幫助你順利進行YOLOv5的訓練和監控。
