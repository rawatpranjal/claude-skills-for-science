# Expert Claude Code Skills and MCP Servers for Applied Scientists

[![License: MIT](https://img.shields.io/badge/license-MIT-green)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen)](CONTRIBUTING.md)
[![Claude Code](https://img.shields.io/badge/Claude-Code-blueviolet)](https://docs.anthropic.com/en/docs/claude-code)

A curated directory of Claude Code skills and MCP servers for applied scientists, organized by subfield. Every entry lists who built it. Entries are rank-ordered by utility within each section. Gaps are noted where no dedicated tooling exists.

> **~80 expert-vetted tools** across 15 subfields -- last updated April 2026

<details>
<summary><strong>What's New (Apr 2026)</strong></summary>
<br>

Initial release covering 15 subfields:

- **Applied Science** -- Experimentation, causal inference, Bayesian modeling, time series, classical ML, deep learning, NLP, recommender systems, survival analysis, optimization, geospatial, MLOps
- **Infrastructure** -- Econometrics & academic research, data infrastructure (databases, BI, notebooks)
- **Meta** -- Source repositories, skill marketplaces, learning resources

</details>

## Ecosystem Maturity

Overview of tooling availability by subfield.

| Subfield | Expert Skills | Expert MCP Servers | Maturity |
|----------|--------------|-------------------|----------|
| **MLOps** | Orchestra (W&B, MLflow, TB) | W&B, MLflow, Dagster, Prefect, Feast -- all official | Excellent |
| **Geospatial** | K-Dense GeoMaster | QGIS (540 stars), PostGIS Yukon, H3/bbox | Strong |
| **Experimentation** | A/B Test Setup | GrowthBook, Optimizely, PostHog -- all official | Strong |
| **Bayesian** | PyMC Labs | None dedicated | Skill-only |
| **Causal inference** | awesome-econ-ai-stuff (LSE) | DoWhy MCP v2 (42 tools) | Emerging |
| **Time series** | K-Dense TimesFM, aeon | Prophet MCP, Chronulus, Nixtla | Fragmented |
| **NLP** | Orchestra RAG skills | HuggingFace gateway | Generic only |
| **Optimization** | None | mcp-optimizer (PuLP + OR-Tools) | Minimal |
| **Classical ML** | K-Dense scikit-learn | Optuna (official) | Adequate |
| **Deep learning** | HF skills (official) | HF MCP, W&B, MLflow | Adequate |
| **Survival analysis** | None | None | Complete gap |
| **Recommender systems** | None | None | Complete gap |

---

## Contents

**Applied Science**
- [Experimentation & A/B Testing](#experimentation--ab-testing)
- [Causal Inference](#causal-inference)
- [Bayesian Modeling](#bayesian-modeling)
- [Time Series & Forecasting](#time-series--forecasting)
- [Classical ML](#classical-ml)
- [Deep Learning & Model Hubs](#deep-learning--model-hubs)
- [NLP & Text Analytics](#nlp--text-analytics)
- [Recommender Systems](#recommender-systems)
- [Survival Analysis](#survival-analysis)
- [Optimization & OR](#optimization--or)
- [Geospatial](#geospatial)
- [MLOps & Experiment Tracking](#mlops--experiment-tracking)

**Infrastructure**
- [Econometrics, Economic Data & Academic Research](#econometrics-economic-data--academic-research)
- [Data Infrastructure](#data-infrastructure)

**Meta**
- [Source Repositories & Discovery](#source-repositories--discovery)
- [Learning Resources](#learning-resources)
- [Contributing](#contributing)

---

## Experimentation & A/B Testing

MCP servers from experimentation platforms plus skills for test design. Ordered by breadth of experimentation features.

| Tool | By | Description | Links |
|------|-----|-------------|-------|
| **GrowthBook MCP** | GrowthBook team (official, parent repo 7K stars) | 14 tools: create feature gates, run A/B tests, manage experiments, fetch results. Parent platform includes CUPED, sequential testing, Bayesian stats, bandits, SRM checks. | [GitHub](https://github.com/growthbook/growthbook-mcp) |
| **PostHog MCP** | PostHog team (official) | Product analytics + experiments, funnels, retention via HogQL. `uv run posthog_mcp` | [Docs](https://posthog.com/docs/product-analytics/build-insights-mcp) |
| **Optimizely MCP** | Optimizely (official, closed beta) | Web + Feature Experimentation. Create/configure flags, diagnose evaluation, generate SDK integration code. | [Blog](https://www.optimizely.com/insights/blog/experimentation-mcp-server/) |
| **A/B Test Knowledge Base MCP** | Eddie Klickstark (CRO specialist, klickstark.agency) | Searchable access to 1,600+ real A/B test results with uplift data, psychological principles, and taxonomy. `uvx ab-test-kb-mcp` | Search "ab-test-kb-mcp" |
| **A/B Test Setup skill** | mysticaltech (marketingskills repo, 59 stars) | Structured framework for hypothesis generation, sample size calculation, metric selection. CRO-focused. `npx skillfish add mysticaltech/marketingskills ab-test-setup` | [GitHub](https://github.com/mysticaltech/marketingskills) |
| **statistical-analysis (K-Dense)** | K-Dense AI (7,800 star collection) | Power analysis, hypothesis testing, assumption checks, experimental design. Part of 170-skill scientific collection. | [GitHub](https://github.com/K-Dense-AI/claude-scientific-skills/tree/main/scientific-skills/statistical-analysis) |

**What's missing:** No skill or MCP implements standalone power analysis, sequential testing math, multi-armed bandit algorithms, or interference/spillover corrections. Platform integrations only — no statistical building blocks.

---

## Causal Inference

Skills and MCP servers for DiD, IV, RDD, matching, and identification strategies. Ordered by scope of causal methods covered.

| Tool | By | Description | Links |
|------|-----|-------------|-------|
| **DoWhy MCP v2.0** | lesong36 | Complete rewrite: 42 specialized tools across 7 modules — SCM/GCM construction, estimation, attribution, root cause analysis, counterfactual reasoning, sensitivity analysis, structure learning. Wraps Microsoft's DoWhy. | [GitHub](https://github.com/lesong36/dowhy_mcp) |
| **r-econometrics** | Antonio Mele (LSE economist, 205 star repo) | DiD, IV, RDD in R using fixest. Parallel-trends checks, event-study plots, McCrary density tests, robust/clustered SEs. | [GitHub](https://github.com/meleantonio/awesome-econ-ai-stuff) |
| **python-panel-data** | Antonio Mele (LSE) | Panel data with Python linearmodels. Fixed effects, DiD, panel regression workflows. | [GitHub](https://github.com/meleantonio/awesome-econ-ai-stuff) |
| **stata-regression** | Antonio Mele (LSE) | Regression in Stata with reghdfe, clustered SEs, publication-ready esttab output. | [GitHub](https://github.com/meleantonio/awesome-econ-ai-stuff) |
| **Stata Skill** | Dylan Moore | Comprehensive Stata: econometrics, causal inference, 20+ community packages, Python/R-to-Stata C plugin translation. 37+ reference files. | [GitHub](https://github.com/dylantmoore/stata-skill) |
| **robustness** | Zirui Song (empirical econ/finance) | Automated robustness checklist: sensitivity analysis, placebo tests, DiD-specific diagnostics, specification curves. | [GitHub](https://github.com/zirui-song/claude-skills) |
| **Research Ideation** | Antonio Mele (LSE) | Generate and refine causal research questions with economic thinking and identification strategy frameworks. | [GitHub](https://github.com/meleantonio/awesome-econ-ai-stuff) |

**What's missing:** No dedicated MCP for EconML, CausalML (Uber), CausalPFN, DoubleML, or synthetic control methods. These libraries are accessible through Jupyter MCP or direct Claude Code execution.

---

## Bayesian Modeling

PyMC-focused skills. The PyMC Labs skill includes auto-suggest hooks and reference documentation.

| Tool | By | Description | Links |
|------|-----|-------------|-------|
| **python-analytics-skills** | PyMC Labs (PyMC maintainers, 16 stars) | 3 skills + 12 reference docs. pymc-modeling: PyMC v5+, MCMC (nutpie, NumPyro backends), ArviZ diagnostics, hierarchical models, GLMs, GPs, BART, time series. pymc-testing: pytest for PyMC models. marimo-notebook: reactive notebooks. Auto-suggest hook triggers on "bayesian," "posterior," "hierarchical model." `./install.sh claude` | [GitHub](https://github.com/pymc-labs/python-analytics-skills) |
| **PyMC skill (K-Dense)** | K-Dense AI (7,800 star collection) | NUTS, Metropolis-Hastings, slice sampling, ADVI, GPs, time series models, ArviZ integration. Part of 170-skill scientific collection. | [GitHub](https://github.com/K-Dense-AI/claude-scientific-skills) |
| **pymc-bayesian-modeling** | davila7 (community) | PyMC 5.x+: hierarchical models, NUTS sampling, variational inference, LOO/WAIC model comparison, posterior predictive checks. | [AgentSkills](https://agentskills.so/skills/davila7-claude-code-templates-pymc-bayesian-modeling) |

**What's missing:** No MCP server or skill for Stan (CmdStan, PyStan, RStan), NumPyro, or Bayesian structural time series. The broader probabilistic programming ecosystem beyond PyMC is completely unserved.

---

## Time Series & Forecasting

Forecasting tools and time series classification. Ordered by breadth of methods.

| Tool | By | Description | Links |
|------|-----|-------------|-------|
| **Nixtla plugins** | intent-solutions-io (wrapping Nixtla's statsforecast + TimeGPT) | 3 plugins + 8 skills for production forecasting. M4 competition benchmarking, BigQuery integration, ERCOT energy grid prototype. Experimental (v1.7.0). `pip install -e packages/nixtla-claude-skills-installer && nixtla-skills init` | [GitHub](https://github.com/intent-solutions-io/plugins-nixtla) |
| **Prophet MCP** | ipradeep99 | Meta's Prophet with LLM-friendly statistical summaries, bounds validation, Chart.js visualization configs. Requires conda. | Search "prophet-mcp-server" |
| **Chronulus AI MCP** | Chronulus AI | API-based time series forecasting. `pip install chronulus-mcp` or `uvx chronulus-mcp` | Search "chronulus-mcp" |
| **MCP Analytics** | mcpanalytics.ai (commercial) | 60+ validated R modules via MCP: ARIMA, Prophet, ETS, STL decomposition, demand forecasting, Cox PH. Free tier (2K credits). `npx -y mcp-remote@latest https://api.mcpanalytics.ai/auth0` | [Website](https://mcpanalytics.ai) |
| **TimesFM (K-Dense)** | K-Dense AI (7,800 star collection) | Google's TimesFM foundation model: zero-shot forecasting for sales, sensors, energy, weather with prediction intervals. | [GitHub](https://github.com/K-Dense-AI/claude-scientific-skills) |
| **aeon (K-Dense)** | K-Dense AI | Comprehensive time series toolkit: 40+ distance metrics (DTW variants), ROCKET/MiniRocket classifiers, deep learning architectures. | [GitHub](https://github.com/K-Dense-AI/claude-scientific-skills) |

**What's missing:** No MCP server for NeuralProphet, Temporal Fusion Transformers, statsforecast standalone, or changepoint detection.

---

## Classical ML

Scikit-learn skills and hyperparameter optimization. Ordered by scope.

| Tool | By | Description | Links |
|------|-----|-------------|-------|
| **scikit-learn skill** | K-Dense AI (7,800 star collection) | Classification, regression, clustering, feature importance, model validation, cross-validation. | [GitHub](https://github.com/K-Dense-AI/claude-scientific-skills) |
| **Model Interpretability skill** | K-Dense AI | SHAP, feature importance, partial dependence plots, model explainability. | [GitHub](https://github.com/K-Dense-AI/claude-scientific-skills) |
| **Optuna MCP** | Optuna team (official) | Bayesian optimization, multi-objective optimization, visualization of optimization history. `uvx optuna-mcp` | [GitHub](https://github.com/optuna/optuna/releases) |
| **Kaggle MCP** | 54yyyu | Full Kaggle integration: competitions, datasets, notebooks, user management. One-line install. | [GitHub](https://github.com/54yyyu/kaggle-mcp) |
| **Hyperparameter Tuning skill** | jeremylongshore | Grid search, random search, Bayesian optimization via Optuna. | [tessl.io](https://tessl.io/registry/skills/github/jeremylongshore/claude-code-plugins-plus-skills/Tuning%20Hyperparameters) |

---

## Deep Learning & Model Hubs

Model training, evaluation, and deployment. Ordered by breadth of coverage.

| Tool | By | Description | Links |
|------|-----|-------------|-------|
| **Hugging Face Skills** | Hugging Face team (official, 6 skills) | Evaluation (vLLM/lighteval), training (fine-tuning with transformers), datasets (configs + SQL querying), CLI (Hub management), jobs (compute), spaces (app deployment). | [GitHub](https://github.com/huggingface/skills) |
| **Hugging Face MCP** | Hugging Face team (official) | Gateway to 900K+ models, 200K+ datasets, papers. Community Gradio tools available as MCP tools. | [Docs](https://huggingface.co/docs/hub/en/agents-mcp) |
| **AI-Research-SKILLs** | Orchestra Research (6,100 stars, 87 skills) | Research-grade: 5 RAG skills (Chroma, FAISS, Pinecone, Qdrant, Sentence Transformers), 3 MLOps skills (W&B 427 lines, MLflow 514 lines, TensorBoard 538 lines), distributed training, model architecture. `npx @orchestra-research/ai-research-skills` | [GitHub](https://github.com/Orchestra-Research/AI-Research-SKILLs) |
| **PyTorch Lightning (K-Dense)** | K-Dense AI (7,800 star collection) | Deep learning training, model building, validation with Lightning. | [GitHub](https://github.com/K-Dense-AI/claude-scientific-skills) |
| **Torch Geometric (K-Dense)** | K-Dense AI | Graph neural networks: network topology, node classification, link prediction. | [GitHub](https://github.com/K-Dense-AI/claude-scientific-skills) |
| **Dataset Viewer MCP** | privetin | Browse HF datasets without full download — filtering, statistics, data export. | [GitHub](https://github.com/privetin/dataset-viewer) |

---

## NLP & Text Analytics

NLP model access and retrieval-augmented generation. Ordered by scope.

| Tool | By | Description | Links |
|------|-----|-------------|-------|
| **Hugging Face MCP** | Hugging Face team (official) | Gateway to 200K+ NLP models: text classification, NER, embeddings, summarization, translation. Community Gradio tools as MCP tools. | [Docs](https://huggingface.co/docs/hub/en/agents-mcp) |
| **RAG Skills (Orchestra)** | Orchestra Research (6,100 stars) | 5 RAG implementations: Chroma, FAISS, Sentence Transformers, Pinecone, Qdrant. Research-grade with reference docs. | [GitHub](https://github.com/Orchestra-Research/AI-Research-SKILLs) |
| **Chat Analysis MCP** | rebots-online | Semantic analysis of conversational text: topic modeling, sentiment, concept extraction via embeddings and knowledge graphs. | Search "chat-analysis-mcp" |

**What's missing:** No dedicated MCP for BERTopic, LDA topic modeling, spaCy pipelines, NLTK, or scientific text RAG. Embedding management is unserved beyond the HF gateway.

---

## Recommender Systems

**Complete gap.** No expert-built skill or MCP server exists. Three generic templates on MCPMarket ("Recommendation Engine Systems," "AI Recommendation Engine," "Recommendation Engine Builder") mention scikit-learn and TensorFlow without integrating any actual recommendation library. No MCP wraps LightFM, Implicit, Surprise, RecBole, LensKit, or any learning-to-rank framework.

---

## Survival Analysis

**Complete gap.** No dedicated Claude Code skill or MCP server targets lifelines, scikit-survival, Cox PH, competing risks, or cure models. The only adjacent resources are K-Dense's scikit-survival skill (listed but minimal) and MCP Analytics' Cox PH module (commercial, among 60+ generic R modules). Dylan Moore's Stata skill includes survival analysis among 37+ reference files.

---

## Optimization & OR

Mathematical optimization solvers accessible via MCP. Ordered by solver breadth.

| Tool | By | Description | Links |
|------|-----|-------------|-------|
| **mcp-optimizer** | Dmitry Anchikov (3 stars) | Mathematical optimization: PuLP (LP/IP with CBC, GLPK, Gurobi, CPLEX) and Google OR-Tools (assignment, knapsack, routing, scheduling). Docker/K8s deployment, Prometheus monitoring. `pip install mcp-optimizer` or `uvx mcp-optimizer` | [GitHub](https://github.com/dmitryanchikov/mcp-optimizer) |
| **GurobiMCP** | KKonuru | Direct connection to on-device Gurobi solver for LP, MILP, QP, MIQCP. Runs locally. | [Glama](https://mcpservers.org/servers/KKonuru/GurobiMCP) |

**What's missing:** No skill for operations research methodology. No MCP for Pyomo, CVXPY, or dedicated pricing/inventory optimization.

---

## Geospatial

GIS, spatial analysis, and remote sensing. Ordered by breadth of spatial tools.

| Tool | By | Description | Links |
|------|-----|-------------|-------|
| **QGIS MCP** | Juan Jose Santos (540 stars) | Two-way QGIS Desktop communication: project management, layer manipulation, processing toolbox, arbitrary PyQGIS code, map rendering. `uv run qgis_mcp_server.py` | [GitHub](https://github.com/jjsantos01/qgis_mcp) |
| **QGISToolMCP** | Community | 333 geospatial processing tools across 14 specialized MCP services. | Search "QGISToolMCP" |
| **PostGIS Yukon MCP** | zmgiser | 32 professional spatial tools: DBSCAN clustering, k-NN, Voronoi diagrams, convex hulls, NL-to-SQL for PostGIS, spatial joins. | Search "postgis-yukon-mcp" |
| **bbox MCP** | iamvibhorsingh | Bounding box conversion (6 formats), Uber H3 hexagonal cell generation, Overpass queries binned into H3 for spatial density. `npx -y bbox-mcp-server` | [GitHub](https://github.com/iamvibhorsingh/bbox-mcp-server) |
| **GeoMaster (K-Dense)** | K-Dense AI (7,800 star collection) | Satellite imagery (Sentinel, Landsat, MODIS, SAR), spatial statistics, point cloud processing, cloud-native workflows (STAC, COG), 500+ code examples across 8 languages. | [GitHub](https://github.com/K-Dense-AI/claude-scientific-skills) |

**What's missing:** No spatial econometrics MCP (though RMCP's 429 R packages may partially cover this). No ArcGIS Online MCP.

---

## MLOps & Experiment Tracking

Experiment tracking, pipeline orchestration, and feature stores. Ordered by adoption.

| Tool | By | Description | Links |
|------|-----|-------------|-------|
| **W&B MCP** | Weights & Biases (official) | Query runs, sweeps, Weave traces, evaluations. Generate reports with visualizations. Hosted or local (`uvx wandb-mcp-server`). | [GitHub](https://github.com/wandb/wandb-mcp-server) |
| **MLflow MCP** | MLflow team (official, built into 3.4+) | Trace management, experiment tracking, model registry, feedback logging. `uv run --with "mlflow[mcp]>=3.5.1" mlflow mcp run` | [Docs](https://mlflow.org/docs/latest/genai/mcp/) |
| **Dagster MCP** | kyryl-opens-ml | Explore pipelines, monitor runs, manage assets, list jobs/repositories, materialize assets. `pip install mcp-server-dagster` | [GitHub](https://github.com/kyryl-opens-ml/mcp-server-dagster) |
| **Prefect MCP** | Prefect team (official) | Read-only access to deployments, flow runs, infrastructure. `claude mcp add prefect -- uvx --from prefect-mcp prefect-mcp-server` | [GitHub](https://github.com/PrefectHQ/prefect-mcp-server) |
| **Feast MCP** | Feast team (official, built into v0.56+) | Feature store access. Configure with `feature_server: type: mcp` in feature_store.yaml. AI assistants call `/get-online-features`. | [Feast Docs](https://docs.feast.dev) |
| **Airflow MCP** | hipposys-ltd | Natural language DAG management via Docker. Apache Airflow APIs for tasks, connections, variables. | [GitHub](https://github.com/hipposys-ltd/airflow-mcp) |
| **Orchestra MLOps skills** | Orchestra Research (6,100 stars) | 3 expert skills: W&B (427 lines + 3 ref docs), MLflow (514 lines + 3 refs), TensorBoard (538 lines + 3 refs). | [GitHub](https://github.com/Orchestra-Research/AI-Research-SKILLs) |

**What's missing:** No MCP for Tecton, Evidently AI (model monitoring/drift), or WhyLabs. Model monitoring is a confirmed gap.

---

## Econometrics, Economic Data & Academic Research

Skills and MCP servers for econometrics, academic writing, literature, and economic data access. Ordered by scope within each sub-category.

| Tool | By | Description | Links |
|------|-----|-------------|-------|
| **awesome-econ-ai-stuff** | Antonio Mele (LSE economist, 205 stars) | 18+ skills across 8 research stages: r-econometrics, python-panel-data, stata-regression, academic-paper-writer, lit-review-assistant, latex-econ-model, econ-visualization, api-data-fetcher, Beamer presentations. R/Python/Stata/Julia. | [GitHub](https://github.com/meleantonio/awesome-econ-ai-stuff) |
| **Sant'Anna Workflow** | Pedro Sant'Anna (Emory PhD econometrics) | 10 agents, 22 skills, 18 rules. Replication-first protocol (Stata-to-R, numeric tolerance <0.01), `/slide-excellence` with 6 parallel agents, quality gates. Used by 15+ research groups, produced 800+ slides. | [Website](https://psantanna.com/claude-code-my-workflow) |
| **clo-author** | Hugo Sant'Anna | 17 agents in 6 worker-critic pairs (Librarian, Explorer, Strategist, Coder, Writer, Storyteller). Phase-based severity gradient, AEA replication compliance. Full lifecycle from lit review to journal submission. | [GitHub](https://github.com/hugosantanna/clo-author) |
| **claude-skills** | Zirui Song (empirical econ/finance) | robustness (DiD diagnostics), lit-review, coding-standards, data-codebook, project-structure, referee-response. | [GitHub](https://github.com/zirui-song/claude-skills) |
| **scientific-writer** | K-Dense AI (19 writing skills) | Writing for Nature/Science/NeurIPS, grant templates (NSF, NIH, DOE, DARPA), scientific schematics (CONSORT, neural net viz), peer review, hypothesis generation. | [GitHub](https://github.com/K-Dense-AI/claude-scientific-writer) |
| **claudeblattman** | Chris Blattman (U Chicago economist) | Non-technical academic workflows: executive assistant, proposal writing with donor profiles, "Referee 2" audit protocol, PDF reading. | [GitHub](https://github.com/chrisblattman/claudeblattman) |
| **MCP-Stata** | Thomas Monk (LSE) | Connect Claude to Stata for do-files and output retrieval. | [GitHub](https://github.com/tmonk/mcp-stata) |
| **RMCP** | finite-sample | 52 statistical tools across 429 R packages: 55 econometrics, 48 time series, 32 Bayesian. HTTP + stdio. | [GitHub](https://github.com/finite-sample/rmcp) |
| **FRED MCP** | Stefano Amorelli | 800,000+ Federal Reserve Economic Data time series. | [GitHub](https://github.com/stefanoamorelli/fred-mcp-server) |
| **US Gov Open Data MCP** | lzinga | 300+ tools across 40+ APIs: Treasury, BLS, BEA, EIA, Census, SEC, World Bank. | [GitHub](https://github.com/lzinga/us-gov-open-data-mcp) |
| **Census MCP** | Brock Webb | Natural language queries mapped to 145+ demographic variables. | [GitHub](https://github.com/brockwebb/census-mcp-server) |
| **arXiv MCP** | blazickjp | Search, download, deep-read papers with analysis prompts. | [GitHub](https://github.com/blazickjp/arxiv-mcp-server) |
| **arxiv-latex MCP** | Takashi Ishida | Fetch LaTeX source instead of PDFs — critical for equation-heavy fields. | [GitHub](https://github.com/takashiishida/arxiv-latex-mcp) |
| **Semantic Scholar MCP** | FujishigeTemma | 200M+ papers with citation graphs and export. | [GitHub](https://github.com/FujishigeTemma/semantic-scholar-mcp) |
| **LaTeX MCP** | Yeok-c | Read cited papers, generate figures from data, compile LaTeX to PDF. | [GitHub](https://github.com/Yeok-c/latex-mcp-server) |

---

## Data Infrastructure

Best-of-breed picks only. One entry per platform — the most popular or the official server.

| Tool | By | Description | Links |
|------|-----|-------------|-------|
| **Anthropic Data Plugin** | Anthropic (official) | `/write-query` (optimized SQL), `/explore-data` (profiling), `/build-dashboard`, `/validate` (methodology review). Works with Snowflake, Databricks, BigQuery. | [GitHub](https://github.com/anthropics/knowledge-work-plugins/tree/main/data) |
| **DuckDB Skills** | DuckDB team (official plugin) | attach-db, query, read-file (CSV/JSON/Parquet/Avro/Excel/spatial), search docs. | [GitHub](https://github.com/duckdb/duckdb-skills) |
| **Snowflake MCP** | Snowflake Labs (official) | Cortex AI (Search, Analyst, Agent), SQL orchestration, semantic views. | [GitHub](https://github.com/Snowflake-Labs/mcp) |
| **BigQuery MCP** | LucasHild (most popular community) | Schema inspection, query execution. `uvx mcp-server-bigquery` | [GitHub](https://github.com/LucasHild/mcp-server-bigquery) |
| **DuckDB/MotherDuck MCP** | MotherDuck (official) | Local DuckDB, in-memory, S3, MotherDuck cloud. Read-only default. `uvx mcp-server-motherduck` | [GitHub](https://github.com/motherduckdb/mcp-server-motherduck) |
| **Databricks MCP** | Databricks Labs (official) | Unity Catalog, vector search, Genie spaces, Databricks SQL. | [GitHub](https://github.com/databrickslabs/mcp) |
| **PostgreSQL MCP** | MCP team (official reference) | Read-only database access with schema inspection. | [GitHub](https://github.com/modelcontextprotocol/servers) |
| **dbt MCP** | dbt Labs (official) | CLI execution (run, build, test, compile), metadata, Semantic Layer, text-to-SQL, lineage. | [GitHub](https://github.com/dbt-labs/dbt-mcp) |
| **Jupyter MCP** | Datalayer (most comprehensive) | Cell CRUD, kernel execution, multimodal output, OpenTelemetry. 12+ tools. `pip install jupyter-mcp-server` | [GitHub](https://github.com/datalayer/jupyter-mcp-server) |
| **Looker MCP** | Google (official) | Query Looker's semantic layer — no SQL needed. Optimized SQL generation, create dashboards. | [Docs](https://docs.cloud.google.com/looker/docs/connect-ide-to-looker-using-mcp-toolbox) |
| **Tableau MCP** | Tableau (official) | Full OAuth 2.1 support for data visualization and analytics. | [GitHub](https://github.com/tableau/tableau-mcp) |
| **Apache Superset MCP** | Superset team (built into 5.0+) | 128+ tools: datasets, charts, dashboards, SQL with RBAC enforcement. | [Docs](https://superset.apache.org/user-docs/using-superset/using-ai-with-superset/) |
| **Grafana MCP** | Grafana team (official) | Dashboards, PromQL, LogQL, alerting, incidents, on-call. `uvx mcp-grafana` | [GitHub](https://github.com/grafana/mcp-grafana) |

---

## Source Repositories & Discovery

Key repositories and directories. Ordered by relevance to applied scientists.

| Resource | By | Description | Links |
|----------|-----|-------------|-------|
| **K-Dense-AI/claude-scientific-skills** | K-Dense AI (7,800 stars) | 170 scientific skills: stats, ML, DL, Bayesian, time series, optimization, geospatial, 78+ databases. `npx skills add K-Dense-AI/claude-scientific-skills` | [GitHub](https://github.com/K-Dense-AI/claude-scientific-skills) |
| **Orchestra-Research/AI-Research-SKILLs** | Orchestra Research (6,100 stars) | 87 research-grade skills: RAG (5 impls), MLOps (W&B, MLflow, TB), distributed training, model architecture. `npx @orchestra-research/ai-research-skills` | [GitHub](https://github.com/Orchestra-Research/AI-Research-SKILLs) |
| **meleantonio/awesome-econ-ai-stuff** | Antonio Mele, LSE (205 stars) | 18+ economics/causal inference skills in R, Python, Stata, Julia. | [GitHub](https://github.com/meleantonio/awesome-econ-ai-stuff) |
| **pymc-labs/python-analytics-skills** | PyMC Labs (16 stars) | Bayesian modeling: 3 skills + 12 reference docs. `./install.sh claude` | [GitHub](https://github.com/pymc-labs/python-analytics-skills) |
| **anthropics/skills** | Anthropic (official, 102K stars) | Official skills: xlsx, skill-creator, document handling, web artifacts. `/plugin marketplace add` | [GitHub](https://github.com/anthropics/skills) |
| **anthropics/knowledge-work-plugins** | Anthropic (official, 11K stars) | Data analytics, finance, productivity plugins. | [GitHub](https://github.com/anthropics/knowledge-work-plugins) |
| **modelcontextprotocol/servers** | MCP team (official) | Authoritative MCP server repository — reference + community. | [GitHub](https://github.com/modelcontextprotocol/servers) |
| **PulseMCP** | PulseMCP | 11,150+ MCP servers with detailed metadata. Largest searchable directory. | [Website](https://www.pulsemcp.com/servers) |
| **Smithery.ai** | Smithery | 7,300+ MCP servers with CLI install. | [Website](https://smithery.ai) |
| **SkillsMP** | SkillsMP | 96,000+ Claude Code skills indexed from GitHub. | [Website](https://skillsmp.com) |
| **SkillHub** | SkillHub | 7,000+ AI-evaluated skills with playground testing. | [Website](https://www.skillhub.club) |
| **Official MCP Registry** | MCP community | Canonical catalog. 10,000+ servers. | [Website](https://registry.modelcontextprotocol.io) |

---

## Learning Resources

| Resource | By | Description | Links |
|----------|-----|-------------|-------|
| **Claude Code for Applied Economists** | Paul Goldsmith-Pinkham (Princeton) | 7-episode video series on Claude Code workflows for applied economics research. | [YouTube](https://www.youtube.com/results?search_query=paul+goldsmith-pinkham+claude+code) |
| **"Claude Code Changed How I Work"** | Scott Cunningham (Baylor, causal inference author) | Substack series on skills, MCP servers, and AI-assisted causal inference. | [Substack](https://substack.com/@causalinf) |
| **Getting Started with Claude Code for DS** | Dataquest | Plan mode, extended thinking, CLAUDE.md for data projects, Jupyter integration, production refactoring. | [Blog](https://dataquest.io/blog/getting-started-with-claude-code-for-data-scientists/) |
| **Skills Documentation** | Anthropic (official) | SKILL.md format, scopes, auto-invocation, progressive disclosure. | [Docs](https://docs.anthropic.com/en/docs/claude-code/skills) |
| **Skills PDF Guide** | Anthropic (official) | Comprehensive guide to building skills for Claude. | [PDF](https://resources.anthropic.com/hubfs/The-Complete-Guide-to-Building-Skill-for-Claude.pdf) |
| **Agent Skills Open Standard** | agentskills.io | SKILL.md specification adopted by 26+ platforms (GitHub Copilot, VS Code, Gemini CLI). Apache 2.0. | [Website](https://agentskills.io) |

---

## Contributing

Pull requests welcome. To add a tool, include who built it, what makes it unique, and a direct link.

## Author

[Pranjal Rawat](https://github.com/rawatpranjal)
