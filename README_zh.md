# 指导

如需支持，请访问
<https://community.konduit.ai>

我们不会经常监控该版本库的 github 问题。

## 简介

**Eclipse Deeplearning4J** (DL4J) 生态系统是一组项目，旨在支持基于 JVM 的深度学习应用程序的所有需求。这意味着要从原始数据开始，从任何地方、任何格式的数据加载和预处理，到构建和调整各种简单和复杂的深度学习网络。

DL4J 堆栈包括

- **DL4J**： 用于构建具有各种层（包括自定义层）的多层网络（MultiLayerNetworks）和计算图（ComputationGraphs）的高级应用程序接口。支持从 h5 导入 Keras 模型，包括 tf.keras 模型（截至 1.0.0-M2），还支持在 Apache Spark 上进行分布式训练
- **ND4J**： 通用线性代数库，包含 500 多种数学、线性代数和深度学习操作。ND4J 基于高度优化的 C++ 代码库 LibND4J，提供 CPU（AVX2/512）和 GPU（CUDA）支持，并通过 OpenBLAS、OneDNN (MKL-DNN)、cuDNN、cuBLAS 等库进行加速。
- **SameDiff** ： 作为 ND4J 库的一部分，SameDiff 是我们的自动区分/深度学习框架。SameDiff 采用基于图（先定义后运行）的方法，类似于 TensorFlow 的图模式。计划采用急迫图（TensorFlow 2.x eager/PyTorch）执行图。SameDiff 支持导入 TensorFlow 冻结模型格式 .pb（protobuf）模型。计划导入 ONNX、TensorFlow SavedModel 和 Keras 模型。Deeplearning4j 还完全支持 SameDiff，可轻松编写自定义层和损失函数。
- **DataVec**： 机器学习数据的 ETL，支持多种格式和文件（HDFS、Spark、图像、视频、音频、CSV、Excel 等）。
- **LibND4J** ： 支撑一切的 C++ 库。有关 JVM 如何访问本地数组和操作的更多信息，请参阅 [JavaCPP](https://github.com/bytedeco/javacpp)

DL4J 生态系统中的所有项目都支持 Windows、Linux 和 macOS。硬件支持包括 CUDA GPU（10.0、10.1、10.2，OSX 除外）、x86 CPU（x86_64、avx2、avx512）、ARM CPU（arm、arm64、armhf）和 PowerPC（ppc64le）。

## 前提条件

本示例软件仓库由多个独立的 Maven Java 项目组成，每个项目都有自己的 pom 文件。Maven 是 Java 项目常用的构建自动化工具。pom.xml文件的内容决定了配置。请阅读有关如何配置 Maven 的更多信息 [此处](https://deeplearning4j.konduit.ai/config/maven)。

用户还可以参考[提供的简单示例项目](./mvn-project-template/pom.xml)，从零开始创建一个简洁的项目。

构建工具被认为是标准的软件工程最佳实践。除此之外，DL4J 生态系统中的项目所带来的复杂性也使得依赖关系难以手动管理。DL4J 生态系统中的所有项目都可以与 Gradle、SBT 等其他构建工具一起使用。有关这方面的更多信息，请参阅 [此处](https://deeplearning4j.konduit.ai/config/buildtools)。

## 支持

有关示例的帮助，请访问我们的[支持论坛](https://community.konduit.ai/)

1.0.0-beta7 及更早版本的用户请注意，为反映框架方向的变化，部分示例和模块已被移除。
框架方向的变化。请参阅我们的 [此处](https://community.konduit.ai/t/upcoming-removal-of-modules-and-roadmap-changes/1240) 并发表评论。

如果您需要解决可能缺失的问题、
请随时在论坛上发帖，我们将竭尽所能为您提供帮助。

## 示例内容

项目基于所含示例向用户展示的功能，而不一定是 DL4J 栈中的哪个库。

项目中的示例一般分为 "快速入门" 和 "高级" 两种。

每个项目的 README 还列出了其中包含的所有示例，并推荐了探索这些示例的顺序。

- [dl4j-examples](dl4j-examples/README.md)
该项目包含一组示例，演示如何使用高级 DL4J API 构建各种神经网络。
其中一些示例是端到端的，即从原始数据开始，对其进行处理，然后在其上构建和训练神经网络。

- [tensorflow-keras-import-examples](tensorflow-keras-import-examples/README.md)
该项目包含一组示例，演示如何将 Keras h5 模型和 TensorFlow frozen pb 模型导入 DL4J 生态系统。一旦导入到 DL4J，这些模型就可以像其他 DL4J 模型一样处理，这意味着您可以继续在它们上运行训练，或使用迁移学习 API 对它们进行修改，或者直接在它们上运行推理。

- [分布式训练示例](dl4j-distributed-training-examples/README.md)
该项目包含一组示例，演示如何在 Apache Spark 上使用 DL4J 进行分布式训练、推理和评估。DL4J 分布式训练采用了一种 混合异步 SGD 方法--更多详情可参见分布式深度学习文档 [此处](https://deeplearning4j.konduit.ai/distributed-deep-learning/intro)

- [cuda-specific-examples](cuda-specific-examples/README.md)
该项目包含一组示例，演示如何利用多 GPU 进行神经网络的数据并行训练以提高性能。

- [samediff-examples](samediff-examples/README.md) 该项目包含一组演示 SameDiff API 的示例。SameDiff（ND4J 库的一部分）可用于构建较低级别的自动区分计算图。SameDiff API 与 DL4J API 的类似之处在于低级的 TensorFlow API 与抽象级别更高的 Keras API。

- [data-pipeline-examples](data-pipeline-examples/README.md)
该项目包含一组示例，演示如何加载、拆分和预处理各种格式的原始数据，以构建可序列化（因而可重现）的 ETL 管道。

- [nd4j-ndarray-examples](nd4j-ndarray-examples/README.md)
该项目包含一组示例，演示如何操作 NDArrays。这里演示的 ND4J 功能可类比于 NumPy。

- [rl4j-examples](rl4j-examples/README.md)
本项目包含使用 DL4J 中的强化学习库 RL4J 的示例。

- [android-examples](android-examples/README.md)
该项目包含一个 Android 示例项目，展示了在 Android 应用程序中使用 DL4J 的情况。

## 反馈与贡献

虽然这些示例并未涵盖 DL4J 的所有功能，但其目的是涵盖大多数用户（初学者和高级用户）所需的功能。 如果您有反馈意见或功能需求，但此处未涵盖，请提交问题 [此处](https://github.com/eclipse/deeplearning4j-examples/issues)。您也可以通过我们的[社区论坛](https://community.konduit.ai/)提问。
我们欢迎来自社区的贡献。更多信息请参阅 [此处](CONTRIBUTORS.md)
我们**喜欢**您的意见。干杯

## 其它

添加平台依赖，包含Linux和macos：

```xml
<dependency>
    <groupId>org.nd4j</groupId>
    <artifactId>nd4j-native-platform</artifactId>
    <version>1.0.0-M2</version>
</dependency>
```
