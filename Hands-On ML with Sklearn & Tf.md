# Hands-On Machine Learning with Scikit-Learn & TensorFlow

## 机器学习系统不同方式分类

1. 监督非监督学习  

2. 批量 & 在线学习  
批量：离线的小批次数据训练学习，对于新数据还是重头开始  
在线：小批次训练数据，用学习率进行控制，新数据接着训练    

3. 基于实例 & 基于模型学习  
基于实例：已经标记好的数据，当新数据加入后，计算之间的距离、相关性等判断  
基于模型：将数据建立模型，对新数据进行预测

## 主要面临的问题  

1. 训练数据不足  

2. 训练数据没有真实反应实际情况，比如数据分布在最右边只有几个点，
而左边集中大量的点，结果模型将把最右边的几个点看作异常值处理掉，泛化能力低  

3. 过拟合、欠拟合：可以剔除一些相关性高的特征，减少过拟合  

## 模型训练验证

1. 数据集分为3部分，train/val/test，就在train上训练val上测试模型，挑个好的，
test用来测试最终模型结果，只能用一次；多次使用，最后模型连test也过拟合了，泛化能力不知道。  


## 机器学习完整项目

1. Frame the problem.  
2. Get the data.  
3. Discover and visualize the data to gain insights.  
4. Prepare the data for Machine Learning algorithms.  
5. Select a model and train it.  
6. Fine-tune your model.  
7. Present your solution.  
8. Launch, monitor, and maintain your system.  

### Fram the problem
定义问题，知道问题是什么  

思考：  

专业术语怎么定义这个问题、打算怎么去解决、有没有现成的类似的模型、问题分类(回归、分类、在线、线下...)、
模型评价方法、评价方法和业务需求一致么(比如模型用f分数，业务是准确率)、直觉经验有没有效果

### Get the data
能自动化收集最好   

思考：  

需要哪些数据、需要多少数据、查找并记录在哪能找到data、是否 要担法律风险，需要获取授权么、
转换数据类型、删除敏感数据，脱敏处理、确认数据格式类型、分出一部分作为test最终数据

### Explore the data
尝试咨询数据内容相关的专业人士，更好的理解数据，多网上查找相关专业知识  

思考：  

创建train数据副本，备份、建立jupyternotebook保存探索记录、对每个特征进行分析、target特征、
数据可视化分析、分析特征之间的相关性、如何手动解决这个问题、确定数据需要做哪些变换、
是否需要采集额外的数据、记录你分析结果

### Prepare the Data
注意原数据备份，数据变换写成方法方便调用  

思考：  

1. 数据清理：异常值、缺失值  

2. 选择特征，删除没用的  

3. 特征工程：连续变离散、拆分特征、特征变换(log倾斜值、sqrt、$x^2$...)、聚合新特征 、降维 

3. 特征缩放：标准化、归一化、均值化

