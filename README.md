# CCL2018-Chinese-Metaphor-Analysis
CCL 2020 中文隐喻识别与情感分析任务说明与数据集  
此评测任务由两个子任务构成

#### 子任务一：中文动词隐喻识别
&emsp;&emsp;众所周知，动词在句子中扮演着重要的角色，对于中文隐喻而言更是如此，隐喻通常涉及两个概念域，其构建的基础是两个概念域之间的相似性，而动词往往表征隐喻概念实体间的相互关系，因此动词是隐喻中名词实体的概念依存体，例如：“音乐凝固了小镇的建筑。”，这个句子便运用了动词隐喻，通过动词“凝固”表征了该隐喻中实体音乐和建筑的关系。因此，该子任务旨在通过对动词及其关联的名词实体的分析，实现对中文动词隐喻的识别。

|数据类别     |数据条数 | 
| ------------ | ------- | 
| 训练集     | 4394  |
| 测试集  | 1100      |

&emsp;&emsp;该子任务提供训练集和测试集，具体数量如上表所示。
该子任务是三分类任务，标签有：动词隐喻(LABLE=1)、名词隐喻(LABLE=2)和中性(LABLE=3)。该子任务采用宏平均(Macro-averaging)进行评价。宏平均首先对每一个类的预测结果计算精确率（P）、召回率（R）以及F值，然后对所有类的F值求算术平均值。具体公式如下：  
<p align="center">
<a href="https://www.codecogs.com/eqnedit.php?latex=\inline&space;F_i=\frac{2*P_i*R_i}{P_i&plus;R_i}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\inline&space;F_i=\frac{2*P_i*R_i}{P_i&plus;R_i}" title="F_i=\frac{2*P_i*R_i}{P_i+R_i}" /></a></p>
<p align="center">
<a href="https://www.codecogs.com/eqnedit.php?latex=\inline&space;Macro\_F=\frac{1}{n}\sum^{n}_{i=1}{F_i}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\inline&space;Macro\_F=\frac{1}{n}\sum^{n}_{i=1}{F_i}" title="Macro\_F=\frac{1}{n}\sum^{n}_{i=1}{F_i}"/></a></p>

#### 子任务二：中文隐喻情感分析
&emsp;&emsp;中文隐喻的情感分析是对隐喻理解的重要部分，其旨在研究作者如何通过隐喻把文本话题的情感传递给读者，是一种更具挑战性的情感计算研究。隐喻是典型的非字面表达，常常通过隐晦、间接的语言表达情感。例如在句子“你就是个备胎”中，并没有情感词汇出现，“备胎”的字面义也没有情感因素，但其隐喻义“排在第二的替补”却能传递出说话者不满、生气的负面情感。因此，该子任务旨在通过对隐喻的内容与语境的分析，实现对中文隐喻的情感分析。

|数据类别     |数据条数 | 
| ------------ | ------- | 
| 训练集     | 3630  |
| 测试集  | 909      |

&emsp;&emsp;该子任务提供训练集和测试集，具体数量如上表所示。该子任务是七分类任务，标签有：乐(label=1)、好(label=2)、怒(lable=3)、哀(lable=4)、惧(lable=5)、恶(lable=6)、惊(lable=7)。该子任务采用宏平均(Macro-averaging)进行评价,计算公式同子任务一。  
&emsp;&emsp;中文隐喻的情感分类主要有7大类，21小类。大类主要有乐、好、怒、哀、惧、恶、惊，小类主要有快乐、安心、尊敬、赞扬、相信、喜爱、祝愿、愤怒、悲伤、失望、疚、思、慌、恐惧、羞、烦闷、憎恶、贬责、妒忌、怀疑和惊奇。详细信息请查看大连理工大学信息检索实验室的情感词汇本题库(http://ir.dlut.edu.cn/EmotionOntologyDownload)。  

#### 数据集文件说明
```、
-- dataset
    -- subtask1-metaphor-recognition # 子任务一：中文动词隐喻识别
        -- train.xml # 训练集
        -- test.xml # 测试集
        -- test_with_label.csv # 带有标签的测试集
    -- subtask2-metaphor-sentiment-analysis # 子任务二：中文隐喻情感分析
        -- train.xml # 训练集
        -- test.xml # 测试集
        -- test_with_label.csv # 带有标签的测试集
```  
#### 声明：禁止一切使用全部或部分本评测数据进行商业活动。
