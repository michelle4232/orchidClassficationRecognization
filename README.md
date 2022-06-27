# **2022蘭花種類辨識**
##### 比賽網址: [https://aidea-web.tw/topic/09679060-518a-4e6f-94db-53c7d8de8138](https://tbrain.trendmicro.com.tw/Competitions/Details/20)

## 問題描述
臺灣蘭花栽培歷史悠久、品種繁多，產量及品質在國際上受到肯定，臺灣有著領先全球的蘭花育種研發，擁有世界上最多的蝴蝶蘭品種，九成的蝴蝶蘭用於出口，使其成為國內精緻農業金額首位。
但因農業生物科技的進步，大量組織苗的繁殖，影響新品種的研發，加上其它國家積極投入育種生產，育種廠商大都有其專注培養的品種，由於各蘭花品種的型態較為類似，往往需要專業人士才能進行區別，目前全球均未有蝴蝶蘭品種的辨識軟體與技術，
本競賽欲透過舉辦蘭花種類辨識及分類競賽，邀集具AI、機器學習、深度學習專長的專家與高手，訓練出高辨識率的蘭花品項影像辨識模型，除了能提升產業競爭力外，更讓社會大眾對於蘭花這類高經濟作物有更多的認識，進一步提升蝴蝶蘭的銷售與產值。


## **作法**
### 編譯環境
* google colab
* 程式語言: python

### **使用資料**
* 主辦方資料
* train.csv: 包含不同蘭花種類的照片
* lebel.csv: 共219種蘭花每種蘭花十張照片

### **方法**
* 資料前處理
  *  讀取資料並加入label
  *  生成照片至各種類五十張，並進行以下動作
    *  水平翻轉
    *  垂直翻轉
    *  旋轉30度
    *  增加顏色對比度
    *  resize成160*160
* 加入``Transfer learning``分別使用InceptionResNetV2及InceptionV3進行訓練
  * InceptionResNetV2
    * 將先前訓練ㄉ全部凍結並接著進行訓練
  * InceptionV3
    * 凍結所有留下20層並進行訓練


## **結果**
* InceptionResNetV2
  ![image](https://user-images.githubusercontent.com/62208026/175887465-00e5bcb6-f193-4692-934d-154ba559311f.png)
  ![image](https://user-images.githubusercontent.com/62208026/175887485-a1f708a6-9591-475b-bc04-5bc87139e91a.png)
  ![image](https://user-images.githubusercontent.com/62208026/175887512-2fde505b-0f48-48f0-a0bc-7f26e459cb3a.png)

* InceptionV3
  ![image](https://user-images.githubusercontent.com/62208026/175887304-1b7b5405-fbef-4817-89ba-3aed46070fcc.png)
  ![image](https://user-images.githubusercontent.com/62208026/175887337-5f2bbdce-fa77-40c4-aaaf-6524a1247970.png)
  ![image](https://user-images.githubusercontent.com/62208026/175887370-938de6eb-4cfd-4f03-86d1-16f7a951de8d.png)

