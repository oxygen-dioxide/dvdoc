# Deepvocal简介
[Deepvocal](https://www.deep-vocal.com/#/)（dv）是一款自由，免费，非商业的歌声合成软件，由[Boxstar](https://space.bilibili.com/7644915)开发。用户可使用Deepvocal Toolbox（dvtb）开发dv音源。

## 运行环境
目前，dv和dvtb均仅原生支持windows，但可以通过wine在mac和linux上运行。

## 历史
dv的前身是Sharpkey（sk），dv沿用了sk的界面，但是开发了新的合成引擎。

2019年1月，Sharpkey Galaxy Editor（skg）发布，合成引擎版本为6.0（即后来的dv引擎），包含5个参数（音量，音调，气声，音素，音色）。但是该版本skg的音源在此后各版本dv中均不被支持

2019年6月7日，dv发布[试听](https://www.bilibili.com/video/BV1e4411K7Jq)，开始公测，编辑器版本1.0.0，引擎版本6.0，但不支持同为6.0的skg音源

2019年7月16日，dv1.0.6和dvtb1.0.7开放下载

2019年9月7日，dv1.1.4发布，引擎版本6.1，新增参数“声线”

2019年9月20日，dv1.1.6发布

2020年8月10日：最新消息，dv2.0即将发布，[b站动态](https://t.bilibili.com/421791923350625565?tab=2)

- 关于dv引擎版本：dv编辑器中内置多个版本引擎，而每个音源只支持一个特定版本的引擎，取决于该音源编译打包时使用的dvtb版本。dv会自动根据音源选择引擎版本。

    例如，在dv1.1.6上使用"勇气_v0.9"时，实际使用的是旧版本4.02版引擎，而不是最新版引擎。

    如果要使用最新版引擎，请用最新版dvtb重新编译与打包音源

## 工作原理
#### 歌声合成引擎的分类
- 人工智能型：通过AI学习真实歌声数据库进行合成。需要大量音频数据，音源体积小，不易破解，模拟真人演唱技巧更加真实，例如 Cevio、Muta、Aisingers、Microsoft Studiovoice
- 采样型：事先录制好某一种语言的所有音节，合成时调用对应音频，通过算法变调到指定音高与时长，再拼接成歌声。需要的音频数据较少，音源体积大。这种引擎又分为两种：
    - 非参量型：音源中直接存储原始音频，合成时通过psola等算法调整音频频率。音源容易破解（UTAU甚至直接暴露音频文件，可以自行修改使用，更为灵活），如UTAU默认引擎、袅袅虚拟歌手
    - 参量型：对原始音频进行分析后得到中间参量（例如频谱），储存在音源中，合成时再基于中间参量合成歌声。音源不易破解，如 Moresampler、SynthV、Deepvocal

#### 采样器
deepvocal采用CVVC方案。将每个音节分为“辅音到元音”(CV)和“元音到下一个辅音的过渡段”(VC)。拆分过程在dv内部自动完成，无需手动拆分。

以“好一朵美丽滴茉莉花”为例
```
hao yi duo mei li di mo li hua
```
拆分后：
```
-hao ao_y yi i_d duo o_m mei ei_ly li i_d di i_m mo o_li li i_hw hua a_-
```
具体原理可参考[riskucvvc官方lofter](https://riskucvvc.lofter.com/introduction)

#### 合成器
本部分基于一些实验进行推测，可能与真实合成机制不同

dv将原始音频分为“乐音”（基音+泛音，包括元音、浊辅音）和“噪音”（清辅音、呼吸音、底噪，听起来像悄悄话）两部分处理。

音源制作时，dv分析原始音频，通过傅里叶变换分别计算出乐音每一级谐波的强度，以及噪音的频谱，存储在Dvmodel文件中，再打包为音源。

合成时，再根据音源中的数据经过逆傅里叶变换分别合成乐音和噪音，叠加在一起。“气声”参数用来控制噪音的强度。

[下一章：调校前的准备](https://gitee.com/oxygendioxide/dvdoc/blob/master/deepvocal/2_preparation.md)