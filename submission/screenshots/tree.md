_lakehouse/
├── bronze/
│   ├── agent_traces/
│   │   └── _delta_log/
│   ├── docs_multimodal/
│   │   └── _delta_log/
│   └── llm_calls_raw/
│       └── _delta_log/
│
├── silver/
│   ├── agent_trajectories/
│   │   ├── agent_version=policy-v2/
│   │   ├── agent_version=policy-v3/
│   │   └── _delta_log/
│   ├── llm_calls/
│   │   ├── date=2026-04-01/
│   │   ├── date=2026-04-02/
│   │   ├── ...
│   │   ├── date=2026-04-08/
│   │   └── _delta_log/
│   └── training_corpus_governed/
│       ├── provenance_bucket=licensed/
│       ├── provenance_bucket=public_domain/
│       ├── provenance_bucket=scraped_optout_checked/
│       ├── provenance_bucket=synthetic/
│       ├── provenance_bucket=UNCLASSIFIED/
│       └── _delta_log/
│
├── gold/
│   ├── agent_performance/
│   │   └── _delta_log/
│   └── llm_daily_metrics/
│       ├── date=2026-04-01/
│       ├── date=2026-04-02/
│       ├── ...
│       ├── date=2026-04-08/
│       └── _delta_log/
│
├── iceberg/
│   ├── nb5/
│   │   └── warehouse/lake/llm_events/metadata/
│   ├── nb6/
│   │   └── warehouse/lake/maint/metadata/
│   ├── nb8/
│   │   └── warehouse/lake/trajectories/metadata/
│   └── smoke/
│
├── blobs/
│
└── scratch/
    ├── customers_tt/
    │   └── _delta_log/
    ├── docs_cdf/
    │   ├── _change_data/
    │   └── _delta_log/
    ├── docs_intable/
    │   └── _delta_log/
    ├── emb_f32/
    │   └── _delta_log/
    ├── emb_int8/
    │   └── _delta_log/
    ├── events_smallfiles/
    │   └── _delta_log/
    ├── maint_events/
    │   └── _delta_log/
    ├── media_inline/
    │   └── _delta_log/
    ├── media_pointer/
    │   └── _delta_log/
    ├── users_delta/
    │   └── _delta_log/
    └── vector_index_external/
        └── _delta_log/
