# HopTrace

**Bitcoin UTXO transaction risk scoring engine powered by Graph Neural Networks and Explainable AI.**

| Resource | Link |
|---|---|
| **Live Demo** | [`hoptrace.zainiqbal.tech`](https://hoptrace.zainiqbal.tech) |
| **Frontend Repository** | [`hop-trace-frontend`](https://github.com/muhammadzainiqbal/hop-trace-frontend) |
| **Backend Repository** | [`hop-trace-backend`](https://github.com/muhammadzainiqbal/hop-trace-backend) |

---

## Overview

HopTrace fetches live Bitcoin mainnet UTXO graph topologies via the [mempool.space](https://mempool.space) API, evaluates structural transaction risk using a PyTorch GraphSAGE model, and surfaces key prediction drivers through SHAP feature attributions. Results are rendered on an interactive React Flow dashboard where users can inspect multi-hop transaction lineages and per-node risk breakdowns in real time.

---

## System Architecture

```
[ Next.js Client ]  <--->  [ FastAPI Backend ]  <--->  [ mempool.space API ]
 (React Flow UI)           (PyTorch GraphSAGE + SHAP)   (Bitcoin Mainnet Data)
```

| Layer | Stack | Deployment |
|---|---|---|
| **Frontend** ([`hop-trace-frontend`](https://github.com/muhammadzainiqbal/hop-trace-frontend)) | Next.js 14, TypeScript, React Flow, Tailwind CSS | Vercel → `hoptrace.zainiqbal.tech` |
| **Backend** ([`hop-trace-backend`](https://github.com/muhammadzainiqbal/hop-trace-backend)) | FastAPI, PyTorch Geometric (GraphSAGE), SHAP, LightGBM, Uvicorn | Render |

---

## Repository Index & Setup

This repository is a directory-level entry point. All source code, environment configuration, and local setup instructions live in the individual sub-repositories:

- **[`hop-trace-backend`](https://github.com/muhammadzainiqbal/hop-trace-backend)** — Model weights, FastAPI endpoints, SHAP explainer pipeline, and data ingestion logic.
- **[`hop-trace-frontend`](https://github.com/muhammadzainiqbal/hop-trace-frontend)** — Graph rendering components, client-side UTXO visualization, and Vercel deployment configuration.

Clone and refer to each repository's own README for environment variables, dependency installation, and execution details.
