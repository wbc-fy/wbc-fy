<h1 align="center">你好，我是 wbc-fy 👋</h1>

<p align="center">
  <img src="https://komarev.com/ghpvc/?username=wbc-fy&color=blueviolet" alt="profile views" />
  <a href="https://github.com/wbc-fy/stock-time-series-analysis">
    <img src="https://img.shields.io/badge/StockAnalysisSystem-核心项目-1f4287?style=for-the-badge" alt="main project" />
  </a>
</p>

- 🎓 东北大学秦皇岛分校
- 📫 联系我：a55881838@163.com
- 🔭 目前专注于 **Web 前端开发**、**数据可视化** 与 **后端服务开发**
- 🌱 正在学习 Vue 3 生态、前端工程化与量化数据分析
- 💬 欢迎交流前端 / 后端 / 可视化相关话题

---

## 🚀 团队项目：股票时间序列分析系统（StockAnalysisSystem）

> 基于 **Python + Kafka + Flink + Java + MySQL + ClickHouse + Vue** 的股票数据采集、实时计算与智能分析平台。
> 数据链路：Tushare / AkShare → Python 采集服务 → MySQL / Kafka → Flink 实时指标 → ClickHouse → Vue 前端 & Streamlit 分析。
>
> 🔗 仓库地址：[wbc-fy/stock-time-series-analysis](https://github.com/wbc-fy/stock-time-series-analysis)

### 👤 我在项目中的分工

**角色：前端开发 & 数据可视化 & 后端模块开发**

#### 1. 量化分析可视化大屏
- 独立设计并实现 **1700+ 行**的数据可视化 Dashboard（`visualization/dashboard.html`）
- 整合行情概览、指标分析、监控等多维度数据的可视化展示

#### 2. Vue 前端功能开发
- 编写**股票近似搜索引擎**（`stockSearch.js`）——零依赖纯函数打分引擎：
  - 六级匹配层次：精确 → 前缀 → 包含 → 子序列 → 编辑距离模糊匹配
  - 支持中文子序列搜索（如"平银"→"平安银行"）、错字容忍、全角/半角归一化
  - 多字段加权（名称/代码/行业/地区）与多 token AND 语义
- 配套编写 `node --test` **单元测试**，保证搜索质量可回归验证

#### 3. 前端构建与部署
- 负责 Vue 前端的 **Vite 构建与部署**（Overview / Analysis / Collector / Monitor 四大视图）
- 编写 Windows 一键启动脚本（`start_frontend.cmd` 等），降低团队成员本地运行门槛

#### 4. 后端服务模块开发 —— Market API（重点）

独立负责 **Java Market API 服务**（Spring Boot，端口 8083）的设计与实现，为 Vue 前端提供真实行情数据查询：

- **REST 查询接口**：实现股票池、K 线（MySQL）、实时指标（ClickHouse）三类查询 API，严格的参数校验与语义化响应（400 非法参数 / 404 未知股票 / 503 依赖失败且错误脱敏）
- **Kafka 事务消费链路**：基于 `read_committed` 消费 Flink 输出的事务性指标 topic，ClickHouse 插入完整成功后才提交 offset；坏消息重试三次后 **fail-closed** 停止消费者并联动健康检查，不跳过、不丢毒消息
- **双数据源存储层**：MySQL 读取原始 OHLCV 日线，ClickHouse `ReplacingMergeTree` + `FINAL` 以 Kafka offset 为版本实现逻辑去重；指标精度采用 Decimal 六位 HALF_UP
- **单元测试覆盖**：Controller、Repository、FailClosed 处理器、配置与行为测试（JUnit），保障查询契约可回归

数据链路：`Flink → 事务 Kafka → Market API Consumer → ClickHouse → 查询 API → Vue 分析概览`

#### 5. 仓库协作维护
- 负责 Fork 仓库与上游的**版本同步与合并**（累计同步 V0.5–V0.8 及 10+ 个上游 PR）

### 🛠️ 项目中使用的技术

<p>
  <img src="https://img.shields.io/badge/Vue%203-4FC08D?style=flat-square&logo=vuedotjs&logoColor=white" alt="Vue" />
  <img src="https://img.shields.io/badge/Vite-646CFF?style=flat-square&logo=vite&logoColor=white" alt="Vite" />
  <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black" alt="JavaScript" />
  <img src="https://img.shields.io/badge/ECharts-AA344D?style=flat-square&logo=apacheecharts&logoColor=white" alt="ECharts" />
  <img src="https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=nodedotjs&logoColor=white" alt="Node.js" />
  <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python" />
  <img src="https://img.shields.io/badge/Spring%20Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white" alt="Spring Boot" />
  <img src="https://img.shields.io/badge/Kafka-231F20?style=flat-square&logo=apachekafka&logoColor=white" alt="Kafka" />
  <img src="https://img.shields.io/badge/ClickHouse-FFCC01?style=flat-square&logo=clickhouse&logoColor=black" alt="ClickHouse" />
  <img src="https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white" alt="MySQL" />
  <img src="https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white" alt="Git" />
</p>

---

## 📊 GitHub 统计

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=wbc-fy&show_icons=true&theme=tokyonight&hide_border=true" alt="GitHub stats" height="165" />
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=wbc-fy&layout=compact&theme=tokyonight&hide_border=true" alt="Top languages" height="165" />
</p>
