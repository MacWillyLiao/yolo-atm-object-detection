# yolo-atm-object-detection
YOLOv8-based object detection for ATM

## 訓練步驟
1. 整理資料集：從 Google 照片抓 ATM 相關圖片
2. 處理資料集：用 Roboflow 標記資料集，並以 8：2 切分訓練集和測試集，並生成相關檔案（labels、.yaml）
3. 模型訓練：使用訓練集訓練後用測試集查看辨識結果

## 資料集
總共 100 張（100 images）
訓練集：80 張
測試集：20 張

## 訓練過程
- 模型架構：YOLOv8s、YOLOv8m
- 版本：Python 3
- 訓練環境：Google Colab（T4 GPU）
- 使用模型與參數
>>A: YOLOv8s, epoch 50, batch 16
>>B: YOLOv8s, epoch 80, batch 16
>>C: YOLOv8s, epoch 200, batch 16
>>D: YOLOv8m, epoch 200, batch 16
>>E: YOLOv8m, epoch 200, batch 8

## 訓練結果
A: precision 0.756, recall 0.788, mAP50 0.842, mAP50-95 0.655, fitness 0.674
B: precision 0.844, recall 0.823, mAP50 0.848, mAP50-95 0.654, fitness 0.674
C: precision 0.802, recall 0.848, mAP50 0.890, mAP50-95 0.665, fitness 0.687
D: precision 0.877, recall 0.865, mAP50 0.898, mAP50-95 0.704, fitness 0.723
E: precision 0.794, recall 0.819, mAP50 0.873, mAP50-95 0.691, fitness 0.709
* best: D
