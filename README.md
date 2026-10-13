# wbc-fy

东北大学秦皇岛分校 · a55881838@163.com

关注方向：Web 前端开发、数据可视化、后端服务开发。

---

## 项目：股票时间序列分析系统

基于 Python、Kafka、Flink、Java、MySQL、ClickHouse 与 Vue 的股票数据采集、实时计算与分析平台。数据链路为：Tushare / AkShare 采集 → MySQL / Kafka → Flink 实时指标 → ClickHouse → Market API → Vue 前端。

仓库：[wbc-fy/stock-time-series-analysis](https://github.com/wbc-fy/stock-time-series-analysis)

### 承担工作

**前端开发**

- 负责 Vue 前端四大视图（概览、分析、采集、监控）的功能开发与 Vite 构建部署，编写本地启动脚本降低协作成本。
- 实现股票近似搜索模块：零依赖纯函数打分引擎，支持精确、前缀、包含、子序列、编辑距离六级匹配，覆盖中文子序列与错字容忍，配套 node:test 单元测试保证可回归。

**数据可视化**

- 独立设计与实现量化分析可视化大屏，整合行情概览、指标分析与监控数据的展示。

**数据收集**

- 负责 Python 采集服务的采集适配器开发，接入 Tushare 与 AkShare 双数据源，基于统一基类实现日线行情、每日估值、交易日历及指数/行业成分股的采集接口。
- 实现数据校验与标准化：封装带协议检查的 Tushare 客户端，对网络、配额、权限、Schema 等异常进行分类隔离，统一各数据源的字段格式后再进入存储链路。

**后端开发**

- 参与 Market API 服务（Java / Spring Boot）的开发，实现股票池、K 线与实时指标的查询接口，数据层对接 MySQL 与 ClickHouse，并通过 Kafka 事务消费完成指标落库，为前端提供真实行情数据。

**协作维护**

- 负责 Fork 仓库与上游的版本同步与合并。

### 技术栈

Python / Pandas / Vue 3 / Vite / JavaScript / Java / Spring Boot / Kafka / MySQL / ClickHouse / Git

---

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=wbc-fy&show_icons=true&theme=default&hide_border=true&count_private=true" alt="GitHub stats" height="150" />
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=wbc-fy&layout=compact&theme=default&hide_border=true" alt="Top languages" height="150" />
</p>
