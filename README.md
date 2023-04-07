# Computer Vision in Deep Learning

## 目錄

- [背景](#背景)
    - [資料集介紹與評估方法](#資料集介紹與評估方法)
- [相關的研究進展](#資料集)
- [程式碼與內容說明](#程式碼與內容說明)


## 背景
### 資料集介紹與評估方法
- **Classification Datasets**
[CIFAR-10](https://paperswithcode.com/sota/image-classification-on-cifar-10)：由60,000張32x32的RGB圖像組成，其標籤有10種類別，如：車車、飛機、鳥...等。



## 相關的研究進展

- **Shifted Window Transformer, Swin**
Swin是一種層次化結構的Transformer網路，其是使用移位窗口來表示一張圖片。藉由將自注意力機制限制在不重疊的區域窗口，並允許跨窗口來提高效率。其補足了前一個版本 (**ViT**)於卷積特性(locality及inductive biases)上的缺點，將性能擴展到**物件偵測**及**語意分割**。並且加上Transformer原本在NLP上的優越性，使Swin成為目前CV/NLP/CV+NLP的通用主幹。

## 程式碼與內容說明

|        模型     | `SwinTransformer`          |``            |``                |
| :---:           | :---:            | :---:            | :---:            | 
|   任務   |  影像分類    |  - | -    | 
|   資料集   |  CIFAR_100    |  - | -    | 
|   檔案   |  [[1]](#SwinTransformer_CIFAR_100.ipynb)   |  -  |   -   | 

#### [1] SwinTransformer_CIFAR_100.ipynb
