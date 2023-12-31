# 多轮对话数据收集



## 1.**任务目标** 

构建一个高质量的多轮对话数据集，以用于训练和评估大语言模型。该数据集具有较低的噪声和更好的主题集中性。

## 2.**数据来源** 

 收集来自微信聊天记录、电影、电视剧、小品剧本、评论、问答等不同来源的对话数据。确保获取这些数据的方式合法合规，尊重版权和隐私法规。 

## 3.**数据清洗和预处理** 

数据集可能包含大量非对话性信息，如图片、表情符号、链接等。因此，需要进行数据清洗和预处理，以去除这些噪声并提取有用的文本信息。确保对话数据的格式一致，并标识对话角色。 

**主题归档：** 根据对话内容、关键词或ChatGPT生成的主题标签将对话数据归档到不同的主题分类中。 

## 4.**对话组织和结构** 

确定多轮对话的组织和结构。考虑对话的逻辑性和一致性，确保每个对话都有清晰的上下文和连贯性。

希望收集的多轮对话数据以一问一答的形式呈现，但实际情况中一个人连续说了很多句话的情况，用一下方法处理数据：

​	**拆分连续对话：** 将连续对话拆分成多个一问一答的片段。例如，如果一人连续说了3句话，可以将其拆分成3个对话片段，每个片段包含一句问题和一句回答。这样可以保持一问一答的格式。

​	**合并连续对话：** 如果连续对话的内容紧密相关，可以选择将其合并为一个对话片段，包含多轮问题和回答。这样可以保留对话的上下文和连贯性。 

 **人工检查和润色：** 进行人工检查和润色，以确保每个问答对都符合对话逻辑。人工检查可以对不符合要求的问答对进行调整或修正。 

## 5.**交互次数**

多轮对话通常包含3到10个交互会比较常见 ，但也可以根据任务目标、话题复杂性和对话自然性适当增加或减少。

要保持对话的合理性和自然性：真实的对话通常是自然而流畅的，交互次数取决于参与者的需要和反应。模拟真实对话时，要尊重自然的交流节奏。 

##  6.**数据注标** 

- **情感分类和初步标注：** 使用情感分类模型（如ChatGPT）对多轮对话中的每一轮的每一句对话进行初步的情感分类。根据模型输出，初步标注每句话的情感标签
-  emotion_labels = ["Anger", "Disgust", "Fear", "Happiness", "Sadness", "Surprise", "Neutral", "Frustrated", "Excited", "Other"]

-  **标注说明**

   unlabel_data文件中的json文件是没有进行情感标注的。
   
   label_data文件夹中的json文件是进行过情感标注的，按照情感标签emotion_labels = ["Anger", "Disgust", "Fear", "Happiness", "Sadness", "Surprise", "Neutral", "Frustrated", "Excited", "Other"]的索引保存。
   
   gpt判断不出来的标注为 Other 
   
   "Anger": 0
   
   "Disgust": 1
   
   "Fear" : 2
   
   "Happiness": 3
   
   "Sadness" 4
   
   "Surprise": 5
   
   "Neutral" : 6
   
   "Frustrated": 7
   
   "Excited": 8
   
   "Other": 9

- **人工情感标注：** 经过初步标注后，对数据进行人工情感标注，确保数据的质量和一致性。人工标注员对每句话的情感进行确认和调整。

   人工标注可能**重点**需要看分类结果为6的"Netural"

- **数据平衡：** 确保不同情感类别的问答对数量相对平衡，以防止数据集倾斜。 

## 7.**数据分割** 

将收集的数据划分为训练集、验证集和测试集，以便用于模型训练和评估。

## 8.**数据存储和备份** 

将处理后的数据存储在JSON对象中，确保数据的安全性和可访问性。






