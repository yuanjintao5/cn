# 价格总览
  
京东云支持共享带宽包按包年包月、按配置、按用量计费，各计费类型的带宽单价如下所示：

### 包年包月

| 地域 | 线路                                   | 带宽          | 单价（元/月/Mbps） |
| ---- | --------------------------------------- | ------------- | ------------------ |
| 全地域 | BGP | 200Mbps~5000Mbps | 80                 |


### 按配置

| 地域  |  线路                                  | 带宽          | 单价（元/小时/Mbps） |
| ---- | --------------------------------------- | ------------- | -------------------- |
|  全地域 | BGP | 200Mbps~5000Mbps | 0.14                 |



### 按用量-增强95

|地域|  线路    |  保底带宽占带宽上限的百分比 | 保底带宽日单价（元/天/Mbps） |  超保底带宽日单价（元/天/Mbps） |
| ---- |--------| -------------------------------- | --------------------------------------- | ------------------------------------ |
|全地域| BGP  | 20%                        | 3.36                         |  3.36                           |

### 计费示例
假设您购买了一个共享带宽包，其带宽上限为500Mbps，各个计费类型计费结果如下表所示：
| 计费类型 | 费用公式 | 计费示例 |
|:--------|:---|:---|
| 包年包月 | 包年包月共享带宽实例的总费用 = 带宽单价（元/月/Mbps） x 带宽上限（Mbps） x 购买时长（月） | 时长1个月，价格为：500\*80=￥40000元/月 |
|按配置|带宽总费用=带宽单价(元/小时/Mbps) * 使用时长(小时) \*带宽上限(Mbps)| 使用1个月，价格为：500\* 0.14 \*30\*24 =￥50400元/月 |
| 增强95消峰计费 | 月度费用 = 保底带宽费用 + 超保底带宽费用 | 使用1个月，保底带宽为500\*20%=100Mbps，消峰后为110.78Mbps，</br>月度费用为110.78\* 100.80=￥11166.62元/月 |

## 相关参考
- [计费规则](Billed-Rules.md)
- [计费概述](Billing-Overview.md)
- [增强95消峰计费](Charge-By-Usage/Enhance95th-Eliminate.md)
- [创建共享带宽包](../Operation-Guide/Create-Bwp.md)
- [续费流程](../Operation-Guide/Renew-Bwp.md)
- [常见问题](../FAQ/FAQ.md)
