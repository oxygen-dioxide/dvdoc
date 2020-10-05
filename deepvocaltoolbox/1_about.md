# 关于Deepvocal音源开发
## 注意事项
1. 根据dv的使用协议，请确保音频和人设的版权属于你，或你已经取得版权所有者的授权。禁止使用来源不明或没有版权的音频和人设。例如鬼畜人力，或者为别人创作的角色录制同人音源。

2. dv引擎对原始音频的音质要求较高，低音质音频在音源编译过程中会报错，因此鬼畜人力音源（从技术上）不适用于dv。

3. 建议在使用dv调校了一定数量的歌曲，熟悉dv基本机制与各参数效果（尤其是音素和音色）之后，再开始开发dv音源。

## 从头开发
1. 录音（oremo）
2. 音频后期处理（adobe au）
3. 编写发音字典（dvtb）
4. 原音设定（dvtb）
5. 编译与打包（dvtb）

## 从UTAU移植
1. 音频后期处理（adobe au）
2. 原音设定转换
3. 编译与打包（dvtb）

常见的UTAU录音方案分为三类：整音、CVVC、VCV，这三类UTAU音源移植到dv的难度和效果各不相同

|录音方案|整音（扩张整音、syo、袅袅）|CVVC|VCV|
|-|-|-|-|
|录音数量（中文）| 约410条×1字 | 约210条×8字 | 约2300条×7字|
|移植工作量|需为整音编写专门的发音字典，并进行整音原音设定（约440条）|原音设定可直接转换，但可能有少量错误需要修改|需重新进行CVVC原音设定|
|效果|较差|较好|较好，与CVVC相同|
||如果有条件建议重新录制CVVC|||

## 跨平台音源开发
如果想开发UTAU与Deepvocal跨平台音源，无需为UTAU和dv分别录音，可以用一份音频开发两个平台的音源。建议录制CVVC音源，先进行UTAU原音设定，再转换为dv原音设定。这是因为dv原音设定不能反向转换为UTAU原音设定。

但是如果没有跨平台计划，建议直接进行dv原音设定，工作量较小。

## 软件与资源

### 软件
deepvocal与deepvocal toolbox：[官网](https://www.deep-vocal.com/)

录音软件oremo：[官网](https://osdn.jp/users/nwp8861/pf/OREMO/wiki/FrontPage)  [简体中文版](http://tieba.baidu.com/p/6059601688)

dvcfg模板生成器：[b站专栏](https://www.bilibili.com/read/cv5381992)

oto.ini转voice.dvcfg工具：[Github](https://github.com/justln1113/oto2dvcfg)

Adobe Audition为商业软件，请自行购买，或用audacity等免费软件代替。

## 参考资料

[Boxstar dvtb教程](https://share.weiyun.com/5snXMol)

[Risku中文CVVC官方博客](http://riskucvvc.lofter.com/)