# 常见问题

**Q：物联网引擎适合设备向云端传输哪种类型的数据？**

A：高频，小数据。典型场景为设备上报的遥测报文数据，例如各种传感器监测的数据。视频，图片这些大存储容量的数据不适合使用物联网中心服务传输。

**Q：物联网引擎是共享型的服务吗？**

A：物联网中心服务不是共享型的服务。每个租户在自己的VPC里创建和管理自己的物联网中心服务实例，实例之间相互独立、隔离。

**Q：物联网引擎的规则引擎支持对接哪些京东云的服务？**

A：RDS、ES以及JCQ。

