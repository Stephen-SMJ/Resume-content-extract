# 智能简历信息提取
面试官上传一份简历到系统，系统提取出简历关键信息自动筛选候选人并发起面试。
简历内容分类：首先将简历转换成图片格式，使用OCR检测并提取出含有文字的部分。使用Opencv将文字部分内容填充白色，并把所有不含文字的部分填充成黑色，使用图像的膨胀方法将所有白色区域膨胀，在同一段落的文本（白色区域）会因膨胀而连接在一起，将所有坐标在同一白色区域内的文本拼接起来，以此实现文本段落的划分。使用bert训练出一个6分类的文本分类器（基本、技能、描述、荣誉、经验、其他），将所有划分好的段落依次送入bert中分类，最后整合6个类别的所有段落实现简历内容分类。使用flask编写接口并部署。
基本信息提取：对基本类进行基本信息提取：使用cocoNLP、PyHanlp、pseg联合进行提取姓名；使用正则表达式提取邮箱；使用PyHanlp自定义词库提取学校；使用关键字提取学历以及岗位，并返回最高学历所对应的学校；使用cocoNLP提取手机号。使用flask编写接口并部署。
## 功能预览

![resume](https://user-images.githubusercontent.com/67999981/218740928-4e485f96-f001-4622-8957-a8ea43228b9d.png)
