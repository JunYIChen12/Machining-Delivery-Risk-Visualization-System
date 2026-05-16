# Machining Delivery Risk Visualization System

机加工生产事实可视化产品原型仓库。

本仓库用于沉淀“液压快速换模系统”在机加工多订单交叉生产场景下的产品设计迭代、可演示 Demo 和产品文档。

## 当前推荐版本

当前主版本是 **v5-semifinished-public-pool**：半成品公共池产品原型。

- 当前可运行 Demo：[prototype/index.html](./prototype/index.html)
- v5 归档版本：[versions/v5-semifinished-public-pool/index.html](./versions/v5-semifinished-public-pool/index.html)
- v5 产品说明：[docs/semifinished-public-pool-prototype.md](./docs/semifinished-public-pool-prototype.md)

## 当前产品定义

- 产品族：液压快速换模系统
- 订单型号：例如 25T、30T、10T
- 固定半成品结构：销轴、缸体、活塞、压板、基座
- 固定工艺路线：绑定在半成品模板上
- 订单变化项：每个半成品的规格、目标数量、加工进度、报工状态
- 最小分析颗粒度：半成品名称 + 规格

## 第一阶段产品边界

第一版聚焦“半成品公共池可视化看板”，只回答两个问题：

- 公共池状态：理论上已经形成多少半成品生产能力
- 订单需求状态：哪些订单需要这个半成品及规格

明确不做：

- 不读取不可信库存
- 不判断订单占用
- 不判断真实可交付
- 不自动给出“应该分配给谁”的结论
- 不做排产、预测、设备效率、人员绩效、质量分析

## 可信数据链路

可信链路：销售订单 → 生产任务卡 / 工单 → 产品 → 半成品 → 规格 → 工艺路线 → 工序 → 报工记录。

公共池不是库存池，也不是订单占用池。它是基于 BOM、工艺路线和报工记录形成的理论生产事实池。

核心计算口径：

```text
理论完成量 = 所有必经工序报工数量的最小值
```

## 目录说明

- `docs/`：产品原型文档，含 Markdown 版产品说明
- `prototype/`：当前最新可运行 Demo
- `versions/`：历次产品设计版本沉淀

## 版本脉络

详见 [CHANGELOG.md](./CHANGELOG.md)。
