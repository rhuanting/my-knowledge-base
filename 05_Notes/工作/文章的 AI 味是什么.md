---
type: note
status: active
tags:
  - type/note
  - status/active
  - topic/work
---

# 文章的 AI 味是什么

## 核心观点

文章的 AI 味，不是语言流畅，也不是结构清晰，而是读者感觉不到一个真实作者在场。

它常常表现为：文章很完整、很正确、很平滑，但读完以后不知道作者到底经历了什么、判断了什么、失败了什么、真正做了什么。

更准确地说：

```md
AI 味 = 有表达，但没有经历；有观点，但没有代价；有情绪词，但没有真实情绪。
```

对于科研论文、技术报告和知识型文章来说，AI 味最明显的地方通常不是错，而是太不犯错。它会把所有话说得稳妥、抽象、均衡，却把真实研究中的选择、取舍、卡点和失败擦掉。

## AI 味不是 AI 写作的证据

一篇文章有 AI 味，不等于它一定是 AI 写的。

没有任何单一特征可以证明一篇文章来自 ChatGPT、Claude 或 Gemini。很多人类作者也会写出很重的 AI 味，因为他们习惯写标准答案、汇报材料、论文套话和过度安全的中庸表达。

所以判断 AI 味，不是在判断作者是谁，而是在判断文章里有没有真实思考的痕迹。

## 典型表现

### 1. 结构过于工整

AI 很擅长把内容整理成总分总、三点式、五点式，每段长度差不多，每个小标题格式一致。

这种写法逻辑清晰，但容易让文章像一份自动生成的讲义。

例如：

```md
首先，人工智能提高了效率。
其次，人工智能降低了成本。
最后，人工智能促进了创新。
```

问题不在于这三句话错，而在于它们太像“合理答案”，不像某个人真的想说的话。

真实作者的结构往往会有轻重：有的地方展开，有的地方一笔带过；有的判断很确定，有的地方还在犹豫。文章的节奏里会留下思考过程。

### 2. 套话和空话太多

典型套话包括：

- 随着……的发展
- 在当前背景下
- 具有重要意义
- 值得进一步研究
- 不容忽视
- 发挥重要作用
- 提供新的思路

这些词本身不是不能用，但如果一句话删掉它们以后信息量没有减少，就说明它们只是填充物。

例如：

```md
随着遥感技术的快速发展，相关研究取得了重要进展，为未来研究提供了新的思路。
```

这句话看起来像论文，但它没有告诉读者：是哪种遥感技术，哪个研究问题，什么进展，为什么重要。

### 3. 语言过于平滑

AI 味重的文章往往没有毛边。它不会突然停顿，不会暴露困惑，也很少写出具体失败。

真实写法可能是：

```md
这个方法一开始效果不错，但后来发现烟雾影响特别大，所以又改了两次。
```

AI 味写法可能是：

```md
尽管该方法在初期取得了较好的效果，但在复杂环境下仍存在一定局限性，需要进一步优化。
```

后一种表达语法更完整，但它把真正有价值的信息抹平了：什么复杂环境，什么局限性，怎么发现的，后来怎么改。

### 4. 缺少具体细节

AI 味最重的句子，常常是那种听起来专业、但没有任何可验证细节的句子。

例如：

```md
本研究使用多源遥感数据进行了实验验证。
```

更好的写法是：

```md
本研究使用 Sentinel-1 IW GRD、Sentinel-2 L2A 和 PlanetScope 四波段影像，在 NSW 2023 年 Currowan Fire 区域进行了验证。
```

具体数据、地点、年份、设备、参数、样本、阈值、处理平台越清楚，文章越像真实工作记录，而不是抽象概括。

### 5. 过度依赖连接词

AI 很喜欢用连接词维持文章的表面逻辑：

- 此外
- 同时
- 然而
- 因此
- 值得注意的是
- 综上所述
- 总体而言

这些词能让文章顺滑，但不能替代真实逻辑。

如果每段都靠“此外、同时、然而、因此”往下接，读者会感觉作者不是在推进一个问题，而是在拼接一组正确句子。

### 6. 观点太中庸

AI 常见的表达是：

```md
该方法具有一定优势，但也存在一定不足。
```

或者：

```md
人工智能既带来了机遇，也带来了挑战。
```

这类话永远正确，也因此几乎没有判断力。

更像真人研究者的话通常会更有立场：

```md
对于澳大利亚大范围火灾监测而言，单纯依赖光学遥感意义有限，SAR 才是解决云烟遮挡问题的关键。
```

这句话可能被反驳，但它有判断，有场景，也有取舍。

### 7. 重复同一个意思

AI 为了维持篇幅，经常把一个意思换几种说法：

```md
该方法提高了精度。
同时，该方法增强了结果的可靠性。
此外，该方法进一步提升了结果的准确性。
```

如果三句话都不能提供新的信息，就应该合并，或者补充具体证据。

例如可以改成：

```md
加入 SAR coherence difference 后，烧毁区域边界的碎片化明显减少，尤其是在 Sentinel-2 受烟雾遮挡的区域。
```

这句话不只是说“更好”，而是说清楚哪里更好、为什么更好。

## 科研论文中的 AI 味

### Introduction

AI 味重的 Introduction 往往从很大的背景开始：

```md
Remote sensing has become an important tool...
With the rapid development of satellite technology...
```

问题是，连续几段行业背景并不会自动形成研究问题。

好的 Introduction 应该尽快回答：

- 现有方法卡在哪里
- 这个问题为什么在具体场景中重要
- 本文到底解决哪一个缺口
- 作者为什么选择这套数据和方法

对于 wildfire / FVC / SAR 论文来说，比起泛泛写“遥感很重要”，更有价值的是直接写清楚：光学影像在云、烟、阴影下失效，SAR 在什么条件下补上了什么证据。

### Discussion

AI 味重的 Discussion 常见句子是：

```md
The results demonstrate the effectiveness of the proposed method.
The proposed framework shows promising performance.
```

这些话只是在宣布结果有效，没有解释结果为什么有效。

Discussion 真正应该写的是：

- 哪个模块最有贡献
- 哪些场景下效果明显变差
- 失败样本有什么共同特征
- 结果和已有研究相比差异在哪里
- 方法的适用边界是什么

一个真实研究者的 Discussion，应该能看到他和数据交手过。

### Conclusion

AI 味重的 Conclusion 很喜欢这样结尾：

```md
Future studies may focus on integrating more data sources and advanced deep learning methods.
```

这句话几乎可以放进任何论文，所以它基本没有价值。

更好的结尾应该从本文真实限制出发：

```md
Future work should test whether the SAR-based evidence remains stable in low-biomass grassland fires, where coherence changes may be weaker than in forested areas.
```

它不是泛泛说“未来继续优化”，而是指出下一步最需要验证的具体问题。

## 降低 AI 味的方法

### 1. 写具体对象

不要只写：

```md
Multi-source data were used.
```

要写：

```md
GOES-16 FDCC hotspots were first used to identify potential ignition locations, after which Sentinel-2 imagery was employed to delineate burn perimeters.
```

具体对象会让读者看到你真的处理过材料。

### 2. 写失败经历

失败经历是去 AI 味最有效的材料之一。

例如：

```md
Initial experiments using only Sentinel-2 produced fragmented burn scars due to smoke contamination. SAR coherence difference was therefore introduced as an alternative source of evidence.
```

这类句子里有问题、原因和改动。它不像模板，因为它有研究现场。

### 3. 写决策原因

不要只说“采用某方法”，还要说为什么采用。

例如：

```md
A 50 km x 50 km tiling strategy was adopted because larger regions frequently exceeded GEE memory limits.
```

这句话的价值不在于语言多漂亮，而在于它暴露了真实约束：GEE 内存限制影响了方法设计。

### 4. 写真实数字

“显著提高效率”太空。

更好的写法是：

```md
Processing time was reduced from approximately 45 minutes to less than 5 minutes per tile.
```

数字会让判断落地，也更容易被读者相信。

### 5. 写清楚取舍

真实研究和真实写作都不是只有优点。

可以写：

```md
The SAR-based step improved robustness under smoke contamination, but it also introduced false positives in recently harvested agricultural fields.
```

这类表达比“有优势也有不足”更可信，因为它说清楚了优势在哪里，代价在哪里。

## 快速判断标准

判断一篇文章有没有 AI 味，可以问几个问题：

- 这篇文章有没有具体的人、事、数据、地点、参数或时间？
- 作者有没有说清楚自己为什么这样做？
- 文中有没有失败、限制、改动和取舍？
- 观点有没有明确指向，还是只是在两边都说一点？
- 删除连接词和套话以后，信息量还剩多少？
- 读完以后，我是否知道作者到底干了什么？

最简单的判断是：

```md
AI 味重的文章：语言很流畅，但读完不知道作者到底干了什么。
人味更重的文章：可能没那么华丽，但能看到具体问题、具体决策和真实思考过程。
```

## 写作原则

降低 AI 味，不是把文章改得更口语化，也不是故意制造错别字和不流畅。

真正有效的方法是写出三类痕迹：

- 经历的痕迹：我处理过什么材料，遇到过什么问题。
- 判断的痕迹：我为什么选 A 而不是 B。
- 代价的痕迹：这个选择带来了什么收益，又牺牲了什么。

文章越能呈现这些痕迹，越不像自动生成的标准答案。

## 相关链接

- [[工作]]
