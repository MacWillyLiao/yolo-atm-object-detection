# yolo-atm-object-detection
YOLOv8-based object detection for ATM

### 訓練步驟
1. 整理資料集：從 Google 照片抓 ATM 相關圖片
2. 處理資料集：用 Roboflow 標記資料集，並以 8：2 切分訓練集和測試集，並生成相關檔案（labels、.yaml）
3. 模型訓練：使用訓練集訓練後用測試集查看訓練結果

### 資料集
總共 100 張（100 images）  
訓練集：80 張  
測試集：20 張

### 訓練過程
- 模型架構：YOLOv8s、YOLOv8m
- 版本：Python 3
- 訓練環境：Google Colab（T4 GPU）
- 使用模型與參數  
  **case A**: YOLOv8s, epoch 50, batch 16  
  **case B**: YOLOv8s, epoch 80, batch 16  
  **case C**: YOLOv8s, epoch 200, batch 16  
  **case D**: YOLOv8m, epoch 200, batch 16  
  **case E**: YOLOv8m, epoch 200, batch 8  

### 訓練結果
| case | precision | recall | mAP50 | mAP50-95 | fitness |
|:------:|:------:|:------:|:------:|:------:|:------:|
| A | 0.756 | 0.788 | 0.842 | 0.655 | 0.674 |
| B | 0.844 | 0.823 | 0.848 | 0.654 | 0.674 |
| C | 0.802 | 0.848 | 0.890 | 0.665 | 0.687 |
| D | 0.877 | 0.865 | 0.898 | 0.704 | 0.723 |
| E | 0.794 | 0.819 | 0.873 | 0.691 | 0.709 |  
- best: D
