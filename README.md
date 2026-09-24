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
  <b>Experience:</b> Data Engineer with 9 months of production experience at <b>AFFINA Insurance</b>.<br>
  <b>Education:</b> IT Student at <b>Saigon University</b>.<br>
  <b>Passion:</b> Crafting reliable data pipelines, analytics-ready models, and maintainable event-driven systems.<br>
  <b>Currently Mastering:</b> Apache Airflow, Spark, and dbt.<br>
  <b>Let's Talk:</b> Python, SQL, CDC, ETL/ELT, Stream/Batch Processing, Data Modeling, and System Design.
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

<h2 align="left">Work Experience</h2>

### Data Engineer Intern | **AFFINA Insurance** _(Sep 2025 - May 2026)_

* **CDC Data Platform:** Implemented the MySQL CDC path with Debezium/Kafka and Python consumers from source topics through staging and reporting writes, handling insert, update, and delete events with schema-aware upserts.
* **Excel Ingestion & Standardization:** Built a FastAPI upload flow for seven offline insurance groups, using type-specific mappings and processors to normalize headers, dates, amounts, payer/insured fields, and validate business fields before staging writes.
* **Redis Deduplication:** Implemented duplicate handling that evolved from a four-field helper to normalized seven-field keys (`contractId`, `peopleName/name`, `majorName`, `companyProviderName`, `startDate`, `endDate`, `feeInsurance`), with online records taking precedence.
* **Event-Driven Integration:** Implemented RabbitMQ publishing and topology with a topic exchange, durable `doc_ocr_queue`, dead-letter queue, persistent JSON messages, and reconnect/retry handling; downstream OCR consumption was outside this repository.

*Tech Stack used:* `Python` • `FastAPI` • `MySQL` • `Debezium` • `Apache Kafka` • `RabbitMQ` • `Redis` • `Docker`

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

### Hybrid Data Ingestion & Streaming ELT Platform

| Aspect | Details |
|---|---|
| **Context** | Independent re-implementation of an ingestion pattern from my internship, rebuilt from scratch with synthetic Faker data; no company code or production data was used. |
| **My Role** | Combined PostgreSQL CDC based on WAL/logical decoding with Excel batch ingestion through FastAPI, then designed a four-layer dbt ELT pipeline. Implemented cross-channel deduplication with composite business keys and `ROW_NUMBER()` so online records take precedence over offline duplicates. |
| **Architecture** | 21 dbt models across 10 staging, 2 intermediate, 7 warehouse, and 2 mart models; local observability services for pipeline and database metrics. |
| **Verification** | 101 configured dbt tests. The latest local snapshot reports 95 pass, 2 warnings, and 4 documented synthetic-data failures; no production data is used. |
| **Tech** | `Python` `FastAPI` `Apache Kafka` `Debezium` `PostgreSQL` `dbt` `Prometheus` `Grafana` `Docker` |
| **Learning outcomes** | Practiced PostgreSQL WAL-based CDC, Kafka event flows, dbt ELT modeling and testing, schema-aware batch ingestion, cross-channel deduplication, and synthetic-data safety. |

🔗 **Repository:** [phatle224/hybrid-data-ingestion-streaming-platform](https://github.com/phatle224/hybrid-data-ingestion-streaming-platform)

<br/>

### InsightMesh - Privacy-Bounded NL2SQL Analytics Platform

| Aspect | Details |
|---|---|
| **What I built** | Local-first natural-language analytics for read-only PostgreSQL and MySQL, combining schema-aware retrieval, dialect-aware SQL generation, SQLGlot safety validation, verified execution, saved analyses, and dashboards. |
| **Measured scope** | 37 self-authored cases across PostgreSQL and MySQL variants of a six-table demo e-commerce schema. Status, execution, result, recall, and join-path accuracy were 100%; mean entity precision was 66.98%; all 5/5 unsafe cases were blocked. |
| **Model provenance** | Gemini 2.5 Flash was configured as primary, but the committed run used OpenRouter `openai/gpt-4o-mini` for all 27 SQL generations after Gemini timeout/rate-limit fallback. |
| **Tech** | `Python` `FastAPI` `PostgreSQL` `MySQL` `pgvector` `SQLGlot` `Next.js` `TypeScript` `Docker` |

🔗 **Repository:** [phatle224/insightmesh-multi-source-analytics](https://github.com/phatle224/insightmesh-multi-source-analytics)

<br/>

### Data Platform Governance & Observability Stack

| Aspect | Details |
|---|---|
| **Problem** | Raw data assets (PostgreSQL, ClickHouse, Trino) lack metadata indexing, lineage visibility, and testing. Troubleshooting batch/streaming pipeline failures or SLO breaches requires manually SSH-ing to inspect isolated docker container logs. |
| **My Role** | Deployed OpenMetadata cataloging with MySQL/ES storage; integrated OpenLineage to automatically map runtime transformations from Airflow to cataloged assets; designed a multi-layer dbt pipeline (staging views to mart tables) with 17 data quality assertions; configured Prometheus metrics collection via StatsD to trigger Slack alerts on pipeline failures or SLO breaches (duration > 5 mins) using custom AlertManager templates; built Promtail and Loki log collectors to auto-discover and label Docker logs in Grafana. |
| **Scale / Impact** | Unified 14 dockerized services into a single bridged governance network. Automated E2E cataloging and data lineage graphs across 3 heterogeneous databases. Triggered alert notifications to Slack within 30 seconds of incidents. Reduced system debugging times from server-level logs to single LogQL queries. |
| **Tech** | `OpenMetadata` `Apache Airflow` `dbt` `OpenLineage` `Prometheus` `AlertManager` `Grafana Loki` `Promtail` `Docker` `Slack API` |
| **Learning outcomes** | Mastered enterprise metadata ingestion & lineage standardization, microservice metrics/log collection architectures, pipeline SLO monitoring, threshold alerting systems, and cross-project Docker networks. |

🔗 **Repository:** [phatle224/data-platform-governance](https://github.com/phatle224/data-platform-governance)

</div>

---

<h2 align="left">📌 Pinned Repositories</h2>
<div align="left">

### PitchFlow - Reliable Football Data Lakehouse

Medallion Delta Lakehouse for 380 StatsBomb matches with idempotent ingestion, Airflow orchestration, and Metabase analytics.

🔗 [Repository](https://github.com/phatle224/pitchflow-reliable-football-data-lakehouse)

<br/>

### FMCG Real-Time Analytics Platform

Hot/cold FMCG analytics platform for 1,000 POS transactions per second with ClickHouse, Kafka, Iceberg, Trino, and Cube.js.

🔗 **Repository:** [phatle224/fmcg-real-time-analytics](https://github.com/phatle224/fmcg-real-time-analytics)

<br/>

### Agent SQL - Multi-Agent NL2SQL System

Multi-agent NL2SQL platform with seven data adapters, Kafka workflows, and rule-based safety isolation.

🔗 **Repository:** [phatle224/Agent_SQL](https://github.com/phatle224/Agent_SQL)

<br/>

### WordMesh Vocabulary Platform

Full-stack English vocabulary workspace for lookup, enrichment, spaced repetition, and learner progress.

🔗 [Repository](https://github.com/phatle224/wordmesh-vocab-builder)

<br/>

### AI for Education Platform

Collaborative LLM platform for intelligent tutoring, grading assistance, and personalized curriculum generation.

🔗 [Repository](https://github.com/phatle224/AI-FOR-EDUCATION)

</div>

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
  <a href="https://phatle-portfolio.vercel.app/" target="_blank">
    <img src="https://img.shields.io/static/v1?message=Portfolio&logo=vercel&label=&color=000000&logoColor=white&labelColor=&style=for-the-badge" height="25" alt="portfolio logo"  />
  </a>
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
