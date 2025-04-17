# 数据归约作业-泰塔尼克号幸存预测
[github 仓库](https://github.com/historyer-1/titanic-.git)
## 第一步，数据集读入和处理

用`data_reduced=data.drop(columns=columns_to_drop,axis=1)`删除了不需要的列。
 
查看了数据的缺失值，并用**中位数**填充了**年龄**和**票价**的缺失值

## 第二步 进行数据转换

对*Sex*列进行了**标签编码**
对*Embarked*列进行了**独热编码**
对*Age*列进行了**连续变量分箱**

接着，我对不同的数值型数据进行了**特征缩放**

## 第三步 数学建模

使用`train_test_split`划分数据集
使用`RandomForestClassifier`**随机森林** 建模
`model=RandomForestClassifier(n_estimators=10,random_state=666)`

模型准确率为1.0，考虑**过拟合**和**数据泄露**
在检查和将决策树降为5后仍为1.0，考虑**性别特征（0.843632）**对是否幸存影响过大导致预测测试完全正确
