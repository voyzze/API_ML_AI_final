# 学嘢吗-生活类识别APP

| 发布日期   | 08/12/2019 |
| ---------- | ---------- |
| 主题       | 生活，识别 |
| 文件现状   | 已完成     |
| 文件持有者 | 邱麟茹     |
| 设计师     | 邱麟茹     |
| 开发者     | 邱麟茹     |
| 测试者     | 邱麟茹     |

## 一、PRD价值主张设计

### PRD1.加值宣言

- 通过**图像识别api**解决生活中所遇到的事物盲区。当用户在图像识别中碰到困难时，提供*语音搜索*供用户使用。

### PRD2.核心价值

- 基于大众对生活中许多物体认知薄弱而需要满足求知欲的情况，通过**图像识别api**的小程序解决大部分用户日常想要得知事物的识别功能，名称信息以及扩充信息反馈给用户。

### PRD3.核心价值&用户痛点

1. 在生活中，大多数人对事物是好奇的，可不知如何获取事物的信息，例如是在街道上或是乡村没有特定标注名称的植物、果蔬等等。
    - 人们遇到美的事物总是有一定的求知欲。

2. 当外出遇到一颗很漂亮的树时想知道这棵树的名称便去描述搜索也很难从无数种植物中找到。
    - 搜索引擎很难通过用户描述事物的特征，特别的动植物，给出准确的答案。

3. 外出吃饭时想知道菜品的热量，可是没有下载有关检测热量的app
    - 若在大众日常使用的app中加入图像识别的功能，会让大众更加地便利。且百度图像识别api可检测出菜品热量。

### PRD4.人工智能概率性与用户痛点/问题

1.  用户遇到会动的物体时拍照不稳定导致识别出问题
-  * _如何解决？_

     建议用户先用手机原相机拍到相对清晰的照片再上传至图像识别。

2. 有些原创独特的菜品无法识别，数据库无此菜品信息
- * _如何解决？_

     当识别不到时，建议用户输入菜品中的原材料，搜索引擎结合得出相似的菜品信息。
     
3. 当驱车驶过遇到好看的植物可不够时间拍照
- * _如何解决？_

     建议用户使用关键词描述，得出相似结果供用户选择。

### PRD5.需求列表与人工智能API加值

| Behavior                       | Issue                            | API      |
| ------------------------------ | -------------------------------- | -------- |
| 对物件进行拍照识别       | 物体会移动导致拍照模糊           | 图像识别 |
| 当图像识别不了且用户打字有困难时       |  | 语音搜索 |

## 二、原型

### 原型1.交互及界面设计

1. 首页：用户在此页面进行图像识别功能，提示用户对准目标物体。

![首页](首页.png "首页.png")

2. 拍照页面：在此页面对准目标物体后按提交键/上传图片。

![拍照](拍照.png "拍照.png")

3. 拍照识别失败：这是拍照识别失败返回的页面，提示用户可以用以下方式再次尝试。

![1识别失败](1识别失败.png "1识别失败.png")

4. 再一次拍照/上传图片识别识别：当再一次拍照/上传图片失败时，页面跳转至语音搜索页供用户使用。

![2识别失败](2识别失败.png "2识别失败.png")

5. 语音搜索识别识别：当使用语音搜索都识别失败时页面显示如下文字。

![3识别失败](3识别失败.png "3识别失败.png")

6. 识别成功：若是识别成功会跳转至此页面，内含百科名称及信息。

![结果](结果.png "结果.png")

### 原型2.信息设计

![流程图](流程图.png "流程图.png")

### 原型3.原型文档

- [产品原型交互](http://nfunm071.gitee.io/api_ml_ai)

## 三、API 产品使用关键AI或机器学习之API的输出入展示

### API1.使用水平

- [jupyter代码文件](https://github.com/voyzze/API_ML_AI_final/blob/master/API_final.ipynb)代码文件展示了使用百度图像识别中的动物识别、植物识别、果蔬识别以及通用物体识别。可看到里面所有的图片都识别出来了，而且还有概率细分、品种细分等等。最后一个通用物体api的调用，图中有8个人，可是只能识别出一个人。

- 下图是百度官网供参考的api调用返回结果，匹配相似度以分数的结果呈现。
![百度返回示例](百度返回示例.png "百度返回示例.png")

- 下两图是测试水果主体以及测试实践后的结果返回显示。可看到返回结果，它匹配了几个相似度较高的的果蔬品种，还返回地方不同说辞的名称。
![g](g.png "g.png")
![百度实践返回结果](百度实践返回结果.png "百度实践返回结果.png")

| 输入                       | 输出                            | API      |
| ------------------------------ | -------------------------------- | -------- |
| 用户对准物品进行识别      | 物体名称及百科信息           | 百度图像识别 |
| 用户对准物品进行识别       | 图像打标签/场景识别          | 阿里图像识别 |
| 用户描述物体特征   | 百度搜索结果           | 百度语音搜索 |

### API2.使用比较分析

- [百度、阿里、旷视图像文字识别](https://blog.csdn.net/wwdwjm/article/details/76608101)这是一篇图像文字识别的对比。里面作者得出结果并提出：“百度的识别率最高。”

- [阿里云图像识别产品文档](https://ai.aliyun.com/image?spm=a2c4e.11155472.1280361.261.56c1220a5Qno1r)此页面有说明阿里云产品与服务，它主要的服务是图像打标和场景识别
![阿里图像识别能力](阿里图像识别能力.png "阿里图像识别能力.png")

- [百度图像识别产品文档](https://ai.baidu.com/tech/imagerecognition)此页面是百度图像识别的产品与服务，它可以识别通用物体、场景、动物、植物、品牌logo、果蔬、菜品以及红酒，而且它识别后返回的结果是百度百科的名称和信息。
![百度图像识别能力](百度图像识别能力.png "百度图像识别能力.png")

- [jupyter对比代码文件](https://github.com/voyzze/API_ML_AI_final/blob/master/API_ML_AI_final_compare.ipynb)代码文件展示了百度和阿里云的图像识别api调用情况。百度图像识别返回结果就是名称信息及百科信息，而阿里云返回的结果则是图片注标。

**总结**： 相对于阿里云的图像识别，百度图像识别会更符合此功能想要返回的结果显示，而且百度图像识别物体的范围更广，并且有细分动物植物等专业领域的学科学名，这对于大众来说是一次很好的知识反馈。

| 公司 | API             | 定价                 |
| ---- | --------------- | ------------------------ |
| 百度 | 百度图像识别API | 500次/日的免费额度，超出按调用量计费 |
| 阿里云 | 阿里云图像识别API     | 可免费体验，计费方式有两种，后付费和预付资源包。                   |

**百度**：根据拍摄照片，识别图片内容。支持多种垂类业务场景的细粒度图像识别，精准识别超过十万种物体和场景，基于百度海量数据，持续丰富接口返回内容信息。

 *应用场景*：拍照识图、图片内容检索、相册分类、内容及广告推荐等
  
**阿里云**：支持实时识别，可识别上千种标签，覆盖日常生活各种场景，并实现自动化的视频内容检索服务、个性化推荐、内容检索服务、审查和分发。

 *应用场景*：智能相册、视频场景分析等

- 通过图像识别的识别率、计费方式、限制等对比得出百度图像识别API会更适合此次功能图像识别的调用。

### API3.使用后风险报告

| 类别     | 现在                                                           | 未来                                                     |
| -------- | -------------------------------------------------------------- | -------------------------------------------------------- |
| 图像识别 | 目前已运用在医学技术等生活方面 | 可进一步提高准确度，用于精确的技术研发方面 |
| 语音搜索 | 正在发展中，还不完善                    | 搜索行业发展的一个趋势     |

- 图像识别和语音搜索在人工智能和机器学习中都处于完善阶段，相对来说，图像识别技术会比语音搜索稍微超前一点，但两者未来发展前景应会逐步提高。

| 类别     | 选用公司 | 竞争者           |
| -------- | -------- | ---------------- | 
| 图像识别 | 百度   | 阿里云 |  
| 语音搜索 | 百度     | 微软    |

- 语音搜索目前还处于相对不完善的状态，开发对于公司来说超级困难，除非有很好的突破点。而图像识别需要的数据量很大，目前公司蛮难实现收集各类数据。
