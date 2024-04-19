###sharpness###

1. 观察整体edge 強度，初步調整 OverShootGain 和 UnderShootGain 到适当强度即可。
2. 总共有 6 种不同的 edge filter，无向性 edge 和方向性 edge 分别都有高/中/中低频，可以先调整混合方式到 完全用某一种 filter，并观察每种 filter 的效果，可以搭配 debug mode 以方便观察。
3. 调整无向性 edge 的频段。
  调整 MidRatioUDByMot 和 HighRatioUDByMot 和 HighRatioUDByState 来权衡高低频混合方式。
  调整 SharpnessUD 控制各种频段的强度，或是调整 PreCorUD 控制各种频段的 coring 值。
4. 调整方向性 edge 的频段。
  调整 MidRatioDByMot 和 HighRatioDByMot 和 HighRatioDByState 来权衡高低频混合方式。
  调整 SharpnessD 控制各种频段的强度，或是调整 PreCorD 控制各种频段的 coring 值。
5. 调整 DirRatioByState 来权衡无向性 edge 和方向性 edge 的混合方式。
6. 反复调整上述三步骤。可以将 SharpnessUD 和 SharpnessD 的其中五个值设为 0，就能得知各区域被分配到 哪些向性/频段，若觉得不合理，再调整混合方式。
7. 依据不同条件来調整edge，常用于降低平坦区的edge，讓平坦區更平顺。有很多种方式都可以达成，但每 种方式都会牺牲细节，因此建议不要只用单一方式，否则结果可能只适合某些特定场景。
  调整 DetailGainByMot，可以让 NRLumaAdv 判断为平坦区的区域降低无向性 edge，建议动静暂时调的 一样。
  调整 GainByStd，通常平坦区的标准偏差较小，因此可以降低标准偏差小的区域的 edge。
  调整 EdgeKillLut，通常平坦区的 edge 强度较小，因此可以把小 edge 调的更小。
  调整 YEE 内的 NR，建议将 SmoBlendByStd 和 SmoBlendByMot 都设 0，调整 SmoDiffThByY 即可，若 有需求再混一些 mean/median filter 的结果即可。
  调整 coring 相关参数，包括 PreCorUD 和 PreCorD 和 CorByY。
8. 若有需求想依据亮度调整，可以调整 SclByY 和 StdAdjByY 和 CorByY。
9. 若有需求想限制 overshoot 或 undershoot edge，可以调整 OverShootLimit 和 UnderShootLimit。
10. 若有需求想依据 hue 调整 edge 强度，可以调整 StrengthByHue，例如降低肤色 edge 来减轻人移动的躁声， 或是增加绿色 edge 来强化树的细节。
11. 调整运动噪声
  依据 motion 调降 edge，建议以调整 GainByMot 和 StdAdjByMot 为主。
  亦可尝试调整 CorByMot 和 DetailGainByMot 和 SmoBlendByMot。
  建议搭配 3DNR/NRLuma/NRLuma_Adv 反复调整。


.



