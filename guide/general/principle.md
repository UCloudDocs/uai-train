

# 设计原理
UAI Train平台使用GPU主机来提供AI训练的基础算力，平台利用Docker容器技术来封装训练任务，并可以对接US3和UFS作为后端数据存储。
![](/ai/uai-train/guide/ai_train综述.png)

其所涉及到的技术和产品包括包括：
  - **Docker** 容器技术 [](uai-train/basic/docker)
  - **UHub** UCloud Docker Hub [](uai-train/basic/uhub)
  - **US3**  UCloud 对象存储系统 [](uai-train/basic/ufile)
  - **UFS**   UCloud 分布式存储系统 [](uai-train/basic/ufs)
  - **UDisk**   UCloud 块存储系统 [](uai-train/basic/udisk)

## UAI Train执行的概念图
UAI Train平台在执行训练任务时，是通过将外部存储（US3、UFS、UDisk）的数据映射到Docker容器中访问。整个执行逻辑如下：
![](/ai/uai-train/guide/train-general.png)

**其中有一些固定参数：**
  - 代码入口路径：/data
  - 输入数据路径：/data/data/
  - 输出数据路径：/data/output/

**注：** 固定参数为系统默认参数，无法更改。

