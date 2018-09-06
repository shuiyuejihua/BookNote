# How to Win a Data Science Competition: Learn from Top Kagglers

## 数据类型
1. randomforest 不需要特征处理？机选取的特点，可以不需要做特征选择，
对数据的适应能力很强，对连续和非连续数据都适用，数据不需要规范化

2。数字处理，标准化，有利于线性模型、神经网络等。添加一些+-乘除的转换也是有利于线性模型，同时有利于树模型
，明确地添加大小特征可以导致具有文件的更健壮的模型

3、标签类编码，根据占比，可以变为频率线性模型。独热编码，会加深树的深度

4、时间类型，第一，时间分解成年月日周等；第二，距离某段时间有多少天了距离节假日；
第三，日期和日期之间的关系，注册日期登录日期

5、坐标地理位置类型；变换坐标，坐标划分。坐标显示，计算离群中心的距离。根据坐标聚类。

6、缺失值，注意隐藏的缺失值。有的缺失值已经被替换为0、-1、9999等，或者有可能为均值，
可以通过分布直方图，某个点非常多。缺失值可以删除、替换，附近点代替，统计出现频率有利于处理缺失值。
新构建特征，比如空非空。xgb不怕缺失值。训练数据最好没有缺失值，缺失值最好在特征工程部分处理

### Overview of methods
- [sklearn](http://scikit-learn.org/)  
- [K-nn](http://scikit-learn.org/stable/modules/neighbors.html)   
- [linear model](http://scikit-learn.org/stable/modules/linear_model.html)   
- [decision trees](http://scikit-learn.org/stable/modules/tree.html)   
- [H2O documentation](http://docs.h2o.ai/h2o/latest-stable/h2o-docs/data-science.html)   
- [Vowpal Wabbit repository](https://github.com/JohnLangford/vowpal_wabbit)   
- [XGBoost repository](https://github.com/dmlc/xgboost)   
- [LightGBM repository](https://github.com/Microsoft/LightGBM)   
- [Interactive demo of simple feed-forward Neural Net](http://playground.tensorflow.org/)   
- Frameworks for Neural Nets:[keras](https://keras.io/)、[tensorflow](https://www.tensorflow.org/)、[mxnet](http://mxnet.io/)、[lasagne](http://lasagne.readthedocs.io/)     
- [Example from sklearn with different decision surfaces](http://scikit-learn.org/stable/auto_examples/classification/plot_classifier_comparison.html)   
- [Arbitrary order factorization machines](https://github.com/geffy/tffm)   
 

## 探索数据

1、有基础数据领域知识，熟悉列代表的含义。对数据有大致了解，比如age一般不超过100，
以及其它逻辑，访问量不能大于点击量，有时会数据看似有bug，可以增加feature，isbug，进行统计。
为了设置验证集，需要了解数据生成的方式。如果训练集、测试集不同算法生成，那就不能单用部分训练数据作验证集。
(domain knowlege  check if data is intuitive  understand how data generated)

2、匿名数据，被hash后的数据，也许是敏感信息。可以decode，猜测其数据类型。比如randomforest，查看feature_importance，
可以pd.diff()，查看离散差，查看mean、std，反正则化，可以设置pd.set_option('max_columns', 100)，多查看几列，多观察，弄懂值类型。

3、特征探索，单个特征：plt.hist，plt.plot(x, '.')，统计描述，vaulue_counts(),isnull()；多个特征；特征间relationship，group分组
plt.scatter(x1, x2).pd.scatter_matrix(df),df.corr()/plt.matshow(),df.mean.sort_values().plot(style='.')

4、数据清理，数据集可能是一部分，也可能只给了一部分feature。重复feature、没用feature，比如常量列，labelencode后一样的重复列，
删除有利于训练速度。找出重复列，如果有很多，而且label还不同，明白为什么为重复。如果训练集很多重复值，label还不一样，说明这个比赛
很容易翻车。检查数据是否shuffle，包括行、列，否则可以 high chance to find data leakage。可以通过
df.isnull().sum(axis=0)，表示列的缺失值；df.isnull().sum(axis=1).head()，每一行的缺失值
** axis=0，across row，axis=1，across column **

5、overfitting：ShuffleSplit()，留出法；Kfold；数据太少，留一法。分层采样，对于小data、unbalance data 尤其注意  

6、数据划分策略：1，按照比例随机划分；2，基于时间进行划分。3，基于id划分。目标：train/val和train/test的划分近似。
模型预测结果会接近训练数据平均值。随机划分，当行与行之间独立，无联系时。也可以组合进行划分，接近train/test划分就行。

7、数据划分问题：1，本地验证问题：分数提不高，2，提交后排行榜问题：和排行榜划分方式不一。private leaderbord，
差异的原因，随机划分，数据量太少，分布不一样。

8、如果验证集分数:kfold 平均验证分数；在one split上调试，在其他split上测试分数。如果排行榜分数和本地分数不一样：
思考是否数据太少，是否overfitted，划分策略是否正确，train/test的分布是否一致。

9、数据泄露：ID可能是某些hash值，文件图片创建的日期(假如某些图片拍摄在另外一些图片之前)，行顺序，列顺序。


# 调参







