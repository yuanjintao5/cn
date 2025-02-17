# 常见问题

**Q：什么是共享带宽包？**

A：京东云共享带宽包是一种在同一地域支持多IP带宽聚合的流量计费模式，例如您在华北-北京创建了一个共享带宽包实例，那么您在北京地域的所有按配置和按流量购买的公网IP可添加到该共享带宽包中，这些公网IP复用共享一条带宽。

**Q：共享带宽包的付费类型有哪些？**

A：京东云共享带宽包提供三中付费类型：

包年包月——预付费，至少购买一个月；

按配置——后付费，按小时结算；

按用量——后付费，按月结算；

其中按用量计费模式包括按增强95消峰计费和按95消峰计费两种模式（增强95消峰和传统95消峰计费均处于灰度中，如需使用，请[提交工单](https://ticket.jdcloud.com/applyorder/submit)申请使用权限）。

**Q：如何申请共享带宽包消峰计费模式的使用权限？**

A：共享带宽包的消峰计费模式请[提交工单](https://ticket.jdcloud.com/applyorder/submit)申请。


**Q：如何购买共享带宽包？**

A：首先您需有京东云账号并通过实名认证，进入京东云官方网站登录控制台，点击左上角的【云服务】-->【私有网络】-->【共享带宽包】-->【创建】，即可进入购买共享带宽包操作，详情请参考创建共享带宽包

**Q：如何将公网IP加入共享带宽包？**

A：共享带宽包未停服时支持添加公网IP，进入私有网络，选择共享带宽包，进入共享带宽包列表，定位公网IP需要加入的共享带宽包，点击【添加公网IP】，选择需要加入共享带宽包的公网IP，点击【确定】即可完成公网IP加入共享带宽包。

**Q：IP加入共享带宽包后还会单独计费吗？**

A：不会。公网IP加入共享带宽包后原有计费失效，统一通过共享带宽包进行计费，IP的带宽上限默认为共享带宽包的带宽上限，从共享带宽包中移除后恢复原有计费规则和带宽上限。

**Q：为什么在待添加IP的列表中找不到某个IP？**

A：待添加的列表IP为与当前共享带宽包同地域下所有线路相同的IP，如未找到请确认所加IP与共享带宽包的线路是否相同，更多限制请参考[使用限制](../Introductions/Restrictions.md)。

**Q：共享带宽包带宽上限可以修改吗？**

A：共享带宽包在未到期、未欠费的状态下支持修改带宽上限，并立即生效。调整的带宽上限值不能低于共享带宽包中IP进行单独限速的带宽上限，如需降低共享带宽包带宽，需先调整共享带宽包中单独限速的IP带宽上限。未进行单独限速的IP带宽上限将随共享带宽包同步变更，调整前请确认业务不受影响。

**Q：修改带宽上限会产生费用吗？**

A：修改带宽时会根据不同的付费类型会产生新的订单，订单金额根据调整情况而定，是否需要支付根据付费类型而定。修改带宽上限支付费用明细如下：
      
      注：“√”表示需要支付费用，“×”表示不需要支付费用
      
|付费类型 | 提升带宽|降低带宽|
| --- | --- | --- |
|包年包月 | √（到期时间不变，支付差价）|×（IP资源到期日期延长）|
|按配置 | ×|×|
|按用量 | ×（保底带宽同步调整）|×（保底带宽同步调整）|

上表中，按配置、按用量虽无需立即付费，但后续账单的单价会发生变化，若提升带宽，每小时/每天需支付的费用上升，若降低带宽，则费用降低。

**Q：共享带宽包的出入方向带宽峰值为多少？**

A：共享带宽包的出入方向带宽峰值为您所实际购买带宽上限的100%，如您购买的带宽上限为1000Mbps，则该共享带宽包的最大带宽峰值为1000Mbps，出入方向带宽上限一致，共享带宽包入方向的带宽值等于您购买带宽包的带宽上限。

**Q：如何修改共享带宽包的带宽上限？**

A：进入共享带宽包列表页，定位需要修改的共享带宽包，点击【修改带宽】进行修改共享带宽包带宽上限，详情参考[修改共享带宽包带宽上限](../Operation-Guide/Modify-Bwp.md)。


**Q：如何查看共享带宽的监控信息？**

A：在共享带宽包列表页，定位想要查看的共享带宽包，点击【共享带宽包ID】，进入共享带宽包详情页，点击【监控】tab 即可查看对应共享带宽包的监控信息。

**Q：支持修改EIP的带宽上限吗？**

A：支持，修改之前需要定位EIP所在的共享带宽包，点击【共享带宽包ID】-->【公网IP】，进入弹性公网IP列表页，选择需要修改的公网IP，公网IP的带宽上限最大值不能超过共享带宽包的带宽上限。

**Q：共享带宽包的配额是多少？**

A：按配置和包年包月计费的配额不限，按用量计费的配额为5，仅按用量计费类型支持提工单申请更大的配额。

## 相关参考
- [共享带宽包概述](../Introductions/Product-Overview.md)
- [使用限制](../Introductions/Restrictions.md)
- [计费概述](../Pricing/Billing-Overview.md)
- [价格总览](../Pricing/Price-Overview.md)
- [增强95消峰计费](../Pricing/Charge-By-Usage/Enhance95th-Eliminate.md)
- [计费规则](../Pricing/Billed-Rules.md)
- [管理公网IP](../Getting-Started/Manage-Public-IP.md)
- [修改共享带宽包带宽上限](../Operation-Guide/Modify-Bwp.md)
- [创建共享带宽包](../Operation-Guide/Create-Bwp.md)
