- 提案时间: 2022-09-13
- 影响版本: 1300
- 相关 Issues: 无

## 【必填】概述

image组件支持图片显示质量配置。

## 【必填】动机

Android O以下版本Bitmap内存在Java堆上，加载大量图片容易出现OOM。image组件大部分场景是用来显示网络jpg图片，不含有透明通道。在显示jpg图片场景中，ARGB8888和RGB565显示效果差别不大，但降低至RGB565可以明显降低内存。
Android O版本以下将image对应的native组件FlexImageView默认加载的Bitmap格式从ARGB8888改为RGB565，从线上数据统计来看，由加载图片导致的OOM下降41.7%，整体JE崩溃率下降34.5%，收益比较可观。

## 【必填】API规格和使用案例

如果提案新增或更改 API ，需要按照以下格式说明API规格，以及提供一个基本的代码案例。

#### image组件增加如下属性

| 名称 | 类型  | 必填  | 说明  |
| --- | --- | --- | --- |
|   quality  |  high \| low   |   否  |  图片显示质量配置。high表示高质量显示，low表示低质量显示。Android O版本以下默认为low，Android O版本及以上版本默认为high。|

## 【必填】提案人员是否愿意自行实现该功能

*是：提案人员愿意在提案通过后自行实现该功能；*

## 详细设计

若该属性CP没有配置，则Android O以下版本FlexImageView组件默认加载Bitmap格式为RGB565。Android O及以上仍保持现状，Bitmap格式为ARGB8888。若该属性CP进行了配置，则以CP配置为准，low表示FlexImageView加载Bitmap格式为RGB565，high表示FlexImageView加载Bitmap格式为ARGB8888。

## 缺陷

略。

## 替代选择

略。

## 适配策略

正常情况下，CP不需要配置该属性。除非在Android O以下版本CP确实有高质量图片显示需求。