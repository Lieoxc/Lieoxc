## 个人信息

- 李小聪/男/1996/广东/ | 手机：13559775072 , 邮箱：394101651@qq.com
- 求职意向：Golang后端开发 | 期望城市：深圳/广州

## 技能清单

- **编程语言** ：熟悉C/C++/Golang 、包括基本使用规范、常用标准库、并发编程、内存管理。
- **数据结构**：熟悉常用的数据结构和算法，
- **架构设计** ：掌握常用的设计模式，能够根据项目需求选择适合的设计模式，提高代码可读性和可维护性
- **中间件** ： 熟悉 MySQL、Redis、ClickHouse、Gin、Nginx等常用中间件，了解其实现原理，并掌握常用的 SQL 调优方法。
- **软件调试** ：熟练使用 GDB、strace、valgrind、pprof 等调试工具，能够快速定位和解决程序中的问题
- **计算机网络** ：熟悉 TCP/IP 协议，掌握 HTTP、MQTT、RPC 等协议的工作原理
- **Devops** ：熟悉docker/docker-compose，掌握基于gitlab 的CI/CD 流水线搭建。


## 工作经历
<div style="display: flex; justify-content: space-between;">
  <div style="font-size: 15px;"><strong>深信服集团信锐网科技术有限公司（2019 年 10 月 ~ 至今 ）</strong></div>
  <div>后端开发工程师</div>
</div>

1. IOT平台Golang/C后台开发，主要负责物模型以及数据解析相关业务开发
2. 产品线研发对外接口人：技术支持，处理线上问题
3. 企业会议系统云平台Golang后端开发
4. C++音视频开发

<div style="display: flex; justify-content: space-between;">
  <div style="font-size: 15px;"><strong>宏电技术股份有限公司（2018 年 7 月 ~ 2019 年 10 月 ）</strong></div>
  <div>linux软件开发工程师</div>
</div>

1. 负责OpenWrt Linux C应用层软件开发
2. 负责4G模块移植以及拨号开发
3. 负责设备与平台(MQTT)交互开发工作

## 项目经历 

<div style="display: flex; justify-content: space-between;">
  <div style="font-size: 15px;"><strong>BYOM混合会议音视频开发（2024 年 3 月 ~ 至今 ）</strong></div>
  <div>C++ 音视频开发</div>
</div>

**项目描述**：

- 开发了一套基于QUIC协议的实时音视频传输系统，实现了会议室主机与PC端之间的低延迟、高可靠的多媒体数据交互。系统支持多路音视频流的同步采集、编解码、渲染和虚拟设备注入，为第三方会议软件提供了完整的音视频采集解决方案。

**技术栈**：RTP/RTCP、QUIC、FFMpeg、H.265/HEVC、Opus、Direct3D 11、Windows Media Foundation

**工作内容**：

1. 设计并实现基于C++的音频设备管理SDK，为Electron客户端提供设备枚举、音频参数配置、设备状态监控等核心功能，支持热插拔事件通知机制
2. 针对无线投屏场景下的网络不稳定问题，采用Microsoft QUIC协议栈实现传输层，结合应用层多链路切换机制，显著提升了弱网环境下的传输可靠性，RTT降低40%，丢包恢复时间缩短60%
3. 开发音视频处理核心引擎，实现多路流媒体数据的实时处理与分发：
     -  音频处理流水线：实现RTP音频流解析、Opus解码、多路PCM混音（FFMpeg amix filter）、虚拟音频设备注入，支持双声道48kHz采样率，端到端延迟<100ms
     -  视频渲染流水线：基于FFMpeg实现H.265硬件加速解码，通过Direct3D 11实现零拷贝渲染，支持1080P@30fps实时显示
     -  虚拟设备注入：实现YUV420P到NV12的格式转换，并注入到Windows虚拟摄像头驱动，支持主流视频会议软件的无缝接入
     -  音频采集与编码：实现麦克风音频采集、Opus编码、RTP打包发送，支持动态码率调整，适应不同网络环境
4. 设计基于环形缓冲区的音视频同步机制，通过PTS时间戳对齐和动态缓冲区调整，实现音画同步误差<20ms
5. 采用模块化流水线架构，将RTP解析、音视频解码、渲染/注入等处理环节解耦为独立节点，支持动态加载和热插拔，系统可扩展性显著提升

<div style="display: flex; justify-content: space-between;">
  <div style="font-size: 15px;"><strong>分布式定时调度系统（2023 年 7 月 ~ 2024年3月 ）</strong></div>
  <div>Golang开发工程师</div>
</div>

**项目描述**：
设计并实现了一套高可用、高性能的分布式定时任务调度系统，用于支撑企业级会议云平台的定时任务管理。系统解决了传统Cron单点部署、任务执行不可见、调度能力有限等问题，支持千万级定时任务的可靠调度，提供完整的任务生命周期管理和执行监控能力。

**技术栈**：Golang、Redis分布式锁、Redis 消息队列、多级缓存、布隆过滤器、分布式一致性

**工作内容**：

1. 采用微服务架构设计，将系统拆分为调度器、触发器、执行器和数据迁移器四个核心组件，实现系统的水平扩展
2. 基于Redis ZSET实现高性能时间轮算法：
    - 采用分片策略和预加载机制，将调度延迟控制在毫秒级
    - 支持任务优先级调度，确保关键任务优先执行
3. 构建可靠的分布式调度机制：
    - 基于Redis分布式锁实现多实例协调和故障转移
    - 使用基于Redis的轻量级消息队列Async，确保任务执行的可靠性
4. 优化系统性能：
    - 实现多级缓存架构，显著提升任务数据访问效率
    - 使用布隆过滤器处理任务去重，保证执行精确

**项目成果**：
- 系统支持水平扩展，单集群支撑5万+任务调度
- 任务调度延迟控制在毫秒级
- 提供标准化API接口，已支持多个业务系统接入

<div style="display: flex; justify-content: space-between;">
  <div style="font-size: 15px;"><strong>产品线研发对外接口人（2022 年 10 月 ~ 2023 年 7 月 ）</strong></div>
  <div>项目负责人</div>
</div>

**项目描述**: 组织架构设置中，研发团队不直接对外。因此需要定期从研发团队挑选业务熟练的员工轮岗研发对外接口人,独自负责已售产品的线上问题维护及定制项目咨询。

**工作内容** : 

1. 负责所有在运行设备的故障问题排查及修复。
2. 负责全国各办事处销售人员的技术咨询。
3. 随时**oncall**处理办事处人员的报障。
4. 作为定制项目负责人，负责定制需求可行性分析，工期评估，编码开发。最后统筹测试人员与办事处技服人员进行项目测试，现场实施落地。

**工作亮点** :

1. 轮岗期间，问题查明率97%，问题解决延期率1% 。 两项数据均为公司各产品线前列

<div style="display: flex; justify-content: space-between;">
  <div style="font-size: 15px;"><strong>私有云物联网平台开发（2019 年 10 月 ~ 2022 年 10 月 ）</strong></div>
  <div>Golang/C 后端开发工程师</div>
</div>

**项目描述**: 私有云物联网平台开发，面向企业客户，提供设备接入，设备管理，数据可视化与设备告警推送等功能。 主要负责设备接入框架的设计与编码开发。

**技术栈** ： 物模型、多协议数据解析、skynet、lua、多级时间轮定时器、clickhouse

**工作内容** : 
1. 设计传感器物模型和设备接入框架，使用物模型+插件管理服务+协议插件（如 SNMP、485、Lora、Zigbee），处理不同协议的设备，保证全新设备接入工作量1h内。
2. 基于私有云单机实例运行的业务背景，在设备管理服务中使用二维时间轮算法（刻度+轮次）实现单机版定时器，稳定的保证了5W+设备在线状态变更，延迟命令下发等定时调度操作。
3. 通过skynet+lua插件的形式，搭建物联网平台的策略引擎，保证了平台的各种设备策略灵活运行。
4. 为满足运维分析和多样的监控大屏展示需求，进行时序数据库选型。引入clickhouse存储传感器数据，实现5万+设备状态实时刷新，聚合计算延迟低于1秒。得益于clickhouse的列式存储特性，把传感器本地数据保持最大时长从1 month提升至1 year。
5. 负责版本迭代后期的稳定性、性能问题排查：如 C/C++内存泄漏，进程CoreDump、服务器CPU,内存,磁盘IO异常、数据库死锁、HTTP接口性能优化等复杂问题。

**工作亮点** :
1. 平台目前有效接入3K+不同类型的传感器（UPS 、电表、交换机、温湿度等等）
2. 机房监控应用场景，在中小机房领域市场占用率第一
3. [中国发明] CN202211698938.6 数据处理方法、装置和计算机可读存储介质
4. [中国发明,中国发明授权] CN202010500382.X 一种物联网数据对接方法、系统及相关设备

## 教育经历

| 学校         | 学历，专业     | 时间              | 
| ------------ | -------------- | ----------------- |
| 东莞理工学院 | 本科，电子信息工程 | 2014.09 - 2018.6 |


## 荣誉奖项
* 2016年广东省合泰杯单片机设计大赛     **一等奖**
* 2016年东莞理工学院电子设计比赛       **一等奖**

<div style="page-break-after: always;"></div>