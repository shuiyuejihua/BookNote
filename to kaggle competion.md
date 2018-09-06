# How to Win a Data Science Competition: Learn from Top Kagglers

## ��������
1. randomforest ����Ҫ����������ѡȡ���ص㣬���Բ���Ҫ������ѡ��
�����ݵ���Ӧ������ǿ���������ͷ��������ݶ����ã����ݲ���Ҫ�淶��

2�����ִ�����׼��������������ģ�͡�������ȡ����һЩ+-�˳���ת��Ҳ������������ģ�ͣ�ͬʱ��������ģ��
����ȷ����Ӵ�С�������Ե��¾����ļ��ĸ���׳��ģ��

3����ǩ����룬����ռ�ȣ����Ա�ΪƵ������ģ�͡����ȱ��룬������������

4��ʱ�����ͣ���һ��ʱ��ֽ���������ܵȣ��ڶ�������ĳ��ʱ���ж������˾���ڼ��գ�
���������ں�����֮��Ĺ�ϵ��ע�����ڵ�¼����

5���������λ�����ͣ��任���꣬���껮�֡�������ʾ��������Ⱥ���ĵľ��롣����������ࡣ

6��ȱʧֵ��ע�����ص�ȱʧֵ���е�ȱʧֵ�Ѿ����滻Ϊ0��-1��9999�ȣ������п���Ϊ��ֵ��
����ͨ���ֲ�ֱ��ͼ��ĳ����ǳ��ࡣȱʧֵ����ɾ�����滻����������棬ͳ�Ƴ���Ƶ�������ڴ���ȱʧֵ��
�¹�������������շǿա�xgb����ȱʧֵ��ѵ���������û��ȱʧֵ��ȱʧֵ������������̲��ִ���

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
- Frameworks for Neural Nets:[keras](https://keras.io/)��[tensorflow](https://www.tensorflow.org/)��[mxnet](http://mxnet.io/)��[lasagne](http://lasagne.readthedocs.io/)     
- [Example from sklearn with different decision surfaces](http://scikit-learn.org/stable/auto_examples/classification/plot_classifier_comparison.html)   
- [Arbitrary order factorization machines](https://github.com/geffy/tffm)   
 

## ̽������

1���л�����������֪ʶ����Ϥ�д���ĺ��塣�������д����˽⣬����ageһ�㲻����100��
�Լ������߼������������ܴ��ڵ��������ʱ�����ݿ�����bug����������feature��isbug������ͳ�ơ�
Ϊ��������֤������Ҫ�˽��������ɵķ�ʽ�����ѵ���������Լ���ͬ�㷨���ɣ��ǾͲ��ܵ��ò���ѵ����������֤����
(domain knowlege  check if data is intuitive  understand how data generated)

2���������ݣ���hash������ݣ�Ҳ����������Ϣ������decode���²����������͡�����randomforest���鿴feature_importance��
����pd.diff()���鿴��ɢ��鿴mean��std�������򻯣���������pd.set_option('max_columns', 100)����鿴���У���۲죬Ū��ֵ���͡�

3������̽��������������plt.hist��plt.plot(x, '.')��ͳ��������vaulue_counts(),isnull()�����������������relationship��group����
plt.scatter(x1, x2).pd.scatter_matrix(df),df.corr()/plt.matshow(),df.mean.sort_values().plot(style='.')

4�������������ݼ�������һ���֣�Ҳ����ֻ����һ����feature���ظ�feature��û��feature�����糣���У�labelencode��һ�����ظ��У�
ɾ��������ѵ���ٶȡ��ҳ��ظ��У�����кܶ࣬����label����ͬ������ΪʲôΪ�ظ������ѵ�����ܶ��ظ�ֵ��label����һ����˵���������
�����׷�������������Ƿ�shuffle�������С��У�������� high chance to find data leakage������ͨ��
df.isnull().sum(axis=0)����ʾ�е�ȱʧֵ��df.isnull().sum(axis=1).head()��ÿһ�е�ȱʧֵ
** axis=0��across row��axis=1��across column **

5��overfitting��ShuffleSplit()����������Kfold������̫�٣���һ�����ֲ����������Сdata��unbalance data ����ע��  

6�����ݻ��ֲ��ԣ�1�����ձ���������֣�2������ʱ����л��֡�3������id���֡�Ŀ�꣺train/val��train/test�Ļ��ֽ��ơ�
ģ��Ԥ������ӽ�ѵ������ƽ��ֵ��������֣���������֮�����������ϵʱ��Ҳ������Ͻ��л��֣��ӽ�train/test���־��С�

7�����ݻ������⣺1��������֤���⣺�����᲻�ߣ�2���ύ�����а����⣺�����а񻮷ַ�ʽ��һ��private leaderbord��
�����ԭ��������֣�������̫�٣��ֲ���һ����

8�������֤������:kfold ƽ����֤��������one split�ϵ��ԣ�������split�ϲ��Է�����������а�����ͱ��ط�����һ����
˼���Ƿ�����̫�٣��Ƿ�overfitted�����ֲ����Ƿ���ȷ��train/test�ķֲ��Ƿ�һ�¡�

9������й¶��ID������ĳЩhashֵ���ļ�ͼƬ����������(����ĳЩͼƬ����������һЩͼƬ֮ǰ)����˳����˳��


# ����







