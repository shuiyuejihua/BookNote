# 深度学习视觉

## 图片预处理

1. linear transformation 线性处理，$f = (y-y_min)*\frac{255-0}{y_max-y_min}$。结果黑的更黑，白的更白。  
2. gamma transformation 伽马变换，$f = c * x^\gamma$， 让很黑、很白的变清晰。  
3. free-form brightness transformation  
4. Histogram equalization  

5. noise 是随机的，取平均后可以消除noise
6. spatial filtering
7. 高斯分布可以减少noise，但是会模糊图形。高斯filter不会增加额外信号。高斯核在
图形边缘检测中，sigma越大，边缘越多。
8. 图形边缘可以通过对图像强度的一阶导数来识别，边缘是图像强度快速变化的点