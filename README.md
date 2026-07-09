<div>
  <img style="100%" src="https://capsule-render.vercel.app/api?type=waving&height=110&section=header&reversal=true&text=Smooth%20pipelines,%20clear%20insights&fontSize=20&fontColor=b6c3d9&fontAlign=50&fontAlignY=50&rotate=0&stroke=-&animation=twinkling&descSize=20&descAlign=50&descAlignY=50&textBg=false&color=gradient"  />
</div>

###

<h1 align="center">Hi 👋, I'm Phat</h1>

###

<h3 align="center">Turning messy data into reliable insights</h3>

###

<div align="center">
  <img src="https://img.shields.io/badge/-Ho%20Chi%20Minh%20City-6f42c1?style=flat-square" alt="location badge" />
  <img src="https://img.shields.io/badge/-Final%20Year%20Student-2ea043?style=flat-square" alt="status badge" />
  <img src="https://img.shields.io/badge/-Data%20Engineer-1f6feb?style=flat-square" alt="goal badge" />
  <img src="https://img.shields.io/badge/-Open%20for%20Internship-d29922?style=flat-square" alt="internship badge" />
</div>

###

<h2 align="left">About Me</h2>

<p align="left">
  <b>Education:</b> Final-year IT student at <b>Saigon University</b>.<br>
  <b>Passion:</b> Crafting robust Data Pipelines, Big Data Architectures, and System Optimization.<br>
  <b>Mission:</b> Transforming raw data into actionable insights through scalable platforms.<br>
  <b>Currently Mastering:</b> Apache Airflow, Spark, dbt, and Cloud Infrastructure (AWS/GCP).<br>
  <b>Let's Talk:</b> Python, SQL, ETL/ELT, Data Modeling, and System Design.
</p>

---

<h2 align="left">Core Competencies</h2>

<p align="left">
  <b>Development:</b> Strong Python & SQL fundamentals with a focus on high-performance code.<br>
  <b>Engineering:</b> End-to-end pipeline orchestration: <i>Source ➔ Processing ➔ Storage ➔ Analytics</i>.<br>
  <b>Modern Stack:</b> Hands-on with Airflow, Kafka, RabbitMQ, Docker, and Vector Databases.<br>
  <b>Mindset:</b> Data-quality first. Proactive in debugging consistency and performance bottlenecks.
</p>

---

<h2 align="left">Tech Stack</h2>

###

<p align="left"><b>The Pipeline:</b> <code>Python → Airflow + Kafka → PostgreSQL → Analytics</code></p>
<p align="left">I choose tools based on reliability and maintainability: <b>Python</b> for flexible ETL logic, <b>Airflow</b> for orchestration, <b>Kafka/RabbitMQ</b> for event-driven flow, and <b>PostgreSQL</b> for structured analytics-ready storage.</p>

###

<h3 align="left">My Tech Stack</h3>

<div align="left">
  <img src="./techstack.svg" width="1000" alt="Tech Stack" />
</div>


###

---

<h2 align="left">Featured Projects</h2>
<div align="left">

### Data Platform Governance & Observability Stack

| Aspect | Details |
|---|---|
| **Problem** | Raw data assets (PostgreSQL, ClickHouse, Trino) lack metadata indexing, lineage visibility, and testing. Troubleshooting batch/streaming pipeline failures or SLO breaches requires manually SSH-ing to inspect isolated docker container logs. |
| **My Role** | Deployed OpenMetadata cataloging with MySQL/ES storage; integrated OpenLineage to automatically map runtime transformations from Airflow to cataloged assets; designed a multi-layer dbt pipeline (staging views to mart tables) with 17 data quality assertions; configured Prometheus metrics collection via StatsD to trigger Slack alerts on pipeline failures or SLO breaches (duration > 5 mins) using custom AlertManager templates; built Promtail and Loki log collectors to auto-discover and label Docker logs in Grafana. |
| **Scale / Impact** | Unified 14 dockerized services into a single bridged governance network. Automated E2E cataloging and data lineage graphs across 3 heterogeneous databases. Triggered alert notifications to Slack within 30 seconds of incidents. Reduced system debugging times from server-level logs to single LogQL queries. |
| **Tech** | `OpenMetadata` `Apache Airflow` `dbt` `OpenLineage` `Prometheus` `AlertManager` `Grafana Loki` `Promtail` `Docker` `Slack API` |
| **Learning outcomes** | Mastered enterprise metadata ingestion & lineage standardization, microservice metrics/log collection architectures, pipeline SLO monitoring, threshold alerting systems, and cross-project Docker networks. |

🔗 **Repository:** [phatle224/data-platform-governance](https://github.com/phatle224/data-platform-governance)

<br/>

### FMCG Real-Time Analytics Platform

| Aspect | Details |
|---|---|
| **Problem** | Traditional FMCG retail analysis relies on daily batch pipelines, delaying critical operational updates (e.g. stock replenishment, promotion monitoring) by 24+ hours. |
| **My Role** | Architected a dual-path (Hot/Cold) analytics platform. Configured ClickHouse Kafka Engine to ingest streaming transaction events directly from Kafka into MergeTree tables. Created Materialized Views on SummingMergeTrees for pre-aggregations. Set up Kafka Connect S3 Sink to archive raw streams to MinIO as Parquet files. Integrated Trino to enable federated queries joining ClickHouse (hot) and Iceberg/MinIO (cold) datasets. Built a Cube.js semantic layer serving Prometheus-monitored metrics to Grafana. |
| **Scale / Impact** | Handled peak workloads of 1,000 transactions/second. Reduced dashboard update lag from 24 hours to sub-2 seconds. Optimized dashboard query response times from 12s (PostgreSQL) to sub-50ms on 10M+ records. |
| **Tech** | `Python` `FastAPI` `Apache Kafka` `ClickHouse` `MinIO` `Apache Iceberg` `Trino` `Cube.js` `Grafana` `Docker` |
| **Learning outcomes** | Mastered Hot/Cold path architectural designs, OLAP indexing (MergeTree index granularity, sparse indexes), Apache Iceberg schema and partition evolution, Trino query execution plans and pushdown optimization, semantic caching in Cube.js, and stream processing instrumentation. |

🔗 **Repository:** [phatle224/fmcg-real-time-analytics](https://github.com/phatle224/fmcg-real-time-analytics)

<br/>

### Hybrid Data Ingestion & Streaming ETL Platform

| Aspect | Details |
|---|---|
| **Problem** | Ingest real-time transactional changes (CDC) and batch offline Excel files into a unified data warehouse with zero write conflicts or schema mismatch. |
| **My Role** | Architected the entire pipeline: constructed the CDC Consumer to parse Debezium PostgreSQL binlog events via Apache Kafka; built the Portal Backend in FastAPI employing Factory and Strategy patterns to dynamically validate Excel formats; implemented an incremental SQL-based deduplication strategy in dbt; deployed a containerized observability stack (Prometheus, Grafana, Kafka/PostgreSQL Exporters) for real-time consumer lag monitoring; and established a comprehensive dbt testing framework for data quality assurance. |
| **Scale / Impact** | Decoupled real-time write layers from reporting transformations. Standardized 7 disparate insurance schemas into a structured 11-table staging schema, processing batches via dbt every 5 minutes. Implemented 54 automated tests across 3 processing layers and established real-time monitoring of broker lag, database transaction rates, and pool status. |
| **Tech** | `Python` `FastAPI` `Apache Kafka` `Debezium` `dbt` `PostgreSQL` `Prometheus` `Grafana` `Docker` |
| **Learning outcomes** | Mastered real-time change data capture mechanics, event-driven backpressure management, dbt incremental modeling & data quality testing patterns, application of OOP design patterns in API services, and Prometheus/Grafana exporter architecture for platform observability. |

🔗 **Repository:** [phatle224/Hybrid-Data-Ingestion-Streaming-Platform](https://github.com/phatle224/Hybrid-Data-Ingestion-Streaming-Platform)

<br/>

### Agent SQL - Multi-Agent NL2SQL System

| Aspect | Details |
|---|---|
| **Problem** | Build an intelligent, enterprise-ready self-service analytics platform that translates natural language into secure SQL queries without exposing live production databases to business users. |
| **My Role** | Developed the **Import Service & Connection Hub** supporting 7 data adapters (PostgreSQL, MySQL, MongoDB, SQLite, Redis, DuckDB, and flat files) to dynamically extract schema metadata and ingest data into Supabase; engineered asynchronous event hooks for real-time schema cache invalidation; integrated Apache Kafka for asynchronous request/response queuing; and orchestrated performance load-testing using `k6`. |
| **Scale / Impact** | Delivered a highly secure, multi-tenant microservices architecture capable of seamless ingestion from NoSQL, relational, and column-oriented DBs with rule-based safety validation and active connection isolation. |
| **Tech** | `Python` `FastAPI` `Apache Kafka` `PostgreSQL` `Supabase` `Redis` `MongoDB` `DuckDB` `Docker` `k6` `Trivy` |
| **Learning outcomes** | Deepened expertise in multi-engine database adapters, microservices communication (Kafka messaging, async/await coordination), connection pooling, database security guardrails, and automated load/vulnerability scanning. |

🔗 **Repository:** [ductoanoxo/Agent_SQL](https://github.com/ductoanoxo/Agent_SQL)

</div>

###

---

<h2 align="left">GitHub Stats</h2>

###

<div align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=phatle224&hide_title=false&hide_rank=false&show_icons=true&include_all_commits=true&count_private=true&disable_animations=false&theme=dracula&locale=en&hide_border=false&order=1" height="150" alt="stats graph"  />
  <img src="https://github-activity-graph-one.vercel.app/graph?username=phatle224&radius=16&theme=material-palenight&area=true&order=5&custom_title=No%20pain%20no%20gain&v=1" height="290" alt="activity-graph graph"  />
</div>

###

---

<h2 align="left">Let's connect</h2>

###

<p align="left">I'm open to internship opportunities and collaboration around data engineering, backend systems, and practical product-building projects.</p>

###

<div align="center">
  <a href="https://www.linkedin.com/in/phat-le-674640330/" target="_blank">
    <img src="https://img.shields.io/static/v1?message=LinkedIn&logo=linkedin&label=&color=0077B5&logoColor=white&labelColor=&style=for-the-badge" height="25" alt="linkedin logo"  />
  </a>
  <a href="mailto:hongphatle224@gmail.com" target="_blank">
    <img src="https://img.shields.io/static/v1?message=Gmail&logo=gmail&label=&color=D14836&logoColor=white&labelColor=&style=for-the-badge" height="25" alt="gmail logo"  />
  </a>
  <a href="https://www.instagram.com/_fat.le44/" target="_blank">
    <img src="https://img.shields.io/static/v1?message=Instagram&logo=instagram&label=&color=E4405F&logoColor=white&labelColor=&style=for-the-badge" height="25" alt="instagram logo"  />
  </a>
</div>

###

<div>
  <img style="100%" src="https://capsule-render.vercel.app/api?type=waving&height=110&section=footer&reversal=true&text=It%20always%20seems%20impossible%20until%20it's%20done&fontSize=20&fontColor=b6c3d9&fontAlign=50&fontAlignY=50&rotate=0&stroke=-&animation=twinkling&descSize=20&descAlign=50&descAlignY=50&textBg=false&color=gradient"  />
</div>

###
