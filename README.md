# Claude Skills and MCPs for Applied and Data Science

[![License: MIT](https://img.shields.io/badge/license-MIT-green)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen)](CONTRIBUTING.md)
[![Claude Code](https://img.shields.io/badge/Claude-Code-blueviolet)](https://docs.anthropic.com/en/docs/claude-code)

A curated directory of Claude Code skills and MCP servers for applied scientists, organized by subfield. Every entry lists who built it, a copy-pasteable install command, and the specific tools inside. Entries are rank-ordered by utility. Gaps noted where no dedicated tooling exists.

> **~70 sources** across 15 subfields -- last updated April 2026

<details>
<summary><strong>What's New (Apr 2026)</strong></summary>
<br>

Initial release covering 15 subfields:

- **Applied Science** -- Experimentation, causal inference, Bayesian modeling, time series, classical ML, deep learning, NLP, recommender systems, survival analysis, optimization, geospatial, MLOps
- **Infrastructure** -- Econometrics & academic research, data infrastructure (databases, BI, notebooks)
- **Meta** -- Source repositories, skill marketplaces, learning resources

</details>

## Quick Links

| Subfield | Top Skills | Top MCP Servers | Maturity |
|----------|-----------|----------------|----------|
| [**Experimentation**](#experimentation--ab-testing) | A/B Test Setup | GrowthBook, Optimizely, PostHog | Strong |
| [**Causal Inference**](#causal-inference) | awesome-econ-ai-stuff (LSE) | DoWhy MCP v2 (42 tools), causalMCP | Emerging |
| [**Bayesian**](#bayesian-modeling) | PyMC Labs, Stan skill | bayes-msp | Emerging |
| [**Time Series**](#time-series--forecasting) | K-Dense TimesFM, aeon | Nixtla, Chronulus | Fragmented |
| [**Classical ML**](#classical-ml) | K-Dense scikit-learn | Optuna (official), sklearn MCP | Adequate |
| [**Deep Learning**](#deep-learning--model-hubs) | HF skills (official) | HF MCP, W&B, MLflow | Adequate |
| [**NLP**](#nlp--text-analytics) | Orchestra RAG skills | HuggingFace MCP, Jama NLP | Thin |
| [**Recommender Systems**](#recommender-systems) | None | None | Complete gap |
| [**Survival Analysis**](#survival-analysis) | tidyrmodelling (R) | None dedicated | Skill-only |
| [**Optimization**](#optimization--or) | pymoo skill | mcp-solver (150 stars), USolver, IBM CP-SAT | Strong |
| [**Geospatial**](#geospatial) | K-Dense GeoMaster | QGIS (540 stars), PostGIS Yukon, H3/bbox | Strong |
| [**MLOps**](#mlops--experiment-tracking) | Orchestra (W&B, MLflow, TB) | W&B, MLflow, Dagster, Prefect, Feast | Excellent |
| [**Econometrics & Academic**](#econometrics-economic-data--academic-research) | Mele (LSE), Sant'Anna, Blattman | MCP-Stata, RMCP (198 stars), FRED, arXiv | Strong |
| [**Data Infrastructure**](#data-infrastructure) | Anthropic Data Plugin, DuckDB | Snowflake, BigQuery, dbt, Jupyter, Looker | Excellent |
| [**Repos & Discovery**](#source-repositories--discovery) | K-Dense (7.8K stars), Orchestra (6.1K stars) | PulseMCP, Smithery, MCP Registry | — |

---

## Experimentation & A/B Testing

MCP servers from experimentation platforms plus skills for test design.

| Source | By | Install | What's Inside |
|--------|-----|---------|--------------|
| [**GrowthBook MCP**](https://github.com/growthbook/growthbook-mcp) | GrowthBook (official, 7K stars) | `claude mcp add growthbook -- npx -y @growthbook/mcp@latest` | 14 tools: feature gates, A/B tests, experiment management, results. Platform has CUPED, sequential testing, Bayesian stats, bandits, SRM checks |
| [**PostHog MCP**](https://posthog.com/docs/product-analytics/build-insights-mcp) | PostHog (official) | `claude mcp add posthog -- uv run posthog_mcp` | Experiments, funnels, retention, feature flags via HogQL |
| [**Optimizely MCP**](https://www.optimizely.com/insights/blog/experimentation-mcp-server/) | Optimizely (official, closed beta) | Closed beta — request access | Web + Feature Experimentation: create/configure flags, diagnose evaluation, SDK integration |
| [**A/B Test KB MCP**](https://glama.ai/mcp/servers/klickstark/ab-test-kb-mcp) | Eddie Klickstark (CRO, klickstark.agency) | `claude mcp add abtestkb -- uvx ab-test-kb-mcp` | 1,600+ real A/B test results with uplift data, psychological principles, taxonomy |
| [**causalMCP**](https://glama.ai/mcp/servers/mohitkr/causalMCP) | mohitkr | `claude mcp add causal -- pip install causalmcp` | CausalPFN + EconML: ATE, CATE, uplift ranking, S/T/X-Learner, DML. Observational causal inference for experiment analysis |
| [**marketingskills**](https://github.com/mysticaltech/marketingskills) | mysticaltech (59 stars) | `git clone https://github.com/mysticaltech/marketingskills .claude/skills/marketing` | `/ab-test-setup` hypothesis generation, sample size calculation, metric selection |
| [**K-Dense scientific-skills**](https://github.com/K-Dense-AI/claude-scientific-skills) | K-Dense AI (7,800 stars) | `npx skills add K-Dense-AI/claude-scientific-skills` | `/statistical-analysis` power analysis, hypothesis testing, assumption checks, experimental design |

**Gap:** No standalone sequential testing, CUPED/variance reduction, switchback design, or interference correction skill. OraClaw (see Optimization) includes bandit algorithms (UCB1, Thompson Sampling, LinUCB).

---

## Causal Inference

DiD, IV, RDD, matching, and identification strategies.

| Source | By | Install | What's Inside |
|--------|-----|---------|--------------|
| [**DoWhy MCP v2.0**](https://github.com/lesong36/dowhy_mcp) | lesong36 | `pip install -e . && claude mcp add dowhy -- python -m dowhy_mcp` | 42 tools across 7 modules: SCM/GCM construction, estimation, attribution, root cause analysis, counterfactuals, sensitivity analysis, structure learning |
| [**causalMCP**](https://glama.ai/mcp/servers/mohitkr/causalMCP) | mohitkr | `claude mcp add causal -- pip install causalmcp` | CausalPFN + EconML: ATE, CATE, uplift ranking, meta-learners (S/T/X-Learner, DML) |
| [**awesome-econ-ai-stuff**](https://github.com/meleantonio/awesome-econ-ai-stuff) | Antonio Mele (LSE, 205 stars) | `git clone https://github.com/meleantonio/awesome-econ-ai-stuff .claude/skills/econ` | `/r-econometrics` DiD, IV, RDD with fixest, event-study plots, McCrary tests · `/python-panel-data` linearmodels, fixed effects · `/stata-regression` reghdfe, esttab · `/research-ideation` identification strategies |
| [**Stata Skill**](https://github.com/dylantmoore/stata-skill) | Dylan Moore | `git clone https://github.com/dylantmoore/stata-skill .claude/skills/stata` | Comprehensive Stata: econometrics, causal inference, 20+ community packages, Python/R-to-Stata C plugin translation, 37+ reference files |
| [**claude-skills**](https://github.com/zirui-song/claude-skills) | Zirui Song (empirical econ/finance) | `git clone https://github.com/zirui-song/claude-skills .claude/skills/econ-empirical` | `/robustness` sensitivity analysis, placebo tests, DiD diagnostics, specification curves |

**Gap:** No MCP for CausalML (Uber), DoubleML, or synthetic control. Accessible through Jupyter MCP.

---

## Bayesian Modeling

PyMC and Stan skills. The PyMC Labs skill includes auto-suggest hooks; the Stan skill is the only non-PyMC probabilistic programming resource.

| Source | By | Install | What's Inside |
|--------|-----|---------|--------------|
| [**python-analytics-skills**](https://github.com/pymc-labs/python-analytics-skills) | PyMC Labs (PyMC maintainers, 16 stars) | `git clone https://github.com/pymc-labs/python-analytics-skills && cd python-analytics-skills && ./install.sh claude` | `/pymc-modeling` PyMC v5+, MCMC (nutpie, NumPyro), ArviZ, hierarchical models, GLMs, GPs, BART, time series · `/pymc-testing` pytest for PyMC · `/marimo-notebook` reactive notebooks. Auto-suggest on "bayesian," "posterior," "hierarchical model" |
| [**stan-development**](https://github.com/seabbs/claude-code-config/tree/main/skills/stan-development) | Sam Abbott (epidemiologist, Stan contributor, 6 stars) | `npx playbooks add skill seabbs/claude-code-config --skill stan-development` | Stan 2.26+: cmdstanr/cmdstanpy, compilation, MCMC, variational inference, Pathfinder, Laplace, modular `#include`, divergence debugging, non-centered parameterizations, R-hat/ESS diagnostics |
| [**bayes-msp**](https://github.com/wrenchchatrepo/bayes-msp) | wrenchchatrepo | `git clone https://github.com/wrenchchatrepo/bayes-msp && claude mcp add bayes -- python bayesian_mcp.py` | Bayesian inference MCP on PyMC: MCMC sampling, model comparison (information criteria), predictive inference, posterior visualization |
| [**K-Dense scientific-skills**](https://github.com/K-Dense-AI/claude-scientific-skills) | K-Dense AI (7,800 stars) | `npx skills add K-Dense-AI/claude-scientific-skills` | `/pymc` NUTS, Metropolis-Hastings, ADVI, GPs, time series, ArviZ integration |

**Gap:** No skill or MCP for NumPyro, Pyro, TensorFlow Probability, brms, BUGS/JAGS, or Bayesian nonparametrics.

---

## Time Series & Forecasting

Forecasting tools and time series classification.

| Source | By | Install | What's Inside |
|--------|-----|---------|--------------|
| [**Nixtla plugins**](https://github.com/intent-solutions-io/plugins-nixtla) | intent-solutions-io | `pip install -e packages/nixtla-claude-skills-installer && nixtla-skills init` | 3 plugins + 8 skills: statsforecast + TimeGPT, M4 benchmarking, BigQuery integration, ERCOT energy prototype. Experimental v1.7.0 |
| [**MCP Analytics**](https://mcpanalytics.ai) | mcpanalytics.ai (commercial) | `claude mcp add analytics -- npx -y mcp-remote@latest https://api.mcpanalytics.ai/auth0` | 60+ R modules: ARIMA, Prophet, ETS, STL decomposition, demand forecasting, Cox PH. Free tier (2K credits) |
| **Chronulus AI MCP** | Chronulus AI | `claude mcp add chronulus -- uvx chronulus-mcp` | API-based time series forecasting |
| [**K-Dense scientific-skills**](https://github.com/K-Dense-AI/claude-scientific-skills) | K-Dense AI (7,800 stars) | `npx skills add K-Dense-AI/claude-scientific-skills` | `/timesfm` Google TimesFM foundation model, zero-shot forecasting with prediction intervals · `/aeon` 40+ distance metrics (DTW), ROCKET/MiniRocket classifiers, DL architectures |

**Gap:** No MCP for NeuralProphet, Temporal Fusion Transformers, or changepoint detection.

---

## Classical ML

Scikit-learn skills, hyperparameter optimization, and an sklearn MCP server.

| Source | By | Install | What's Inside |
|--------|-----|---------|--------------|
| [**K-Dense scientific-skills**](https://github.com/K-Dense-AI/claude-scientific-skills) | K-Dense AI (7,800 stars) | `npx skills add K-Dense-AI/claude-scientific-skills` | `/scikit-learn` classification, regression, clustering, feature importance, cross-validation · `/model-interpretability` SHAP, partial dependence, explainability |
| [**Optuna MCP**](https://github.com/optuna/optuna/releases) | Optuna (official) | `claude mcp add optuna -- uvx optuna-mcp` | Bayesian optimization, multi-objective optimization, optimization history visualization |
| [**mcp-server-scikit-learn**](https://github.com/shibuiwilliam/mcp-server-scikit-learn) | shibuiwilliam | See repo | Standardized sklearn execution: training, evaluation, preprocessing, cross-validation via MCP |
| [**Kaggle MCP**](https://github.com/54yyyu/kaggle-mcp) | 54yyyu | `claude mcp add kaggle -- npx -y @kaggle/mcp` | Competitions, datasets, notebooks, user management |

---

## Deep Learning & Model Hubs

Model training, evaluation, and deployment.

| Source | By | Install | What's Inside |
|--------|-----|---------|--------------|
| [**Hugging Face**](https://github.com/huggingface/skills) | HF team (official) | Skills: `git clone https://github.com/huggingface/skills .claude/skills/hf` / MCP: `claude mcp add hf -- npx -y @huggingface/mcp` | 6 skills: `/evaluation` vLLM/lighteval · `/training` fine-tuning · `/datasets` configs + SQL · `/cli` Hub management · `/jobs` compute · `/spaces` app deployment. MCP: 900K+ models, 200K+ datasets, Gradio tools |
| [**AI-Research-SKILLs**](https://github.com/Orchestra-Research/AI-Research-SKILLs) | Orchestra Research (6,100 stars) | `npx @orchestra-research/ai-research-skills` | 5 RAG skills (Chroma, FAISS, Pinecone, Qdrant, Sentence Transformers) · 3 MLOps skills (W&B 427 lines, MLflow 514 lines, TensorBoard 538 lines) · distributed training · model architecture |
| [**K-Dense scientific-skills**](https://github.com/K-Dense-AI/claude-scientific-skills) | K-Dense AI (7,800 stars) | `npx skills add K-Dense-AI/claude-scientific-skills` | `/pytorch-lightning` training, model building, validation · `/torch-geometric` GNNs, node classification, link prediction |
| [**Dataset Viewer MCP**](https://github.com/privetin/dataset-viewer) | privetin | `claude mcp add dataview -- npx -y dataset-viewer-mcp` | Browse HF datasets without download: filtering, statistics, data export |

---

## NLP & Text Analytics

See also: Hugging Face MCP and Orchestra RAG skills in [Deep Learning](#deep-learning--model-hubs).

| Source | By | Install | What's Inside |
|--------|-----|---------|--------------|
| [**Jama Python MCP**](https://glama.ai/mcp/servers/sanjeevkoppal1/jama-python-mcp) | sanjeevkoppal1 | `pip install -e . && python -m spacy download en_core_web_sm` | 10 NLP tools: NER, text classification, keyword extraction, semantic analysis, semantic search via spaCy + sentence-transformers + ChromaDB |
| [**Survey Insight MCP**](https://glama.ai/mcp/servers/sinjorjob/survey-insight-mcp) | sinjorjob (4 stars) | See Glama listing | Survey text analysis: spaCy morphological analysis, keyword rankings, word clouds |

**Gap:** No dedicated MCP for BERTopic, Gensim, NLTK, stanza, flair, SciBERT, or any R text mining tool (quanteda, tidytext, stm). Note: spaCy's creator (Matthew Honnibal) has a [claude-skills repo](https://github.com/honnibal/claude-skills) but it contains no NLP-specific content.

---

## Recommender Systems

**Complete gap.** No skill or MCP wraps LightFM (5K+ stars), Implicit, Surprise, RecBole (4.1K+ stars), LensKit, cornac, or any learning-to-rank framework. A [CLIP-based fashion recommender](https://github.com/attarmau/FastMCP_RecSys) (attarmau) exists but is narrow and domain-specific.

---

## Survival Analysis

One comprehensive R skill now covers this subfield.

| Source | By | Install | What's Inside |
|--------|-----|---------|--------------|
| [**tidyrmodelling**](https://github.com/choxos/tidyrmodelling) | Ahmad Sofi-Mahmudi (biostatistician) | `npx skillfish add choxos/tidyrmodelling survival-analysis` | `/survival-analysis` Kaplan-Meier with survminer, Cox PH with automated diagnostics, parametric models (Weibull, Gamma, Royston-Parmar via flexsurv/rstpm2), competing risks (Fine-Gray), multi-state models, RMST, tidymodels censored package · `/clinical-trials` survival endpoints, sample size, group sequential designs |

**Gap:** No MCP or skill for lifelines (Python), pycox, DeepSurv, XGBSurvival, frailty models, or cure models. MCP Analytics includes Cox PH among 60+ generic R modules.

---

## Optimization & OR

The most dramatically expanded subfield — 12 tools including a 150-star academic solver.

| Source | By | Install | What's Inside |
|--------|-----|---------|--------------|
| [**mcp-solver**](https://github.com/szeider/mcp-solver) | Stefan Szeider (TU Wien, ~150 stars) | `git clone https://github.com/szeider/mcp-solver && uv pip install -e ".[all]"` | MiniZinc, PySAT, MaxSAT, Z3, Clingo (ASP). 5 operational modes for constraint solving, SAT, answer set programming. Academic paper at SAT 2025. Only solver with MiniZinc + ASP support |
| [**USolver**](https://github.com/sdiehl/usolver) | Stephen Diehl (~60 stars) | `pip install usolver` | Chains Z3, CVXPY, HiGHS, OR-Tools — results from one feed into another. Job shop scheduling, portfolio optimization (Markowitz), nurse scheduling, logistics, knapsack, network flow. Fills the CVXPY gap |
| [**chuk-mcp-solver**](https://github.com/IBM/chuk-mcp-solver) | IBM | `claude mcp add chuksolver -- python -m chuk_mcp_solver.server` | Google OR-Tools CP-SAT: scheduling (cumulative, no_overlap), resource allocation, routing, inventory (reservoir constraints), knapsack |
| [**highs-mcp**](https://github.com/wspringer/highs-mcp) | Wilfred Springer | `claude mcp add highs -- npx highs-mcp` | HiGHS solver (CVXPY's default MILP backend): LP, MIP, convex QP. Lightweight Node.js server |
| [**mcp-optimizer**](https://github.com/dmitryanchikov/mcp-optimizer) | Dmitry Anchikov | `claude mcp add optimizer -- uvx mcp-optimizer` | PuLP (LP/IP with CBC, GLPK, Gurobi, CPLEX) + Google OR-Tools (assignment, knapsack, routing, scheduling). Docker/K8s, Prometheus monitoring |
| [**optimization-mcp**](https://github.com/eesb99/optimization-mcp) | eesb99 | See Glama listing | PuLP, SciPy, CVXPY, NetworkX with Monte Carlo simulation. Pareto frontier multi-objective optimization, stochastic programming |
| [**MCP-Constrained-Optimization**](https://github.com/Sharmarajnish/MCP-Constrained-Optimization) | Rajnish Sharma | `pip install constrained-opt-mcp` | Z3, CVXPY, HiGHS, OR-Tools with portfolio focus: Markowitz, Black-Litterman, risk parity, ESG-constrained |
| [**GurobiMCP**](https://mcpservers.org/servers/KKonuru/GurobiMCP) | KKonuru | See Glama listing | Direct on-device Gurobi solver: LP, MILP, QP, MIQCP |
| [**OraClaw**](https://github.com/Whatsonyourmind/oraclaw) | Whatsonyourmind | `claude mcp add oraclaw -- npx @oraclaw/mcp-server` | 19 algorithms: CMA-ES, genetic algorithms, LP/MIP, Monte Carlo, A* pathfinding, bandit algorithms (UCB1, Thompson Sampling, LinUCB). New (Mar 2026) |
| [**pymoo skill**](https://smithery.ai/skills/davila7/pymoo) | davila7 | `smithery skill add davila7/pymoo` | Multi-objective optimization: NSGA-II, NSGA-III, MOEA/D, Pareto fronts, constraint handling. Only dedicated optimization SKILL.md |

**Gap:** No MCP for Pyomo (standalone), DEAP, Ax, BoTorch, SimPy, or R optimization packages (lpSolve, ROI).

---

## Geospatial

GIS, spatial analysis, and remote sensing.

| Source | By | Install | What's Inside |
|--------|-----|---------|--------------|
| [**QGIS MCP**](https://github.com/jjsantos01/qgis_mcp) | Juan Jose Santos (540 stars) | `claude mcp add qgis -- uv run qgis_mcp_server.py` | Two-way QGIS Desktop: project management, layer manipulation, processing toolbox, PyQGIS code, map rendering |
| **QGISToolMCP** | Community | Search "QGISToolMCP" | 333 geospatial processing tools across 14 specialized MCP services |
| **PostGIS Yukon MCP** | zmgiser | Search "postgis-yukon-mcp" | 32 spatial tools: DBSCAN clustering, k-NN, Voronoi, convex hulls, NL-to-SQL for PostGIS, spatial joins |
| [**bbox MCP**](https://github.com/iamvibhorsingh/bbox-mcp-server) | iamvibhorsingh | `claude mcp add bbox -- npx -y bbox-mcp-server` | Bounding box conversion (6 formats), Uber H3 hexagonal cells, Overpass queries binned into H3 |
| [**K-Dense scientific-skills**](https://github.com/K-Dense-AI/claude-scientific-skills) | K-Dense AI (7,800 stars) | `npx skills add K-Dense-AI/claude-scientific-skills` | `/geomaster` satellite imagery (Sentinel, Landsat, MODIS, SAR), spatial stats, point clouds, STAC/COG workflows, 500+ examples |

**Gap:** No spatial econometrics MCP. No ArcGIS Online MCP.

---

## MLOps & Experiment Tracking

Experiment tracking, pipeline orchestration, and feature stores.

| Source | By | Install | What's Inside |
|--------|-----|---------|--------------|
| [**W&B MCP**](https://github.com/wandb/wandb-mcp-server) | Weights & Biases (official) | `claude mcp add wandb --transport http https://mcp.withwandb.com/mcp` | Runs, sweeps, Weave traces, evaluations, report generation. Also local: `uvx wandb-mcp-server` |
| [**MLflow MCP**](https://mlflow.org/docs/latest/genai/mcp/) | MLflow (official, built into 3.4+) | `claude mcp add mlflow -- uv run --with "mlflow[mcp]>=3.5.1" mlflow mcp run` | Trace management, experiment tracking, model registry, feedback logging |
| [**Dagster MCP**](https://github.com/kyryl-opens-ml/mcp-server-dagster) | kyryl-opens-ml | `claude mcp add dagster -- pip install mcp-server-dagster` | Explore pipelines, monitor runs, manage assets, list jobs, materialize assets |
| [**Prefect MCP**](https://github.com/PrefectHQ/prefect-mcp-server) | Prefect (official) | `claude mcp add prefect -- uvx --from prefect-mcp prefect-mcp-server` | Read-only: deployments, flow runs, infrastructure |
| [**Feast MCP**](https://docs.feast.dev) | Feast (official, built into v0.56+) | Configure `feature_server: type: mcp` in feature_store.yaml | Feature store: `/get-online-features` for real-time feature retrieval |
| [**Airflow MCP**](https://github.com/hipposys-ltd/airflow-mcp) | hipposys-ltd | `claude mcp add airflow -- docker run hipposys/airflow-mcp` | DAG management, tasks, connections, variables via Airflow APIs |
| [**AI-Research-SKILLs**](https://github.com/Orchestra-Research/AI-Research-SKILLs) | Orchestra Research (6,100 stars) | `npx @orchestra-research/ai-research-skills` | `/wandb` (427 lines + 3 refs) · `/mlflow` (514 lines + 3 refs) · `/tensorboard` (538 lines + 3 refs) |

**Gap:** No MCP for Tecton, Evidently AI (drift detection), or WhyLabs. Model monitoring is unserved.

---

## Econometrics, Economic Data & Academic Research

Skills and MCP servers for econometrics, academic writing, literature, and economic data.

| Source | By | Install | What's Inside |
|--------|-----|---------|--------------|
| [**awesome-econ-ai-stuff**](https://github.com/meleantonio/awesome-econ-ai-stuff) | Antonio Mele (LSE, 205 stars) | `git clone https://github.com/meleantonio/awesome-econ-ai-stuff .claude/skills/econ` | `/academic-paper-writer` journal conventions · `/lit-review-assistant` citation management, gap identification · `/latex-econ-model` theorems, proofs · `/econ-visualization` ggplot2 pub-quality charts · `/api-data-fetcher` FRED, World Bank · `/beamer` presentations with coefficient plots |
| [**scientific-writer**](https://github.com/K-Dense-AI/claude-scientific-writer) | K-Dense AI | `npx skills add K-Dense-AI/claude-scientific-writer` | 19 writing skills: Nature/Science/NeurIPS style · grant templates (NSF, NIH, DOE, DARPA) · scientific schematics (CONSORT, neural net viz) · peer review · hypothesis generation |
| [**claude-skills**](https://github.com/zirui-song/claude-skills) | Zirui Song (empirical econ/finance) | `git clone https://github.com/zirui-song/claude-skills .claude/skills/econ-empirical` | `/robustness` DiD diagnostics · `/lit-review` paper summarization · `/coding-standards` Python/Stata · `/data-codebook` dataset docs · `/project-structure` reproducible dirs · `/referee-response` R&R formatting |
| [**Sant'Anna Workflow**](https://psantanna.com/claude-code-my-workflow) | Pedro Sant'Anna (Emory) | See website | 10 agents, 22 skills, 18 rules. Replication-first (Stata-to-R, tolerance <0.01), `/slide-excellence` with 6 parallel agents. Used by 15+ research groups |
| [**clo-author**](https://github.com/hugosantanna/clo-author) | Hugo Sant'Anna | `git clone https://github.com/hugosantanna/clo-author .claude/skills/clo-author` | 17 agents in 6 worker-critic pairs (Librarian, Explorer, Strategist, Coder, Writer, Storyteller). AEA replication compliance. Full lifecycle |
| [**claudeblattman**](https://github.com/chrisblattman/claudeblattman) | Chris Blattman (U Chicago) | `git clone https://github.com/chrisblattman/claudeblattman .claude/skills/blattman` | Executive assistant, proposal writing with donor profiles, "Referee 2" audit protocol, PDF reading |
| [**MCP-Stata**](https://github.com/tmonk/mcp-stata) | Thomas Monk (LSE) | `claude mcp add stata -- python -m mcp_stata` | Connect Claude to Stata for do-files and output retrieval |
| [**RMCP**](https://github.com/finite-sample/rmcp) | finite-sample (198 stars) | `pip install rmcp && rmcp start` | 52 tools across 429 R packages: 55 econometrics, 48 time series, 32 Bayesian. Cross-cutting: covers survival (flexsurv), experimentation (gsDesign), NLP (quanteda), optimization (lpSolve) |
| [**FRED MCP**](https://github.com/stefanoamorelli/fred-mcp-server) | Stefano Amorelli | See repo | 800,000+ Federal Reserve Economic Data time series |
| [**US Gov Open Data MCP**](https://github.com/lzinga/us-gov-open-data-mcp) | lzinga | See repo | 300+ tools across 40+ APIs: Treasury, BLS, BEA, EIA, Census, SEC, World Bank |
| [**Census MCP**](https://github.com/brockwebb/census-mcp-server) | Brock Webb | See repo | Natural language queries mapped to 145+ demographic variables |
| [**arXiv MCP**](https://github.com/blazickjp/arxiv-mcp-server) | blazickjp | See repo | Search, download, deep-read papers with analysis prompts |
| [**arxiv-latex MCP**](https://github.com/takashiishida/arxiv-latex-mcp) | Takashi Ishida | See repo | Fetch LaTeX source instead of PDFs |
| [**Semantic Scholar MCP**](https://github.com/FujishigeTemma/semantic-scholar-mcp) | FujishigeTemma | See repo | 200M+ papers with citation graphs and export |
| [**LaTeX MCP**](https://github.com/Yeok-c/latex-mcp-server) | Yeok-c | See repo | Read cited papers, generate figures, compile LaTeX to PDF |

---

## Data Infrastructure

Best-of-breed only. One entry per platform.

| Source | By | Install | What's Inside |
|--------|-----|---------|--------------|
| [**Anthropic Data Plugin**](https://github.com/anthropics/knowledge-work-plugins/tree/main/data) | Anthropic (official) | `claude plugin add data` | `/write-query` optimized SQL · `/explore-data` profiling · `/build-dashboard` · `/validate` methodology review. Snowflake, Databricks, BigQuery |
| [**DuckDB Skills**](https://github.com/duckdb/duckdb-skills) | DuckDB (official) | `claude plugin add duckdb` | attach-db, query, read-file (CSV/JSON/Parquet/Avro/Excel/spatial), search docs |
| [**Snowflake MCP**](https://github.com/Snowflake-Labs/mcp) | Snowflake Labs (official) | See repo | Cortex AI (Search, Analyst, Agent), SQL orchestration, semantic views |
| [**BigQuery MCP**](https://github.com/LucasHild/mcp-server-bigquery) | LucasHild | `claude mcp add bigquery -- uvx mcp-server-bigquery` | Schema inspection, query execution |
| [**DuckDB/MotherDuck MCP**](https://github.com/motherduckdb/mcp-server-motherduck) | MotherDuck (official) | `claude mcp add duckdb -- uvx mcp-server-motherduck` | Local DuckDB, in-memory, S3, MotherDuck cloud. Read-only default |
| [**Databricks MCP**](https://github.com/databrickslabs/mcp) | Databricks Labs (official) | See repo | Unity Catalog, vector search, Genie spaces, Databricks SQL |
| [**PostgreSQL MCP**](https://github.com/modelcontextprotocol/servers) | MCP team (official) | See repo | Read-only database access with schema inspection |
| [**dbt MCP**](https://github.com/dbt-labs/dbt-mcp) | dbt Labs (official) | See repo | CLI execution (run, build, test), metadata, Semantic Layer, text-to-SQL, lineage |
| [**Jupyter MCP**](https://github.com/datalayer/jupyter-mcp-server) | Datalayer | `claude mcp add jupyter -- pip install jupyter-mcp-server` | Cell CRUD, kernel execution, multimodal output, OpenTelemetry. 12+ tools |
| [**Looker MCP**](https://docs.cloud.google.com/looker/docs/connect-ide-to-looker-using-mcp-toolbox) | Google (official) | See docs | Query semantic layer (no SQL needed), create dashboards |
| [**Tableau MCP**](https://github.com/tableau/tableau-mcp) | Tableau (official) | See repo | OAuth 2.1 data visualization and analytics |
| [**Apache Superset MCP**](https://superset.apache.org/user-docs/using-superset/using-ai-with-superset/) | Superset (built into 5.0+) | See docs | 128+ tools: datasets, charts, dashboards, SQL with RBAC |
| [**Grafana MCP**](https://github.com/grafana/mcp-grafana) | Grafana (official) | `claude mcp add grafana -- uvx mcp-grafana` | Dashboards, PromQL, LogQL, alerting, incidents, on-call |

---

## Source Repositories & Discovery

| Source | By | Install | What's Inside |
|--------|-----|---------|--------------|
| [**K-Dense-AI/claude-scientific-skills**](https://github.com/K-Dense-AI/claude-scientific-skills) | K-Dense AI (7,800 stars) | `npx skills add K-Dense-AI/claude-scientific-skills` | 170 scientific skills: stats, ML, DL, Bayesian, time series, optimization, geospatial, 78+ databases |
| [**Orchestra-Research/AI-Research-SKILLs**](https://github.com/Orchestra-Research/AI-Research-SKILLs) | Orchestra Research (6,100 stars) | `npx @orchestra-research/ai-research-skills` | 87 skills: RAG (5 impls), MLOps (W&B, MLflow, TB), distributed training, model architecture |
| [**awesome-econ-ai-stuff**](https://github.com/meleantonio/awesome-econ-ai-stuff) | Antonio Mele, LSE (205 stars) | `git clone https://github.com/meleantonio/awesome-econ-ai-stuff .claude/skills/econ` | 18+ economics/causal inference skills in R, Python, Stata, Julia |
| [**python-analytics-skills**](https://github.com/pymc-labs/python-analytics-skills) | PyMC Labs (16 stars) | `./install.sh claude` | Bayesian modeling: 3 skills + 12 reference docs |
| [**RMCP**](https://github.com/finite-sample/rmcp) | finite-sample (198 stars) | `pip install rmcp && rmcp start` | 52 tools, 429 R packages. Cross-cutting: econometrics, survival, time series, Bayesian, NLP, optimization |
| [**anthropics/skills**](https://github.com/anthropics/skills) | Anthropic (official, 102K stars) | `claude plugin add skills` | xlsx, skill-creator, document handling, web artifacts |
| [**anthropics/knowledge-work-plugins**](https://github.com/anthropics/knowledge-work-plugins) | Anthropic (official, 11K stars) | `claude plugin add data` | Data analytics, finance, productivity plugins |
| [**modelcontextprotocol/servers**](https://github.com/modelcontextprotocol/servers) | MCP team (official) | N/A | Authoritative MCP server repository |
| [**PulseMCP**](https://www.pulsemcp.com/servers) | PulseMCP | [pulsemcp.com](https://www.pulsemcp.com/servers) | 11,150+ MCP servers, largest directory |
| [**Smithery.ai**](https://smithery.ai) | Smithery | [smithery.ai](https://smithery.ai) | 7,300+ MCP servers with CLI install |
| [**SkillsMP**](https://skillsmp.com) | SkillsMP | [skillsmp.com](https://skillsmp.com) | 96,000+ skills indexed from GitHub |
| [**SkillHub**](https://www.skillhub.club) | SkillHub | [skillhub.club](https://www.skillhub.club) | 7,000+ AI-evaluated skills with playground |
| [**MCP Registry**](https://registry.modelcontextprotocol.io) | MCP community | [registry.modelcontextprotocol.io](https://registry.modelcontextprotocol.io) | Canonical catalog, 10,000+ servers |

---

## Learning Resources

| Source | By | Link |
|--------|-----|------|
| [**Claude Code for Applied Economists**](https://www.youtube.com/results?search_query=paul+goldsmith-pinkham+claude+code) | Paul Goldsmith-Pinkham (Princeton) | 7-episode video series |
| [**"Claude Code Changed How I Work"**](https://substack.com/@causalinf) | Scott Cunningham (Baylor) | Substack series on skills, MCP servers, causal inference |
| [**Getting Started with Claude Code for DS**](https://dataquest.io/blog/getting-started-with-claude-code-for-data-scientists/) | Dataquest | Plan mode, CLAUDE.md, Jupyter integration |
| [**Skills Documentation**](https://docs.anthropic.com/en/docs/claude-code/skills) | Anthropic (official) | SKILL.md format, scopes, auto-invocation |
| [**Agent Skills Open Standard**](https://agentskills.io) | agentskills.io | SKILL.md spec, 26+ platforms, Apache 2.0 |

---

## Contributing

Pull requests welcome. To add a tool, include who built it, a one-liner install, and what's inside.

## Author

[Pranjal Rawat](https://github.com/rawatpranjal)
