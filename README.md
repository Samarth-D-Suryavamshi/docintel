# DocIntel

DocIntel is a cloud-native document intelligence platform that automates document summarization through an asynchronous NLP processing pipeline. The platform supports secure document ingestion, large-scale text processing, API-driven summarization workflows, monitoring, analytics, and production-oriented deployment practices.

---

## Problem Statement

Organizations frequently process large volumes of reports, research papers, technical documentation, and operational records. Manual review workflows are time-consuming, difficult to scale, and often produce inconsistent outcomes.

DocIntel addresses this challenge by providing an automated document summarization platform capable of processing uploaded documents and generating concise summaries through a scalable NLP pipeline.

---

## Solution Overview

The platform accepts PDF, DOCX, and TXT documents, validates uploaded files, extracts textual content, performs token-aware preprocessing, generates summaries using a fine-tuned BART model, and exposes results through both a web dashboard and developer APIs.

The architecture separates document ingestion, processing, storage, monitoring, analytics, and API management to improve maintainability, reliability, and scalability.

---

## Key Features

### User Features

* Secure document uploads
* Batch upload support
* Processing status tracking
* Summary generation and retrieval
* Downloadable summaries
* Notification center
* Usage analytics
* Account management

### API Platform

* API key generation
* API key rotation and revocation
* Programmatic summarization
* API usage monitoring
* Request logging and analytics

### Processing Engine

* Asynchronous job execution
* Queue-based processing workflows
* Text extraction and preprocessing
* Token-aware chunking
* Recursive summarization
* Summary aggregation

### Administrative Features

* User monitoring
* Queue monitoring
* Error tracking
* Model monitoring
* System analytics
* Failed job inspection

### AI Features

* Fine-tuned BART summarization model
* Abstractive summarization
* Hierarchical chunk processing
* Batch inference workflows

---

## Architecture Characteristics

* Asynchronous Processing Architecture
* Queue-Based Workflows
* Stateless REST API Layer
* Modular Service Design
* Cloud-Native Storage Strategy
* Horizontal Scaling Ready
* Production-Oriented Monitoring

---

## System Architecture

### High-Level Workflow

```text
User Upload
      │
      ▼
FastAPI Backend
      │
      ▼
File Validation
      │
      ▼
AWS S3 Storage
      │
      ▼
Job Queue
      │
      ▼
Background Workers
      │
      ▼
Text Extraction
      │
      ▼
Chunk Processing
      │
      ▼
BART Inference
      │
      ▼
Summary Storage
      │
      ▼
Dashboard / API Retrieval
```

### Architecture Diagram

![Architecture Diagram](architecture/architecture.png)

Detailed architecture documentation is available in:

```text
docs/architecture.md
```

---

## Technology Stack

| Layer          | Technologies                                    |
| -------------- | ----------------------------------------------- |
| Frontend       | React, Vite, TypeScript, TailwindCSS, shadcn/ui |
| Backend        | FastAPI, SQLAlchemy, Celery, REST APIs          |
| Database       | PostgreSQL (AWS RDS)                            |
| Storage        | AWS S3                                          |
| Infrastructure | AWS EC2, CloudWatch, ACM                        |
| AI/ML          | BART, PyTorch, Hugging Face Transformers        |

---

## Project Structure

```text
DocIntel/
│
├── backend/
├── frontend/
├── ml/
├── docs/
├── architecture/
├── screenshots/
├── deployment/
└── README.md
```

---

## Implementation Highlights

### Architecture Decisions

* Asynchronous processing for long-running NLP workloads
* Separation of ingestion and processing lifecycles
* Dedicated job management workflows
* Modular service boundaries

### Scalability Considerations

* S3-based document storage
* Stateless API services
* Queue-driven processing
* Independent worker scaling

### Performance Optimizations

* Recursive chunk summarization
* Batched inference execution
* Background worker processing
* Indexed PostgreSQL queries

### Security Measures

* OAuth authentication
* JWT authorization
* API key hashing
* Presigned S3 URLs
* Rate limiting
* Role-based access control

### Engineering Trade-Offs

| Decision                | Reason                              |
| ----------------------- | ----------------------------------- |
| BART over larger LLMs   | Reduced infrastructure requirements |
| Polling over WebSockets | Simpler operational model           |
| Monolithic deployment   | Appropriate for MVP scale           |
| PostgreSQL over MongoDB | Strong analytical capabilities      |

---

## Screenshots

### Landing Page

![Landing Page](screenshots/landing-page.png)

### Dashboard

![Dashboard](screenshots/dashboard.png)

### Upload Workflow

![Upload Workflow](screenshots/upload.png)

### Summary Viewer

![Summary Viewer](screenshots/summary-viewer.png)

---

## Quick Start

```bash
git clone https://github.com/your-username/docintel.git
cd docintel
```

### Start Application

```bash
docker compose up
```

Detailed deployment instructions:

```text
docs/deployment.md
```

---

## Documentation

* Architecture: `docs/architecture.md`
* API Reference: `docs/api.md`
* Deployment Guide: `docs/deployment.md`
* ML Pipeline: `docs/ml-pipeline.md`
* Security Design: `docs/security.md`

---

## Future Enhancements

### Platform

* Team workspaces
* Organization-level access control
* Audit logging

### AI/ML

* Multi-language summarization
* Long-document transformer support
* Automated evaluation pipelines

### Infrastructure

* Container orchestration
* Auto-scaling workers
* Event-driven processing

---

## Learning Outcomes

### Technical Concepts

* NLP model fine-tuning
* Transformer architectures
* Async workflow design
* Cloud-native storage systems
* API engineering
* Monitoring and observability

### Engineering Challenges

* Handling model token limitations
* Designing scalable processing pipelines
* Secure file storage and retrieval
* Workflow orchestration for NLP workloads

### Skills Demonstrated

* Full-Stack Development
* Machine Learning Engineering
* Cloud Deployment
* API Development
* Database Architecture
* System Design
* Production-Oriented Engineering

---

## Team Contributions

| Contributor                | Responsibility                                               |
| -------------------------- | ------------------------------------------------------------ |
| Samarth D Suryavamshi      | System Architecture, Backend Engineering, ML Pipeline Design |
| Sanmati Payappa Topannavar | Frontend Development                                         |
| Rounak Sharma              | Application Development                                      |
| Pratiksha D Korishettar    | UI/UX & Platform Support                                     |
| Lakshmi Shital             | Documentation & Testing                                      |

---

## Contributors

| Contributor | GitHub | LinkedIn |
|-------------|--------|----------|
| Samarth D Suryavamshi | [GitHub](https://github.com/Samarth-D-Suryavamshi) | [LinkedIn](https://www.linkedin.com/in/samarth-suryavamshi-a15642298/) |
| Sanmati Payappa Topannavar | [GitHub](https://github.com/sanmati2005) | [LinkedIn](https://www.linkedin.com/in/sanmati-payappa-topannavar-86a30b327/) |
| Rounak Sharma | [GitHub](https://github.com/rounak43) | N/A |
| Pratiksha D Korishettar | N/A | [LinkedIn](https://www.linkedin.com/in/pratiksha-d-korishettar) |
| Lakshmi Shital | N/A | [LinkedIn](https://www.linkedin.com/in/lakshmi-shital-4165922a3) |
