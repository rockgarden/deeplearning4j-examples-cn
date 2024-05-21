# 示例

## Eclipse Deeplearning4J 示例

该项目包含一组示例，演示如何使用高级 DL4J API 构建各种神经网络。DL4J 生态系统还允许用户使用 SameDiff（ND4J 库的一部分）构建神经网络，其 API 更为精细。有关这方面的更多信息，请参阅 [此处]（.../samediff-examples）。

本项目中的 pom 文件可用作用户自己项目的模板。下文简要介绍了本项目中的示例及其演示内容。这也是推荐的探索顺序。

[返回](../README_zh.md) 主版本库页面，探索 **Eclipse Deeplearning4J** 生态系统的其他特性/功能。在 [此处](https://github.com/eclipse/deeplearning4j-examples/issues) 提交问题，申请新功能。

### QUICKSTART

#### 建模示例

##### 前馈神经网络

###### 分类

* [IrisClassifier.java](./src/main/java/org/deeplearning4j/examples/quickstart/modeling/feedforward/classification/IrisClassifier.java)
介绍 RecordReaders、MultiLayerConfiguration 等重要概念的基本端到端示例

* [LinearDataClassifier.java](./src/main/java/org/deeplearning4j/examples/quickstart/modeling/feedforward/classification/LinearDataClassifier.java)
带绘图的基本端到端示例
* [MNISTSingleLayer.java](./src/main/java/org/deeplearning4j/examples/quickstart/modeling/feedforward/classification/MNISTSingleLayer.java)
分类 MNIST
* [MNISTDoubleLayer.java](./src/main/java/org/deeplearning4j/examples/quickstart/modeling/feedforward/classification/MNISTDoubleLayer.java)
用更多层对 MNIST 进行分类
* [ModelXOR.java](./src/main/java/org/deeplearning4j/examples/quickstart/modeling/feedforward/classification/ModelXOR.java)
对两个输入 XOR 函数（即简单的非线性可分离函数）建模
* [MoonClassifier.java](./src/main/java/org/deeplearning4j/examples/quickstart/modeling/feedforward/classification/MoonClassifier.java)
为分离成 "月亮" 形状的数据建模，并将结果可视化
* [SaturnClassifier.java](./src/main/java/org/deeplearning4j/examples/quickstart/modeling/feedforward/classification/SaturnClassifier.java)
为分离成 "土星" 形状的数据建模，并将结果可视化

###### 回归

* [CSVDataModel.java](./src/main/java/org/deeplearning4j/examples/quickstart/modeling/feedforward/regression/CSVDataModel.java)
带绘图的端到端基本示例
* [MathFunctionsModel.java](./src/main/java/org/deeplearning4j/examples/quickstart/modeling/feedforward/regression/MathFunctionsModel.java)
建立各种数学函数模型
* [SumModel.java](./src/main/java/org/deeplearning4j/examples/quickstart/modeling/feedforward/regression/SumModel.java)
在有噪声的合成数据集上添加模型
* [ImageDrawer.java](./src/main/java/org/deeplearning4j/examples/quickstart/modeling/feedforward/regression/ImageDrawer.java)
训练模型绘制图像！

###### 无监督

* [MNISTAutoencoder.java](./src/main/java/org/deeplearning4j/examples/quickstart/modeling/feedforward/unsupervised/MNISTAutoencoder.java)
如何构建自动编码器的基本介绍

##### 卷积神经网络

* [LeNetMNIST.java](./src/main/java/org/deeplearning4j/examples/quickstart/modeling/convolution/LeNetMNIST.java)
用于手绘数字分类的经典 LeNet 示例（MNIST）
* [LeNetMNISTReLu.java](./src/main/java/org/deeplearning4j/examples/quickstart/modeling/convolution/LeNetMNISTReLu.java)
与上述相同，略有修改
* [CIFARClassifier.java](./src/main/java/org/deeplearning4j/examples/quickstart/modeling/convolution/CIFARClassifier.java)
对 CIFAR 数据集进行分类
* [CenterLossLeNetMNIST.java](./src/main/java/org/deeplearning4j/examples/quickstart/modeling/convolution/CenterLossLeNetMNIST.java)
在 MNIST 上使用中心损失模型训练嵌入

##### 循环神经网络

* [UCISequenceClassification.java](./src/main/java/org/deeplearning4j/examples/quickstart/modeling/recurrent/UCISequenceClassification.java)
对 UCI 句法控制时间序列数据集进行时间序列（序列）分类
* [MemorizeSequence.java](./src/main/java/org/deeplearning4j/examples/quickstart/modeling/recurrent/MemorizeSequence.java)
训练 RNN 以记忆字符序列
* [RNNEmbedding.java](./src/main/java/org/deeplearning4j/examples/quickstart/modeling/recurrent/RNNEmbedding.java)
使用嵌入层（EmbeddingLayer）（相当于使用具有单次输入表示的密集层）作为 RNN 的第一层
* [VideoFrameClassifier.java](./src/main/java/org/deeplearning4j/examples/quickstart/modeling/recurrent/VideoFrameClassifier.java)
对视频帧中出现的形状进行分类。演示如何在单个神经网络中结合 RNN、CNN 和全连接密集层。这是一个耗费内存的示例。你需要至少 7G 的堆外内存。请参阅 [此处](<https://deeplearning4j.konduit>).
