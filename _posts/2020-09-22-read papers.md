---
title: 9月论文 非线性效应
categories: 
 - papers
date: 2020-09-22 20:30:00
tags: 
 - OPM 2020
 - GN Model
 - EGN Model
description: 论文总结分析
---

<!-- more -->

### 1. 北邮 硕士论文 非线性效应 估计

## 高速光通信系统中非线性效应估计方法的理论研究

1. 用最小均方差算法去除线性型号和非线性信号相关性（单载波，色散不补偿）。Q：最小均方差算法是什么？如何去除？A：和DSP的RMSE的方法类似
2. 多载波，色散补偿系统的非线性估计。

非线性噪声功率谱密度理论值得到的方法：

1. 数学函数模拟
2. 插值函数表示发射端信号来模拟

系统组合（单载波，最后的信号均没有色散补偿）：

1. 脉冲方式：奈奎斯特整形，NRZ，RZ
2. 色散：预色散（200000ps/nm ???），无预色散
3. 光纤：SMF，NZCSF
4. span：1个span，15个span
5. 调制格式：QPSK，16QAM
6. 功率：0dbm，5dbm

存在的问题就是，无预色散的信号不完美服从高斯分布，因而理论计算出来的非线性噪声和实际的拟合有一定的偏差。因此需要对理论的公式进行一定程度的修正。

![9%E6%9C%88%E8%AE%BA%E6%96%87%20%E9%9D%9E%E7%BA%BF%E6%80%A7%E6%95%88%E5%BA%94%204b6d00cb81274ae08578a8d65ed11b41/Untitled.png](9%E6%9C%88%E8%AE%BA%E6%96%87%20%E9%9D%9E%E7%BA%BF%E6%80%A7%E6%95%88%E5%BA%94%204b6d00cb81274ae08578a8d65ed11b41/Untitled.png)

![9%E6%9C%88%E8%AE%BA%E6%96%87%20%E9%9D%9E%E7%BA%BF%E6%80%A7%E6%95%88%E5%BA%94%204b6d00cb81274ae08578a8d65ed11b41/Untitled%201.png](9%E6%9C%88%E8%AE%BA%E6%96%87%20%E9%9D%9E%E7%BA%BF%E6%80%A7%E6%95%88%E5%BA%94%204b6d00cb81274ae08578a8d65ed11b41/Untitled%201.png)

![9%E6%9C%88%E8%AE%BA%E6%96%87%20%E9%9D%9E%E7%BA%BF%E6%80%A7%E6%95%88%E5%BA%94%204b6d00cb81274ae08578a8d65ed11b41/Untitled%202.png](9%E6%9C%88%E8%AE%BA%E6%96%87%20%E9%9D%9E%E7%BA%BF%E6%80%A7%E6%95%88%E5%BA%94%204b6d00cb81274ae08578a8d65ed11b41/Untitled%202.png)

![9%E6%9C%88%E8%AE%BA%E6%96%87%20%E9%9D%9E%E7%BA%BF%E6%80%A7%E6%95%88%E5%BA%94%204b6d00cb81274ae08578a8d65ed11b41/Untitled%203.png](9%E6%9C%88%E8%AE%BA%E6%96%87%20%E9%9D%9E%E7%BA%BF%E6%80%A7%E6%95%88%E5%BA%94%204b6d00cb81274ae08578a8d65ed11b41/Untitled%203.png)

Q值居然可以用上面的表达式来表示！

**可做的点：高斯模型的修正，实验验证。第一点应该被修正为了EGN，extended GN?第二点应该是也有相应的实验验证了。**



### 2. GN Model

## Modeling of the Impact of Nonlinear Propagation Effects in Uncompensated Optical Coherent Transmission Links

非线性效应在未补偿光通信系统中的建模

1. introduction
2. THE GN MODEL AND ITS DERIVATION
    1. BER SNR and OSNR ✅
    2. Modeling the Transmitted Signal ✅ 
    3. The NLI Power Spectral Density ✅ 
3. SIMULATED TEST SYSTEM LAYOUT AND BACK-TO-BACK PERFORMANCE
   
    1. Back-to-Back Sensitivity Evaluation ✅
4.  COMPARISON BETWEEN MODEL AND SIMULATION RESULTS

    **对比的组合：信道的功率（Pch=-10~5 dbm）、信道的宽度（Δf=32G、50G）、调制格式（PM-BPSK、PM-QPSK、PM-8QAM、PM-16QAM）、光纤种类（SMF、NZDSF、PSCF）**

    1. Performance versus Number of Channels ✅

        结论：Lmax会随着信道数的增多而下降，但是下降的比较慢（C波段的仿真）

    2. Coherent versus Incoherent Noise Accumulation ✅

        结论：仿真并不能代表真实实验的情况，因此不能得出结论关于相干和非相干模型的优劣

    3. Ultralow Dispersion Scenarios ✅

        结论：对于低色散光纤，例如NZDSF，模型的性能并没严重退化。可能是因为D的值还不够低。**可以做下一步的验证。**

    4. Experimental Validation ✅
5. CONCLUSION

For notational clarity 为了方便描述，为了符号清晰

为了使通过公式：

![9%E6%9C%88%E8%AE%BA%E6%96%87%20%E9%9D%9E%E7%BA%BF%E6%80%A7%E6%95%88%E5%BA%94%204b6d00cb81274ae08578a8d65ed11b41/Untitled%204.png](9%E6%9C%88%E8%AE%BA%E6%96%87%20%E9%9D%9E%E7%BA%BF%E6%80%A7%E6%95%88%E5%BA%94%204b6d00cb81274ae08578a8d65ed11b41/Untitled%204.png)

算出来的BER和实际测到的BER相符合，提出了SNR的修正公式：

![9%E6%9C%88%E8%AE%BA%E6%96%87%20%E9%9D%9E%E7%BA%BF%E6%80%A7%E6%95%88%E5%BA%94%204b6d00cb81274ae08578a8d65ed11b41/Untitled%205.png](9%E6%9C%88%E8%AE%BA%E6%96%87%20%E9%9D%9E%E7%BA%BF%E6%80%A7%E6%95%88%E5%BA%94%204b6d00cb81274ae08578a8d65ed11b41/Untitled%205.png)

在修正公式中，加入了XI项，代表交叉串扰crosstalk和ISI。如果信道的滤波器太窄，会引起ISI，如果滤波器太宽，会引起crosstalk。XI项和功率无关。



### 3. Model review

## Recent Advances in the Modeling of the Impact of Nonlinear Fiber Propagation Effects on Uncompensated Coherent Transmission Systems (Tutorial Review)

从目录可见，其实就主要是对于GNmodel和EGNmodel的介绍

1. introduction
2. The GN model
    1. The nonlinear OSRN ✅
    2. The GN-Model Equations ✅
    3. Accuracy Assessment ✅

        Q: ASE 噪声全加在了Rx上，没有加inline的ASE

    4. Incoherent GN-Model test result ✅

        短距（<200 km）会导致信号的分布不够高斯，从而使得误差增大，距离大于500km后基本误差会变得比较小。并且误差基本和MF,fiber的种类以及span的长度无关。

    5. Closed-form incoherent GN-Model test result ✅

        由于做二重积分依旧需要一定的计算量，因此对积分再做合理的简化可以直接得到$P_{NLI}$。但是其拟合度需要检验。并且这一简化是从incoherent的模型出发的。并且span的loss需要大于10dB。

    6. comments on the incoherent GN-Model ✅

        incoherent GN-Model正确率高的原因是误打误撞地在两次简化中消除了误差。并且得到的结果是和EGN-Model的结果相似的。

    7. Limitations of the GN-Model ✅ 

        GN-model loses accuracy at low symbol rates and low spans. It does not allow to assess some finer effects of format-dependence on NLI. It does not handle well NL-PN mitigation.

3. The EGN-Model
    1. EGN-Model test result ✅

        在MR和$P_{NLI}$两个层面上都拟合地更好

    2. Low symbol rate ✅
        - GN model需要信号是高斯分布的，因此需要在大的色散条件下，而大的色散需要的是高symbol rate，所以小信号速率会导致GN Model的精度较低。因此引入EGN，这个模型不需要大信号速率。
        - 提出一个用来比较的标准：$G^{hat}_{NLI}=P_{NLI}/R_{s}G^{3}_{ch}$，发现不同的MF的GNLI是相同的，因此可以用来比较不同的symbol rate之前的关系。

            ![9%E6%9C%88%E8%AE%BA%E6%96%87%20%E9%9D%9E%E7%BA%BF%E6%80%A7%E6%95%88%E5%BA%94%204b6d00cb81274ae08578a8d65ed11b41/Untitled%206.png](9%E6%9C%88%E8%AE%BA%E6%96%87%20%E9%9D%9E%E7%BA%BF%E6%80%A7%E6%95%88%E5%BA%94%204b6d00cb81274ae08578a8d65ed11b41/Untitled%206.png)

    3. **EGN-Model closed-form approximations** ✅

        ![9%E6%9C%88%E8%AE%BA%E6%96%87%20%E9%9D%9E%E7%BA%BF%E6%80%A7%E6%95%88%E5%BA%94%204b6d00cb81274ae08578a8d65ed11b41/Untitled%207.png](9%E6%9C%88%E8%AE%BA%E6%96%87%20%E9%9D%9E%E7%BA%BF%E6%80%A7%E6%95%88%E5%BA%94%204b6d00cb81274ae08578a8d65ed11b41/Untitled%207.png)

        ![9%E6%9C%88%E8%AE%BA%E6%96%87%20%E9%9D%9E%E7%BA%BF%E6%80%A7%E6%95%88%E5%BA%94%204b6d00cb81274ae08578a8d65ed11b41/Untitled%208.png](9%E6%9C%88%E8%AE%BA%E6%96%87%20%E9%9D%9E%E7%BA%BF%E6%80%A7%E6%95%88%E5%BA%94%204b6d00cb81274ae08578a8d65ed11b41/Untitled%208.png)

4. Nonlinear phase and polarization noise
    1. Nonlinear phase noise ✅
        - 非线性的相位噪声会带来序列间的长相关，50个symbol左右还有相关性。PN-receiver CPE算法在消除了非线性相位噪声之后，可能得到的BER就和模型计算出来的BER不相同了，估计的NLI noise会被高估。NLI被高估的话，能达到的最远传输距离相应地就会下降，这在图21中体现了出来。
        - Average EGN model MR prediction error is −5.5% in the 100 km-spans landscape and −7.6% in the 60 km-spans landscape.
        - 补偿这一个小误差的方法是将所有的格式都当作PM-QPSK来对待，因为去长相关后，每个MF的信号的相应NLI和PM-QPSK的相近。用这个方法后，误差下降到了1.8%和1.1%。
        - 长相关的标准是累积色散达到3000ps/nm，也就是相当于将近200km的长度。
    2. Nonlinear polarization noise ✅
        - 消除了偏振的串扰后，得到的MR的提升为：2.2% and 3.5%, for the 100 km and 60 km spans landscapes
5. Copropagating ASE noise and signal depletion  
    1. ASE noise ✅
       
        - 在低OSNR的情况下，PM-QPSK及更低的调制格式会受到ASE的影响。其他格式或者高OSNR的情况都影响不大。更精确的矫正在27号文献中。39号文献也有相关内容。
    2. Signal depletion ✅
    - 在低OSNR的情况下，ASE噪声功率一定（是NLI噪声的2/3，因此OSNR越低，相对的信号非线性噪声比越低，那么信号转化为非线性噪声的比例越大）。将这一部分转化考虑进去的话，MR会比不考虑的低，也就是不考虑的MR会高估。 文献39。
    
        ![9%E6%9C%88%E8%AE%BA%E6%96%87%20%E9%9D%9E%E7%BA%BF%E6%80%A7%E6%95%88%E5%BA%94%204b6d00cb81274ae08578a8d65ed11b41/Untitled%209.png](9%E6%9C%88%E8%AE%BA%E6%96%87%20%E9%9D%9E%E7%BA%BF%E6%80%A7%E6%95%88%E5%BA%94%204b6d00cb81274ae08578a8d65ed11b41/Untitled%209.png)
    
6. NLI Modeling and distributed amplification ✅
    - HRE 混合拉曼EDFA放大，hybrid Raman EDFA amplification。什么是Noise figure?
    - HRE 确实会带来一些NLI的放大，因为拉曼放大是逆向的，在span的后半段会导致信号几乎没什么损耗，非线性噪声也相同。大致会导致3%的MR下降。
7. other NLI models ✅
   
    - **regular perturbation (RP) models 定期微扰模型，文献45，43。T**he GN end EGN models are first-order RP-VS models, as well.
8. comments and conclusion ✅

系统构成：

**5** five modulation formats (PM-QPSK, and PMQAM with 8, 16, 32 and 64 constellation points),

**3** three fiber types (SMF, PSCF and NZDSF)

**3** three channel spacings (33.6, 37.5 and 50 GHz)

**2** both terrestrial-type and submarine-type span-lengths (100 and 60 km)

**15** channels

![9%E6%9C%88%E8%AE%BA%E6%96%87%20%E9%9D%9E%E7%BA%BF%E6%80%A7%E6%95%88%E5%BA%94%204b6d00cb81274ae08578a8d65ed11b41/Untitled%2010.png](9%E6%9C%88%E8%AE%BA%E6%96%87%20%E9%9D%9E%E7%BA%BF%E6%80%A7%E6%95%88%E5%BA%94%204b6d00cb81274ae08578a8d65ed11b41/Untitled%2010.png)

GN Model 下的二次简化：

![9%E6%9C%88%E8%AE%BA%E6%96%87%20%E9%9D%9E%E7%BA%BF%E6%80%A7%E6%95%88%E5%BA%94%204b6d00cb81274ae08578a8d65ed11b41/Untitled%2011.png](9%E6%9C%88%E8%AE%BA%E6%96%87%20%E9%9D%9E%E7%BA%BF%E6%80%A7%E6%95%88%E5%BA%94%204b6d00cb81274ae08578a8d65ed11b41/Untitled%2011.png)

![9%E6%9C%88%E8%AE%BA%E6%96%87%20%E9%9D%9E%E7%BA%BF%E6%80%A7%E6%95%88%E5%BA%94%204b6d00cb81274ae08578a8d65ed11b41/Untitled%2012.png](9%E6%9C%88%E8%AE%BA%E6%96%87%20%E9%9D%9E%E7%BA%BF%E6%80%A7%E6%95%88%E5%BA%94%204b6d00cb81274ae08578a8d65ed11b41/Untitled%2012.png)

EGN Model 的修正：

![9%E6%9C%88%E8%AE%BA%E6%96%87%20%E9%9D%9E%E7%BA%BF%E6%80%A7%E6%95%88%E5%BA%94%204b6d00cb81274ae08578a8d65ed11b41/Untitled%2013.png](9%E6%9C%88%E8%AE%BA%E6%96%87%20%E9%9D%9E%E7%BA%BF%E6%80%A7%E6%95%88%E5%BA%94%204b6d00cb81274ae08578a8d65ed11b41/Untitled%2013.png)

![9%E6%9C%88%E8%AE%BA%E6%96%87%20%E9%9D%9E%E7%BA%BF%E6%80%A7%E6%95%88%E5%BA%94%204b6d00cb81274ae08578a8d65ed11b41/Untitled%2014.png](9%E6%9C%88%E8%AE%BA%E6%96%87%20%E9%9D%9E%E7%BA%BF%E6%80%A7%E6%95%88%E5%BA%94%204b6d00cb81274ae08578a8d65ed11b41/Untitled%2014.png)

```html
<object data="http://yoursite.com/the.pdf" type="application/pdf" width="700px" height="700px">
       <embed src="http://yoursite.com/the.pdf">
           This browser does not support PDFs. Please download the PDF to view it: <a href="http://yoursite.com/the.pdf">Download PDF</a>.</p>
       </embed>
</object>
```