# 监控概述

京东云提供对弹性公网IP进行监控和报警的服务，通过图示展示各项监控指标数据，直观地展示资源的使用情况，
并支持对监控指标设置报警，当触发报警后会通过短信、邮件等方式发送报警通知，方便您了解在弹性公网IP资源的使用情况、性能和运行情况；通过报警及时作出反应，保障业务的稳定运行。

## 监控指标

公网IP的监控指标如下表所示。
| 监控指标 |Metric  | 含义|值类型|单位|说明|
|------|----|-------|------|-----|----|
|**公网出带宽速率**|floatingip.outgoing.bytes|在某个时刻公网IP出方向的带宽速率|时刻|bps||
|**公网入带宽速率**|floatingip.incoming.bytes|在某个时刻公网IP入方向的带宽速率|时刻|bps||
|**公网出带宽使用率**|floatingip.out.bandwidth.util|在某个时刻公网IP出方向的带宽上限占出方向总带宽上限的比例|时刻|%|公网IP加入共享带宽包后，带宽上限以在共享带宽包中的带宽上限为准|
|**公网入带宽使用率**|floatingip.out.bandwidth.util|在某个时刻公网IP出方向的带宽上限占出方向总带宽上限的比例|时刻|%|出方向100Mbps以内的公网IP入方向默认为100Mbps，公网IP加入共享带宽包后，带宽上限以在共享带宽包中的带宽上限为准
|**公网出包量**|floatingip.outgoing.packets|在当前周期下，公网IP出方向转发的包量|增量|pps||
|**公网入包量**|floatingip.incoming.packets|在当前周期下，公网IP入方向转发的包量|增量|pps||
|**公网出流量**|floatingip.outgoing.bytes|在当前周期下，公网IP出方向转发的流量|增量|bytes|需通过云监控的[接口](https://docs.jdcloud.com/cn/monitoring/api/describemetricdata?content=API)拉取数据查看|
|**公网入流量**|floatingip.incoming.bytes|在当前周期下，公网IP入方向转发的流量|增量|bytes|需通过云监控的[接口](https://docs.jdcloud.com/cn/monitoring/api/describemetricdata?content=API)拉取数据查看|

## 监控数据说明

* 监控数据采集周期为30s，最小展示间隔为1min；
* 不同指标的默认聚合方式不同，可在监控图中指定各指标的聚合方式；
* 统计周期默认支持1小时、6小时、12小时、1天、3天、7天及14天，此外还支持您自定义监控数据统计周期，最短为1分钟最长为一个月；
* 不同监控数据统计周期监控值会做对应聚合，例如查看6小时的监控数据，每5分钟聚合一个监控值，该监控值为对应统计周期内采集值的聚合，支持以不同的聚合方式查询；
* 在控制台可以观察30天的监控数据，在后台监控数据最多保存60天，若需要获取30天-60天的监控数据，请提交工单。

## 相关参考

- [云监控](https://docs.jdcloud.com/cn/monitoring/product-overview)
- [云监控-弹性公网IP](https://docs.jdcloud.com/cn/monitoring/ip)
- [管理报警规则](https://docs.jdcloud.com/cn/monitoring/manage_alarmrules_cm)

