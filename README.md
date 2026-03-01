# 数据工程方面情绪对话数据集获取
#### 本来是想做两种风格对话微调模型的，但后续有些麻烦，用xtuner，简要过程放pdf里，自己有兴趣复现好了

###需要安装库如下（如果有其它缺少，自行安装）：
#### pip install zhipuai sentence_transformers numpy
### 需要在智普ai开放平台注册并实名认证，创建apikey：在这里进行替换
> client = ZhipuAI(api_key="238333f13fdb4efdf39d7.GwngHUrulaFNjfgw")  # 替换为你的API Key
### 网址：https://open.bigmodel.cn/usercenter/proj-mgmt/apikeys
### test01.py 是测试获取100条温柔和毒舌风格的对话数据数据集，存放在style_chat_data.json中
### get_data.py 是获取一万条温柔和毒舌风格的对话数据集，存放在style_chat_data1.json中
### model_convert 是对数据进行归一化处理，因为原始 text2vec-base-chinese-sentence 模型缺少归一化层，导致输出的句子向量模长不等于1，计算余弦相似度时结果不准确，这个脚本是做修补作用
### cleaned_output.txt 是1000条人工筛选后的数据集
