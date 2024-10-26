113-1南華大學跨領域-人工智慧
主題:google-colab跑項目
![image](https://github.com/user-attachments/assets/9fc05739-4601-47b7-bb85-464358dae454)
點開文件(圖標)
再點選檔案名稱為「..」的資料夾(滑鼠放上去顯示的名稱叫做上一級目錄)
![image](https://github.com/user-attachments/assets/2d6652e4-ec59-4774-9fc9-67e918b350c8)
看到我們的初始位置在/content的資料夾裡
![image](https://github.com/user-attachments/assets/6368176e-13a9-4410-87ab-d5d3d7c91a02)
能看到自己的文件路徑在/content下方，但沒辦法運行
![image](https://github.com/user-attachments/assets/e21a2204-bbf0-40bf-92c7-d92c487fd7c9)
但是如果要裝載文件進去，必須加上/content(像是上方，裝載google雲端到/content下方)
所以我們運用的代碼是:
from google.colab import drive
drive.mount('/content/drive')
但如果是用:
from google.colab import drive
drive.mount('/drive')
則會造成雲端沒有在/content(下圖)
![image](https://github.com/user-attachments/assets/9117d3b4-6ed8-49b9-ac06-48ca11d8c022)
現在問題來了，我們清楚如何掛載文件到目錄裡面。但現在要回去打代碼，點不進去了怎麼辦?
可以輸入:/content/drive
![image](https://github.com/user-attachments/assets/f77018c1-09e8-4de0-b64e-5f1da0889f58)
看到下方有黑色底線，使用ctrl+滑鼠點擊
![image](https://github.com/user-attachments/assets/690666cb-3efd-40e9-bab2-01aa900fcd0c)
就會進去到drive裡面啦
