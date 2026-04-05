# Expert Claude Code Skills and MCP Servers for Applied Scientists

[![License: MIT](https://img.shields.io/badge/license-MIT-green)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen)](CONTRIBUTING.md)
[![Claude Code](https://img.shields.io/badge/Claude-Code-blueviolet)](https://docs.anthropic.com/en/docs/claude-code)

A curated directory of Claude Code skills and MCP servers for applied scientists, organized by subfield. Every entry lists who built it, a copy-pasteable install command, and the specific tools inside. Entries are rank-ordered by utility. Gaps noted where no dedicated tooling exists.

> **~55 sources** across 15 subfields -- last updated April 2026

<details>
<summary><strong>What's New (Apr 2026)</strong></summary>
<br>

Initial release covering 15 subfields:

- **Applied Science** -- Experimentation, causal inference, Bayesian modeling, time series, classical ML, deep learning, NLP, recommender systems, survival analysis, optimization, geospatial, MLOps
- **Infrastructure** -- Econometrics & academic research, data infrastructure (databases, BI, notebooks)
- **Meta** -- Source repositories, skill marketplaces, learning resources

</details>

## Ecosystem Maturity

| Subfield | Expert Skills | Expert MCP Servers | Maturity |
|----------|--------------|-------------------|----------|
| **MLOps** | Orchestra (W&B, MLflow, TB) | W&B, MLflow, Dagster, Prefect, Feast | Excellent |
| **Geospatial** | K-Dense GeoMaster | QGIS (540 stars), PostGIS Yukon, H3/bbox | Strong |
| **Experimentation** | A/B Test Setup | GrowthBook, Optimizely, PostHog | Strong |
| **Bayesian** | PyMC Labs | None dedicated | Skill-only |
| **Causal inference** | awesome-econ-ai-stuff (LSE) | DoWhy MCP v2 (42 tools) | Emerging |
| **Time series** | K-Dense TimesFM, aeon | Nixtla, Chronulus | Fragmented |
| **Classical ML** | K-Dense scikit-learn | Optuna (official) | Adequate |
| **Deep learning** | HF skills (official) | HF MCP, W&B, MLflow | Adequate |
| **NLP** | Orchestra RAG skills | HuggingFace MCP | Generic only |
| **Optimization** | None | mcp-optimizer (PuLP + OR-Tools) | Minimal |
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

MCP servers from experimentation platforms plus skills for test design.

| Source | By | Install | What's Inside |
|--------|-----|---------|--------------|
| **GrowthBook MCP** | GrowthBook (official, 7K stars) | `claude mcp add growthbook -- npx -y @growthbook/mcp@latest` | 14 tools: feature gates, A/B tests, experiment management, results. Platform has CUPED, sequential testing, Bayesian stats, bandits, SRM checks |
| **PostHog MCP** | PostHog (official) | `claude mcp add posthog -- uv run posthog_mcp` | Experiments, funnels, retention, feature flags via HogQL |
| **Optimizely MCP** | Optimizely (official, closed beta) | Closed beta — request access | Web + Feature Experimentation: create/configure flags, diagnose evaluation, SDK integration |
| **A/B Test KB MCP** | Eddie Klickstark (CRO, klickstark.agency) | `claude mcp add abtestkb -- uvx ab-test-kb-mcp` | 1,600+ real A/B test results with uplift data, psychological principles, taxonomy |
| **marketingskills** | mysticaltech (59 stars) | `git clone https://github.com/mysticaltech/marketingskills .claude/skills/marketing` | `/ab-test-setup` hypothesis generation, sample size calculation, metric selection |
| **K-Dense scientific-skills** | K-Dense AI (7,800 stars) | `npx skills add K-Dense-AI/claude-scientific-skills` | `/statistical-analysis` power analysis, hypothesis testing, assumption checks, experimental design |

**Gap:** No standalone sequential testing, multi-armed bandit, or interference/spillover skill.

---

## Causal Inference

DiD, IV, RDD, matching, and identification strategies.

| Source | By | Install | What's Inside |
|--------|-----|---------|--------------|
| **DoWhy MCP v2.0** | lesong36 | `pip install -e . && claude mcp add dowhy -- python -m dowhy_mcp` | 42 tools across 7 modules: SCM/GCM construction, estimation, attribution, root cause analysis, counterfactuals, sensitivity analysis, structure learning |
| **awesome-econ-ai-stuff** | Antonio Mele (LSE, 205 stars) | `git clone https://github.com/meleantonio/awesome-econ-ai-stuff .claude/skills/econ` | `/r-econometrics` DiD, IV, RDD with fixest, event-study plots, McCrary tests · `/python-panel-data` linearmodels, fixed effects · `/stata-regression` reghdfe, esttab · `/research-ideation` identification strategies |
| **Stata Skill** | Dylan Moore | `git clone https://github.com/dylantmoore/stata-skill .claude/skills/stata` | Comprehensive Stata: econometrics, causal inference, 20+ community packages, Python/R-to-Stata C plugin translation, 37+ reference files |
| **claude-skills** | Zirui Song (empirical econ/finance) | `git clone https://github.com/zirui-song/claude-skills .claude/skills/econ-empirical` | `/robustness` sensitivity analysis, placebo tests, DiD diagnostics, specification curves |

**Gap:** No MCP for EconML, CausalML (Uber), CausalPFN, DoubleML, or synthetic control. Accessible through Jupyter MCP.

---

## Bayesian Modeling

PyMC-focused skills with auto-suggest hooks and reference documentation.

| Source | By | Install | What's Inside |
|--------|-----|---------|--------------|
| **python-analytics-skills** | PyMC Labs (PyMC maintainers, 16 stars) | `git clone https://github.com/pymc-labs/python-analytics-skills && cd python-analytics-skills && ./install.sh claude` | `/pymc-modeling` PyMC v5+, MCMC (nutpie, NumPyro), ArviZ diagnostics, hierarchical models, GLMs, GPs, BART, time series · `/pymc-testing` pytest for PyMC · `/marimo-notebook` reactive notebooks. Auto-suggest on "bayesian," "posterior," "hierarchical model" |
| **K-Dense scientific-skills** | K-Dense AI (7,800 stars) | `npx skills add K-Dense-AI/claude-scientific-skills` | `/pymc` NUTS, Metropolis-Hastings, ADVI, GPs, time series, ArviZ integration |
| **pymc-bayesian-modeling** | davila7 (community) | `git clone https://github.com/davila7/claude-code-templates .claude/skills/pymc-community` | PyMC 5.x+: hierarchical models, NUTS, variational inference, LOO/WAIC, posterior predictive checks |

**Gap:** No skill or MCP for Stan, NumPyro, or Bayesian structural time series.

---

## Time Series & Forecasting

Forecasting tools and time series classification.

| Source | By | Install | What's Inside |
|--------|-----|---------|--------------|
| **Nixtla plugins** | intent-solutions-io | `pip install -e packages/nixtla-claude-skills-installer && nixtla-skills init` | 3 plugins + 8 skills: statsforecast + TimeGPT, M4 benchmarking, BigQuery integration, ERCOT energy prototype. Experimental v1.7.0 |
| **MCP Analytics** | mcpanalytics.ai (commercial) | `claude mcp add analytics -- npx -y mcp-remote@latest https://api.mcpanalytics.ai/auth0` | 60+ R modules: ARIMA, Prophet, ETS, STL decomposition, demand forecasting, Cox PH. Free tier (2K credits) |
| **Chronulus AI MCP** | Chronulus AI | `claude mcp add chronulus -- uvx chronulus-mcp` | API-based time series forecasting |
| **K-Dense scientific-skills** | K-Dense AI (7,800 stars) | `npx skills add K-Dense-AI/claude-scientific-skills` | `/timesfm` Google TimesFM foundation model, zero-shot forecasting with prediction intervals · `/aeon` 40+ distance metrics (DTW), ROCKET/MiniRocket classifiers, DL architectures |

**Gap:** No MCP for NeuralProphet, Temporal Fusion Transformers, or changepoint detection.

---

## Classical ML

Scikit-learn skills and hyperparameter optimization.

| Source | By | Install | What's Inside |
|--------|-----|---------|--------------|
| **K-Dense scientific-skills** | K-Dense AI (7,800 stars) | `npx skills add K-Dense-AI/claude-scientific-skills` | `/scikit-learn` classification, regression, clustering, feature importance, cross-validation · `/model-interpretability` SHAP, partial dependence, explainability |
| **Optuna MCP** | Optuna (official) | `claude mcp add optuna -- uvx optuna-mcp` | Bayesian optimization, multi-objective optimization, optimization history visualization |
| **Kaggle MCP** | 54yyyu | `claude mcp add kaggle -- npx -y @kaggle/mcp` | Competitions, datasets, notebooks, user management |

---

## Deep Learning & Model Hubs

Model training, evaluation, and deployment.

| Source | By | Install | What's Inside |
|--------|-----|---------|--------------|
| **Hugging Face** | HF team (official) | Skills: `git clone https://github.com/huggingface/skills .claude/skills/hf` / MCP: `claude mcp add hf -- npx -y @huggingface/mcp` | 6 skills: `/evaluation` vLLM/lighteval · `/training` fine-tuning · `/datasets` configs + SQL · `/cli` Hub management · `/jobs` compute · `/spaces` app deployment. MCP: 900K+ models, 200K+ datasets, Gradio tools |
| **AI-Research-SKILLs** | Orchestra Research (6,100 stars) | `npx @orchestra-research/ai-research-skills` | 5 RAG skills (Chroma, FAISS, Pinecone, Qdrant, Sentence Transformers) · 3 MLOps skills (W&B 427 lines, MLflow 514 lines, TensorBoard 538 lines) · distributed training · model architecture |
| **K-Dense scientific-skills** | K-Dense AI (7,800 stars) | `npx skills add K-Dense-AI/claude-scientific-skills` | `/pytorch-lightning` training, model building, validation · `/torch-geometric` GNNs, node classification, link prediction |
| **Dataset Viewer MCP** | privetin | `claude mcp add dataview -- npx -y dataset-viewer-mcp` | Browse HF datasets without download: filtering, statistics, data export |

---

## NLP & Text Analytics

See also: Hugging Face MCP and Orchestra RAG skills in [Deep Learning](#deep-learning--model-hubs).

| Source | By | Install | What's Inside |
|--------|-----|---------|--------------|
| **Chat Analysis MCP** | rebots-online | Search "chat-analysis-mcp" | Semantic analysis of conversational text: topic modeling, sentiment, concept extraction via embeddings and knowledge graphs |

**Gap:** No dedicated MCP for BERTopic, spaCy, LDA, NLTK, or scientific text RAG.

---

## Recommender Systems

**Complete gap.** No skill or MCP wraps LightFM, Implicit, Surprise, RecBole, LensKit, or any learning-to-rank framework. Generic templates exist on MCPMarket but integrate no actual recommendation library.

---

## Survival Analysis

**Complete gap.** No dedicated skill or MCP targets lifelines, scikit-survival, Cox PH, competing risks, or cure models. MCP Analytics includes Cox PH among 60+ generic R modules. Dylan Moore's Stata skill includes survival analysis among 37+ reference files.

---

## Optimization & OR

Mathematical optimization solvers via MCP.

| Source | By | Install | What's Inside |
|--------|-----|---------|--------------|
| **mcp-optimizer** | Dmitry Anchikov | `claude mcp add optimizer -- uvx mcp-optimizer` | PuLP (LP/IP with CBC, GLPK, Gurobi, CPLEX) + Google OR-Tools (assignment, knapsack, routing, scheduling). Docker/K8s, Prometheus monitoring |
| **GurobiMCP** | KKonuru | See [Glama](https://mcpservers.org/servers/KKonuru/GurobiMCP) | Direct on-device Gurobi solver: LP, MILP, QP, MIQCP |

**Gap:** No MCP for Pyomo, CVXPY, or pricing/inventory optimization. No OR methodology skill.

---

## Geospatial

GIS, spatial analysis, and remote sensing.

| Source | By | Install | What's Inside |
|--------|-----|---------|--------------|
| **QGIS MCP** | Juan Jose Santos (540 stars) | `claude mcp add qgis -- uv run qgis_mcp_server.py` | Two-way QGIS Desktop: project management, layer manipulation, processing toolbox, PyQGIS code, map rendering |
| **QGISToolMCP** | Community | Search "QGISToolMCP" | 333 geospatial processing tools across 14 specialized MCP services |
| **PostGIS Yukon MCP** | zmgiser | Search "postgis-yukon-mcp" | 32 spatial tools: DBSCAN clustering, k-NN, Voronoi, convex hulls, NL-to-SQL for PostGIS, spatial joins |
| **bbox MCP** | iamvibhorsingh | `claude mcp add bbox -- npx -y bbox-mcp-server` | Bounding box conversion (6 formats), Uber H3 hexagonal cells, Overpass queries binned into H3 |
| **K-Dense scientific-skills** | K-Dense AI (7,800 stars) | `npx skills add K-Dense-AI/claude-scientific-skills` | `/geomaster` satellite imagery (Sentinel, Landsat, MODIS, SAR), spatial stats, point clouds, STAC/COG workflows, 500+ examples |

**Gap:** No spatial econometrics MCP. No ArcGIS Online MCP.

---

## MLOps & Experiment Tracking

Experiment tracking, pipeline orchestration, and feature stores.

| Source | By | Install | What's Inside |
|--------|-----|---------|--------------|
| **W&B MCP** | Weights & Biases (official) | `claude mcp add wandb --transport http https://mcp.withwandb.com/mcp` | Runs, sweeps, Weave traces, evaluations, report generation. Also local: `uvx wandb-mcp-server` |
| **MLflow MCP** | MLflow (official, built into 3.4+) | `claude mcp add mlflow -- uv run --with "mlflow[mcp]>=3.5.1" mlflow mcp run` | Trace management, experiment tracking, model registry, feedback logging |
| **Dagster MCP** | kyryl-opens-ml | `claude mcp add dagster -- pip install mcp-server-dagster` | Explore pipelines, monitor runs, manage assets, list jobs, materialize assets |
| **Prefect MCP** | Prefect (official) | `claude mcp add prefect -- uvx --from prefect-mcp prefect-mcp-server` | Read-only: deployments, flow runs, infrastructure |
| **Feast MCP** | Feast (official, built into v0.56+) | Configure `feature_server: type: mcp` in feature_store.yaml | Feature store: `/get-online-features` for real-time feature retrieval |
| **Airflow MCP** | hipposys-ltd | `claude mcp add airflow -- docker run hipposys/airflow-mcp` | DAG management, tasks, connections, variables via Airflow APIs |
| **AI-Research-SKILLs** | Orchestra Research (6,100 stars) | `npx @orchestra-research/ai-research-skills` | `/wandb` (427 lines + 3 refs) · `/mlflow` (514 lines + 3 refs) · `/tensorboard` (538 lines + 3 refs) |

**Gap:** No MCP for Tecton, Evidently AI (drift detection), or WhyLabs. Model monitoring is unserved.

---

## Econometrics, Economic Data & Academic Research

Skills and MCP servers for econometrics, academic writing, literature, and economic data.

| Source | By | Install | What's Inside |
|--------|-----|---------|--------------|
| **awesome-econ-ai-stuff** | Antonio Mele (LSE, 205 stars) | `git clone https://github.com/meleantonio/awesome-econ-ai-stuff .claude/skills/econ` | `/academic-paper-writer` journal conventions · `/lit-review-assistant` citation management, gap identification · `/latex-econ-model` theorems, proofs · `/econ-visualization` ggplot2 pub-quality charts · `/api-data-fetcher` FRED, World Bank · `/beamer` presentations with coefficient plots |
| **scientific-writer** | K-Dense AI | `npx skills add K-Dense-AI/claude-scientific-writer` | 19 writing skills: Nature/Science/NeurIPS style · grant templates (NSF, NIH, DOE, DARPA) · scientific schematics (CONSORT, neural net viz) · peer review · hypothesis generation |
| **claude-skills** | Zirui Song (empirical econ/finance) | `git clone https://github.com/zirui-song/claude-skills .claude/skills/econ-empirical` | `/robustness` DiD diagnostics · `/lit-review` paper summarization · `/coding-standards` Python/Stata · `/data-codebook` dataset docs · `/project-structure` reproducible dirs · `/referee-response` R&R formatting |
| **Sant'Anna Workflow** | Pedro Sant'Anna (Emory) | [See website](https://psantanna.com/claude-code-my-workflow) | 10 agents, 22 skills, 18 rules. Replication-first (Stata-to-R, tolerance <0.01), `/slide-excellence` with 6 parallel agents. Used by 15+ research groups |
| **clo-author** | Hugo Sant'Anna | `git clone https://github.com/hugosantanna/clo-author .claude/skills/clo-author` | 17 agents in 6 worker-critic pairs (Librarian, Explorer, Strategist, Coder, Writer, Storyteller). AEA replication compliance. Full lifecycle |
| **claudeblattman** | Chris Blattman (U Chicago) | `git clone https://github.com/chrisblattman/claudeblattman .claude/skills/blattman` | Executive assistant, proposal writing with donor profiles, "Referee 2" audit protocol, PDF reading |
| **MCP-Stata** | Thomas Monk (LSE) | `claude mcp add stata -- python -m mcp_stata` | Connect Claude to Stata for do-files and output retrieval |
| **RMCP** | finite-sample | See [GitHub](https://github.com/finite-sample/rmcp) | 52 tools across 429 R packages: 55 econometrics, 48 time series, 32 Bayesian |
| **FRED MCP** | Stefano Amorelli | See [GitHub](https://github.com/stefanoamorelli/fred-mcp-server) | 800,000+ Federal Reserve Economic Data time series |
| **US Gov Open Data MCP** | lzinga | See [GitHub](https://github.com/lzinga/us-gov-open-data-mcp) | 300+ tools across 40+ APIs: Treasury, BLS, BEA, EIA, Census, SEC, World Bank |
| **Census MCP** | Brock Webb | See [GitHub](https://github.com/brockwebb/census-mcp-server) | Natural language queries mapped to 145+ demographic variables |
| **arXiv MCP** | blazickjp | See [GitHub](https://github.com/blazickjp/arxiv-mcp-server) | Search, download, deep-read papers with analysis prompts |
| **arxiv-latex MCP** | Takashi Ishida | See [GitHub](https://github.com/takashiishida/arxiv-latex-mcp) | Fetch LaTeX source instead of PDFs |
| **Semantic Scholar MCP** | FujishigeTemma | See [GitHub](https://github.com/FujishigeTemma/semantic-scholar-mcp) | 200M+ papers with citation graphs and export |
| **LaTeX MCP** | Yeok-c | See [GitHub](https://github.com/Yeok-c/latex-mcp-server) | Read cited papers, generate figures, compile LaTeX to PDF |

---

## Data Infrastructure

Best-of-breed only. One entry per platform.

| Source | By | Install | What's Inside |
|--------|-----|---------|--------------|
| **Anthropic Data Plugin** | Anthropic (official) | `claude plugin add data` | `/write-query` optimized SQL · `/explore-data` profiling · `/build-dashboard` · `/validate` methodology review. Snowflake, Databricks, BigQuery |
| **DuckDB Skills** | DuckDB (official) | `claude plugin add duckdb` | attach-db, query, read-file (CSV/JSON/Parquet/Avro/Excel/spatial), search docs |
| **Snowflake MCP** | Snowflake Labs (official) | See [GitHub](https://github.com/Snowflake-Labs/mcp) | Cortex AI (Search, Analyst, Agent), SQL orchestration, semantic views |
| **BigQuery MCP** | LucasHild | `claude mcp add bigquery -- uvx mcp-server-bigquery` | Schema inspection, query execution |
| **DuckDB/MotherDuck MCP** | MotherDuck (official) | `claude mcp add duckdb -- uvx mcp-server-motherduck` | Local DuckDB, in-memory, S3, MotherDuck cloud. Read-only default |
| **Databricks MCP** | Databricks Labs (official) | See [GitHub](https://github.com/databrickslabs/mcp) | Unity Catalog, vector search, Genie spaces, Databricks SQL |
| **PostgreSQL MCP** | MCP team (official) | See [GitHub](https://github.com/modelcontextprotocol/servers) | Read-only database access with schema inspection |
| **dbt MCP** | dbt Labs (official) | See [GitHub](https://github.com/dbt-labs/dbt-mcp) | CLI execution (run, build, test), metadata, Semantic Layer, text-to-SQL, lineage |
| **Jupyter MCP** | Datalayer | `claude mcp add jupyter -- pip install jupyter-mcp-server` | Cell CRUD, kernel execution, multimodal output, OpenTelemetry. 12+ tools |
| **Looker MCP** | Google (official) | See [Docs](https://docs.cloud.google.com/looker/docs/connect-ide-to-looker-using-mcp-toolbox) | Query semantic layer (no SQL needed), create dashboards |
| **Tableau MCP** | Tableau (official) | See [GitHub](https://github.com/tableau/tableau-mcp) | OAuth 2.1 data visualization and analytics |
| **Apache Superset MCP** | Superset (built into 5.0+) | See [Docs](https://superset.apache.org/user-docs/using-superset/using-ai-with-superset/) | 128+ tools: datasets, charts, dashboards, SQL with RBAC |
| **Grafana MCP** | Grafana (official) | `claude mcp add grafana -- uvx mcp-grafana` | Dashboards, PromQL, LogQL, alerting, incidents, on-call |

---

## Source Repositories & Discovery

| Source | By | Install | What's Inside |
|--------|-----|---------|--------------|
| **K-Dense-AI/claude-scientific-skills** | K-Dense AI (7,800 stars) | `npx skills add K-Dense-AI/claude-scientific-skills` | 170 scientific skills: stats, ML, DL, Bayesian, time series, optimization, geospatial, 78+ databases |
| **Orchestra-Research/AI-Research-SKILLs** | Orchestra Research (6,100 stars) | `npx @orchestra-research/ai-research-skills` | 87 skills: RAG (5 impls), MLOps (W&B, MLflow, TB), distributed training, model architecture |
| **awesome-econ-ai-stuff** | Antonio Mele, LSE (205 stars) | `git clone https://github.com/meleantonio/awesome-econ-ai-stuff .claude/skills/econ` | 18+ economics/causal inference skills in R, Python, Stata, Julia |
| **python-analytics-skills** | PyMC Labs (16 stars) | `./install.sh claude` | Bayesian modeling: 3 skills + 12 reference docs |
| **anthropics/skills** | Anthropic (official, 102K stars) | `claude plugin add skills` | xlsx, skill-creator, document handling, web artifacts |
| **anthropics/knowledge-work-plugins** | Anthropic (official, 11K stars) | `claude plugin add data` | Data analytics, finance, productivity plugins |
| **modelcontextprotocol/servers** | MCP team (official) | N/A | Authoritative MCP server repository |
| **PulseMCP** | PulseMCP | [pulsemcp.com](https://www.pulsemcp.com/servers) | 11,150+ MCP servers, largest directory |
| **Smithery.ai** | Smithery | [smithery.ai](https://smithery.ai) | 7,300+ MCP servers with CLI install |
| **SkillsMP** | SkillsMP | [skillsmp.com](https://skillsmp.com) | 96,000+ skills indexed from GitHub |
| **SkillHub** | SkillHub | [skillhub.club](https://www.skillhub.club) | 7,000+ AI-evaluated skills with playground |
| **MCP Registry** | MCP community | [registry.modelcontextprotocol.io](https://registry.modelcontextprotocol.io) | Canonical catalog, 10,000+ servers |

---

## Learning Resources

| Source | By | Install | What's Inside |
|--------|-----|---------|--------------|
| **Claude Code for Applied Economists** | Paul Goldsmith-Pinkham (Princeton) | [YouTube](https://www.youtube.com/results?search_query=paul+goldsmith-pinkham+claude+code) | 7-episode video series on Claude Code workflows for applied economics |
| **"Claude Code Changed How I Work"** | Scott Cunningham (Baylor) | [Substack](https://substack.com/@causalinf) | Series on skills, MCP servers, AI-assisted causal inference |
| **Getting Started with Claude Code for DS** | Dataquest | [Blog](https://dataquest.io/blog/getting-started-with-claude-code-for-data-scientists/) | Plan mode, CLAUDE.md for data projects, Jupyter integration |
| **Skills Documentation** | Anthropic (official) | [Docs](https://docs.anthropic.com/en/docs/claude-code/skills) | SKILL.md format, scopes, auto-invocation, progressive disclosure |
| **Agent Skills Open Standard** | agentskills.io | [Website](https://agentskills.io) | SKILL.md spec adopted by 26+ platforms. Apache 2.0 |

---

## Contributing

Pull requests welcome. To add a tool, include who built it, a one-liner install, and what's inside.

## Author

[Pranjal Rawat](https://github.com/rawatpranjal)
