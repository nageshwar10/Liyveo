#  Liyveo — AI CloudOps, FinOps & SecOps Platform
### “ Your Personal AI for Everything You Deploy, Secure, and Optimize.”

**Liyveo** is an AI-powered Cloud Intelligence Assistant designed to simplify, visualize, and optimize your entire AWS infrastructure.
It helps you **see, understand, and act** on your cloud environment through an interactive dashboard — or simply by **talking to your AI copilot**.

Think of it as the **AI layer that transforms cloud management into a conversation** — giving DevOps, FinOps, and Security teams one intelligent pane of glass for their entire cloud.

##  What Liyveo Does

Liyveo combines **real-time cloud analytics, security insights**, and **cost optimization** with **AI-powered conversational intelligence** — so you can ask questions, see your infrastructure visually, and receive automated recommendations.

| Feature                                   | Description                                                                    | Example                                                  |
| ----------------------------------------- | --------------------------------------------------------------------------     | -------------------------------------------------------- |
|     **AWS Resource Visualizer**           | See all running instances, EKS clusters, and workloads across regions.         | Show me all active EC2s and pods running in production.  |
|    **Cost Explorer Dashboard**            | Real-time AWS cost and usage breakdown by service, tag, and project.           | What was my EKS spend last week?                         |
|    **IAM Analyzer**                       | Detects over-permissive IAM roles and risky privilege assignments.             | List all admin roles without MFA.                        |
|    **Security Advisor**                   | Centralized security recommendations for WAF, Trivy, SonarQube, and BlackDuck. | Check if WAF is enabled for staging.                     |
|    **EKS Inspector**                      | Visualizes EKS clusters, nodes, deployments, and pods with health status.      | Show my Kubernetes cluster utilization.                  |
|    **AI + Voice Assistant**               | Conversational bot that understands and speaks your cloud.                     | Hey Liyveo, optimize my AWS cost and check IAM risks.    |
|    **Automated Reports**                  | Scheduled reports for billing, compliance, and resource drift.                 | Daily cost summary or weekly IAM risk scan.              |

---

##  How Liyveo Works

Liyveo unifies data from AWS APIs, Kubernetes, and Security tools, processes them via AI agents, and delivers both visual dashboards and natural language responses.

```text

[AWS Account(s)]
        │
        ▼
 [Liyveo Data Collector]
     - Fetches Cost Explorer, IAM, EKS, and Security data
     - Normalizes and stores in Postgres
        │
        ▼
 [Liyveo AI Core]
     ├── Conversational Agent (GPT-5)
     ├── Voice Interface (Whisper + TTS)
     ├── Optimization Engine (FinOps)
     ├── Security Advisor (SecOps)
        │
        ▼
 [Web Dashboard + Voice Console]
     - Real-time visualizations
     - AI chat assistant
     - Multi-account insights


```
##  AI Service Architecture

### Liyveo Data & Intelligence Pipeline

The **Liyveo Core Engine** continuously ingests, analyzes, and optimizes your AWS environment using AI reasoning and contextual cloud knowledge.

```text
[AWS APIs / Client Credentials]
        │
        ▼
 [Liyveo Ingestion Engine]
     ├── Pulls AWS Cost, IAM, EKS, SecurityHub
     ├── Normalizes JSON and Metrics
     ├── Stores Metadata → Postgres
     ├── Enriches Data → RAG + Vector Store (FAISS)


```
## Liyveo AI Core

The **AI Brain** that powers all cloud insights and conversations.

```text
[Liyveo AI Core]
     ├── LLM: GPT-5 (LangChain Orchestration)
     ├── Cost Intelligence Tool (Cost Explorer API)
     ├── IAM Analyzer Tool (AWS IAM SDK)
     ├── EKS Visualizer Tool (Kubernetes API)
     ├── Security Insights Tool (Security Hub + Trivy)
     ├── RAG Context Builder (FAISS Vector Store)
     ├── Voice Interface (Whisper + Polly)

```
## Liyveo Dashboard Service

Interactive web dashboard providing full visibility of your AWS environment.

```text
[Liyveo Dashboard]
     ├── Cost Analytics: by Service, Region, Tag
     ├── IAM Risk Heatmaps
     ├── EKS Cluster Visualization
     ├── Security Findings Summary
     ├── AI Chat Console

```
##  Pipeline Example — AI Query Flow

Below shows how Liyveo processes a **voice-based cloud query**, combining AWS data, LLM reasoning, and voice synthesis.
```text
Voice → Whisper (ASR)
       ↓
Text → GPT-5 → Intent Detection (“check my EC2 cost”)
       ↓
Tool Execution → Cost Explorer API
       ↓
Response → GPT-5 → Formatted Summary
       ↓
Voice → Polly → Spoken Reply
       ↓
Dashboard → Displays Data Visualization

```

##  Liyveo Modules

The **Liyveo Voice Engine** enables fully voice-driven interactions — converting speech to text and back to natural human-like responses with emotional tone and multilingual support.

```text
[Liyveo Voice Engine]
     ├── ASR → Whisper → Converts Speech → Text
     ├── TTS → Polly / Google / VITS → Converts Text → Speech
     ├── Multi-Language → English, Hindi, etc.
     ├── Emotion Detection → Adjusts Tone Dynamically
```

##  Liyveo Vision Engine

### 1. FinOps Module

Tracks and optimizes AWS spend using Cost Explorer APIs.

```text

[Liyveo FinOps]
     ├── Service-wise cost breakdown
     ├── Forecasting via AI regression
     ├── Tag-based allocation reports
     ├── Recommendations (Idle/Underutilized)

```

##  Liyveo Insights Engine *(Optional – Future Module)*

The **Liyveo Insights Engine** turns user interactions into actionable retail intelligence — helping predict trends, optimize product catalogs, and guide merchandising decisions.

```text
[Liyveo Insights Engine]
     ├── Tracks User Behavior → Searches / Clicks / Purchases
     ├── Builds Product Popularity Heatmaps
     ├── Predicts Emerging Trends (Colors / Styles / Categories)

```
### 2. SecOps Module

Analyzes IAM, WAF, and container scans to strengthen compliance posture.


```text
[Liyveo SecOps]
     ├── IAM Analyzer → Detects risky privileges
     ├── WAF Advisor → Ensures OWASP protection
     ├── Trivy / BlackDuck Integration → Image scans
     ├── Security Hub Findings → Unified dashboard

```
### 3. CloudOps Module

Visualizes all EKS workloads and cloud resources.

```
[Liyveo CloudOps]
     ├── EKS Cluster Map (pods, deployments, services)
     ├── Node and namespace health
     ├── Resource utilization and scaling trends
     ├── Cross-account environment map

```

## Core Database Schema

This section illustrates how **Liyveo** handles a multimodal user query — combining **vision**, **language**, and **voice** to deliver a seamless AI shopping experience.
```
[Postgres Database]
     ├── users → Registered platform users
     ├── aws_accounts → Client AWS credentials / roles
     ├── cost_reports → Historical billing data
     ├── iam_analysis → Over-permissive roles
     ├── eks_clusters → Cluster and workload metadata
     ├── security_findings → Vulnerability data
     ├── chat_logs → AI interaction logs
```
---

## Example Table: cost_reports

```sql
CREATE TABLE cost_reports (
  id SERIAL PRIMARY KEY,
  account_id TEXT,
  service TEXT,
  cost NUMERIC,
  currency TEXT,
  start_date DATE,
  end_date DATE,
  data JSONB
);
```


## AI Workflow (End-to-End)

Liyveo’s conversational workflow blends voice, reasoning, and automation:

```
User Query: “What’s my IAM risk this week?”
     ↓
LLM (GPT-5) → Detects intent (“IAM risk summary”)
     ↓
LangChain Tool → Calls IAM Analyzer
     ↓
AWS API → Returns role data
     ↓
LLM → Formats report
     ↓
Response → Shown in dashboard + spoken by voice
```

---

###  AI Tech Stack Summary

| **Layer**             | **Technology**                     |
| --------------------- | ---------------------------------- |
| **Framework**         | FastAPI (Python 3.11)              |
| **Database**          | PostgreSQL + Redis                 |
| **Cloud SDK**         | Boto3 + Kubernetes Python Client   |
| **AI Model**          | GPT-5 (OpenAI) via LangChain Tools |
| **Voice Engine**      | Whisper (ASR) + Polly (TTS)        |
| **Vector Store**      | FAISS (Contextual Retrieval)       |
| **Containerization**  | Docker + ECS (Dev) / EKS (Prod)    |
| **Monitoring**        | Prometheus / Grafana               |
| **Security Scanning** | Trivy / BlackDuck / SonarQube      |
| **Auth (Future)**     | AWS Cognito / JWT-based            |

---

## Architecture Highlights

- **Unified Cloud Intelligence Layer:**  
  AI + Automation for Cost, Security, and Kubernetes insights.
  
- **Voice + Chat Copilot:**  
  Natural conversational interface for any AWS query.  

- **Multi-Account Support:**  
  Cross-account AWS access via AssumeRole
  
- **Extensible Tooling:**  
  Plug in new scanners, cost optimizers, or AI models.  

- **DevOps Native:**  
  Built for containerized environments (ECS/EKS).  

---


### Developer Integration Points
Liyveo provides REST APIs to access all modules programmatically.


| **Endpoint**                 | **Description**                  |
| ---------------------------- | -------------------------------- |
| `/api/chat`                  | AI conversation (text-based)     |
| `/api/voice`                 | Voice input → AI → voice output  |
| `/api/aws/cost/usage`        | Fetch AWS cost by date range     |
| `/api/aws/iam/analyze`       | Detect over-permissive IAM roles |
| `/api/aws/eks/clusters`      | List and describe EKS workloads  |
| `/api/aws/security/findings` | Retrieve Security Hub findings   |
| `/api/report/sync`           | Trigger background sync job      |

---

## Deployment
**ECS (Development)**

```text
docker build -t liyveo-cloudops .
docker-compose up

```
**EKS (Production)**
```text
kubectl apply -f deploy/liyveo-deployment.yaml
kubectl apply -f deploy/liyveo-service.yaml
```

## Environment Configuration

```
APP_NAME=Liyveo CloudOps AI
APP_ENV=production
AWS_REGION=ap-south-1

POSTGRES_URL=postgresql+psycopg2://user:pass@db:5432/liyveo
REDIS_URL=redis://redis:6379/0

OPENAI_API_KEY=<your_gpt5_key>
ENABLE_AI_ASSISTANT=1
ENABLE_VOICE=1
```

---
## Future Roadmap

| **Planned Feature**         | **Description**                                |
| ---------------------------- | ---------------------------------------------- |
| **Azure & GCP Support**      | Multi-cloud expansion for cost and security analysis. |
| **Drift Detection Engine**   | Automatically track and alert on infrastructure drifts. |
| **Cost Anomaly Detection**   | Machine learning–based monitoring for unexpected cloud spend. |
| **Security Remediation Bot** | Automated IAM, WAF, and Config rule fix recommendations. |
| **CI/CD Advisor**            | Continuous integration insights with SonarQube and pipeline analysis. |
| **AI FinOps Coach**          | Personalized cost optimization and insights powered by GPT-5. |

---


## Liyveo — Prototype Architecture (AI-First System)

The **Liyveo Prototype Architecture** is designed as a modular, AI-first system that connects your eCommerce backend with multimodal AI services — enabling real-time conversational shopping across text, voice, and vision interfaces.

---

```text
                 ┌────────────────────────────────────────────┐
                 │           AWS Account(s)                   │
                 │  (EC2, S3, IAM, EKS, SecurityHub, Cost)    │
                 └───────────────┬────────────────────────────┘
                                 │
                                 ▼
                      ┌──────────────────────────┐
                      │  Liyveo Data Collector   │
                      │  - Cost Explorer (FinOps)│
                      │  - IAM Analyzer (SecOps) │
                      │  - EKS Inspector (Cloud) │
                      │  - Security Scanner       │
                      └───────────┬──────────────┘
                                  │
                     ┌────────────┴───────────────┐
                     │                            │
        ┌──────────────────────────────┐   ┌──────────────────────────────┐
        │  PostgreSQL (Core Database)  │   │   Redis / Celery (Scheduler)  │
        │  - cost_reports              │   │   - background sync jobs      │
        │  - iam_analysis              │   │   - periodic data fetch       │
        │  - eks_clusters              │   │   - report generation         │
        │  - security_findings         │   └──────────────────────────────┘
        └──────────────┬───────────────┘
                       │
                       ▼
              ┌──────────────────────────────┐
              │  Liyveo AI Core (GPT-5)      │
              │──────────────────────────────│
              │  - LangChain Orchestration    │
              │  - RAG + FAISS Vector Store   │
              │  - FinOps Toolchain           │
              │  - SecOps Analyzer            │
              │  - CloudOps Visual Engine     │
              │  - Voice Interface (Whisper)  │
              │  - TTS Engine (Polly / VITS)  │
              └──────────────┬───────────────┘
                             │
                             ▼
           ┌───────────────────────────────────────────┐
           │   Liyveo Dashboard + Conversational UI     │
           │───────────────────────────────────────────│
           │  - Cost Optimization Dashboard (FinOps)    │
           │  - IAM Risk Map & Policy Insights          │
           │  - EKS Cluster Visualization               │
           │  - Security Advisor (Trivy / SonarQube)    │
           │  - AI Chat + Voice Assistant               │
           │  - Reports & Forecasts                     │
           └───────────────────────────────────────────┘
                             │
                             ▼
           ┌───────────────────────────────────────────┐
           │   User Channels & Integrations             │
           │───────────────────────────────────────────│
           │  - Web Dashboard (React / Next.js)         │
           │  - CLI & API Access                        │
           │  - Slack / Teams Bots                      │
           │  - Voice Console (Smart Speaker UI)        │
           └───────────────────────────────────────────┘


```
##  Component Breakdown

---

#### **1. Liyveo Data Collector**
The ingestion layer that continuously synchronizes cloud data.

- Connects via **AWS SDK (boto3)**  
- Fetches data from **Cost Explorer**, **IAM**, **EKS**, and **Security Hub**  
- Normalizes and stores results in **PostgreSQL**  
- Runs on schedule using **Celery + Redis** for background jobs  

---

#### **2. Liyveo AI Core**
The reasoning engine — where **GPT-5** and **LangChain** process cloud data, context, and natural queries.

- Uses **RAG (Retrieval-Augmented Generation)** for contextual awareness  
- Provides **FinOps**, **SecOps**, and **CloudOps** capabilities  
- Converts **voice → text → LLM → voice** for conversational interaction  
- Can query multiple AWS accounts using **STS AssumeRole**  

---

#### **3. Liyveo Dashboard**
An interactive visualization and control center.

- Real-time **cost & usage dashboards**  
- **EKS topology map** (clusters → deployments → pods)  
- **IAM risk visualization** and compliance summaries  
- **Security posture reports** from Security Hub, Trivy, and SonarQube  
- **AI-powered “Ask Your Cloud”** chat interface  

---

#### **4. Voice & Chat Interface**
Natural communication layer between the user and the system.

- **Whisper** → speech-to-text (ASR)  
- **GPT-5 (LLM)** → reasoning and contextual insight  
- **Polly / VITS** → text-to-speech (TTS) output  
- Multi-language and **emotion-aware responses**  
- Integrated into the **web dashboard** and **CLI** for seamless access  

---

#### **5. Background Task Layer**
Asynchronous engine for scheduled syncs, anomaly alerts, and notifications.

- **Celery workers** fetch cost, IAM, EKS, and security data  
- **Redis queue** for scalable job orchestration  
- Automated **FinOps reporting** (daily / weekly)  
- **Security notifications** delivered via Slack or email

## Cloud Infrastructure

Liyveo is designed to be **fully deployable on AWS**, with a modular architecture that supports both development and production environments.

| **Environment / Service**  | **AWS Component**         | **Purpose**                                          |
| -------------------------- | ------------------------- | ---------------------------------------------------- |
| **Dev (ECS)**              | Fargate Tasks             | Runs API and background jobs in development.         |
| **Prod (EKS)**             | Managed Kubernetes        | Hosts scalable API and Celery workers in production. |
| **RDS (PostgreSQL)**       | AWS RDS                   | Core relational data storage for all modules.        |
| **ElastiCache (Redis)**    | AWS ElastiCache           | Provides caching and background job queuing.         |
| **CloudWatch / Grafana**   | AWS CloudWatch + Grafana  | Monitoring, logging, and performance metrics.        |
| **ECR**                    | Elastic Container Registry| Secure Docker image storage and versioning.          |
| **Secrets Manager**        | AWS Secrets Manager       | Secure credentials and API key management.           |

##  Communication Flow
```
[User / Dashboard / Voice]
↓
[Liyveo AI Core (GPT-5)]
↓
[LangChain Tool → AWS SDK]
↓
[PostgreSQL + Redis Storage]
↓
[Visualization / Report / Voice Output]
```

**Description:**
1. **User Input:** Comes from text chat, dashboard interactions, or voice commands.  
2. **AI Core (GPT-5):** Processes natural language via LangChain with context awareness (RAG).  
3. **LangChain Tools:** Invoke specific AWS integrations (Cost Explorer, IAM, EKS, Security Hub) through **boto3**.  
4. **Storage Layer:** Results are normalized and stored in **PostgreSQL** (structured) and **Redis** (cached / queued).  
5. **Output Layer:** Processed insights are returned as:
   -  Dashboards or reports (UI)
   -  Text replies (chat)
   -  Voice responses (TTS via Polly or VITS)

---

###  Optional: Mermaid Diagram (renders directly in GitHub / Docs)

```mermaid
flowchart TD
    A[User / Dashboard / Voice] --> B[Liyveo AI Core (GPT-5)]
    B --> C[LangChain Tool → AWS SDK]
    C --> D[(PostgreSQL + Redis Storage)]
    D --> E[Visualization / Report / Voice Output]

## Vision Statement

> **“Liyveo redefines how humans manage the cloud — 
> not through dashboards and CLI commands, but through conversation, insight, and automation.”**











