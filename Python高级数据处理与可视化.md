 ### Cluster analysis 聚类分析：以相似性为基础把相似的对象通过静态分类的方法分成不同的组别或者更多的子集
 ### K-均值算法表示以空间中K个点为中心进行聚类，对最靠近他们的对象归类。
 ### 聚类是数据挖掘描述性任务和预测性任务的一个重要组成部分。
 ### 通过k-means 即k-均值来对这些数据聚类
 ### 下面演示一个 寻找学霸的小例子：
 ![pic](https://github.com/lidan5452/Python-learning/blob/master/WeChat%20Image_20180607150436.jpg)
##### import numpy as np
##### from scipy.cluster.vq import vq,kmeans,whiten
##### list1=[88.0, 64.0, 96.0, 85.0]
##### list2=[92.0, 99.0, 95.0, 94.0]
##### list3=[91.0, 87.0, 99.0, 95.0]
##### list4=[78.0, 99.0, 97.0, 81.0]
##### list5=[88.0, 78.0, 98.0, 84.0]
##### list6=[100.0, 95.0, 100.0, 92.0]
##### data =np.array([list1, list2, list3, list4, list5, list6])  #利用numpy中的array函数，把它们生成一个data
##### whiten=whiten(data)                   #利用whiten函数 算出各列的标准差
##### centroids,_=kmeans(whiten, 2)         #对数据进行聚类, 分成2类， kmeans的返回是一个元组
##### result,_=vq(whiten,centroids)         #vq是矢量量化函数，可以对每一个数据进行归类
##### print(result)

##### 运行结果如下：
##### [0 1 1 0 0 1]
##### 可以看出   list2 3 和6有学霸潜质
