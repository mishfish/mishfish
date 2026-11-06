<p align="center">
  <a href="https://github.com/mishfish">
    <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=500&size=20&duration=2600&pause=900&color=2DD4BF&center=true&vCenter=true&width=620&height=50&lines=%24+whoami;mykhailo+bohdanov+%E2%80%94+data+%26+platform+engineer;%24+cat+interests.txt;CDC+%C2%B7+Kafka+%C2%B7+ClickHouse+%C2%B7+Go;%24+uptime;8%2B+years%2C+still+shipping+%F0%9F%9A%A2" alt="whoami"/>
  </a>
</p>

```sql
mishfish=> SELECT * FROM engineer WHERE handle = 'mishfish';
```

```
 field     | value
-----------+------------------------------------------------------------
 name      | Mykhailo (Misha) Bohdanov
 role      | Software / Data Engineer @ AUTODOC
 location  | Odesa, Ukraine 🇺🇦
 daytime   | CDC pipelines, database tooling, Go services
(4 rows)
```

<p align="center">
  <img src="https://skillicons.dev/icons?i=go,python,postgres,kafka,docker,grafana,prometheus,linux&theme=dark" alt="stack"/>
</p>
<p align="center">
  <img src="https://img.shields.io/badge/Debezium-0f172a?style=flat-square&logo=apachekafka&logoColor=2dd4bf"/>
  <img src="https://img.shields.io/badge/ClickHouse-0f172a?style=flat-square&logo=clickhouse&logoColor=FFCC01"/>
  <img src="https://img.shields.io/badge/Directus-0f172a?style=flat-square&logo=directus&logoColor=white"/>
  <img src="https://img.shields.io/badge/LLM_tooling-0f172a?style=flat-square&logo=openai&logoColor=white"/>
</p>

---

### ⚡ [energy-data-platform](https://github.com/mishfish/energy-data-platform)

Data platform for the European electricity market. ENTSO-E prices, load and generation + weather, streamed end to end with CDC. The point is the boring hard parts: delivery guarantees, observability, failure handling, runbooks, 30+ ADRs. Includes a fake ENTSO-E API with fault injection, so the whole stack runs locally without tokens.

```mermaid
flowchart LR
    A[ENTSO-E / Open-Meteo] --> B[Go ingest]
    B --> C[(Postgres)]
    C -- Debezium --> D{{Kafka}}
    D --> E[Go sink]
    E --> F[(ClickHouse)]
    F --> G[Grafana / Streamlit]
```

### 💬 [igcrm](https://github.com/mishfish/igcrm)

Customer cards built automatically from Instagram Direct. Meta webhooks → Go → Postgres; after a pause in the chat an LLM fills in name, phone, city, Nova Poshta branch and sizes, and drafts an order when the customer confirms. Every change goes to review with a diff; Directus is the UI.

`Go` `Postgres` `Directus` `Caddy` `LLM`

---

<p align="center"><sub><code>-- exactly once is a lie, idempotency is not</code></sub></p>
