# System Architecture

## Purpose

This document describes the general architecture principles used across the AI Engineer Portfolio.

Each project may use a different architecture depending on its requirements.

---

## General AI Application Architecture

A typical AI application can be organized into the following layers:

User
↓
Frontend / Client
↓
Application API
↓
AI Application Layer
├── Prompt / Model
├── Retrieval
├── Tools
└── AI Validation
↓
Business Logic
↓
Data / External Services

---

## Layer Responsibilities

### 1. Frontend / Client

Responsible for:

- User interaction
- Authentication
- Displaying AI responses
- Handling loading and error states
- Sending requests to the backend

---

### 2. Application API

Responsible for:

- Authentication
- Authorization
- Request validation
- Rate limiting
- Calling application services
- Returning structured responses

---

### 3. AI Application Layer

Responsible for AI-specific behavior:

- Prompt construction
- LLM calls
- Structured outputs
- Tool calling
- Retrieval
- Context management
- AI response validation

The AI layer should not directly bypass application security or business rules.

---

### 4. Business Logic

Responsible for deterministic application behavior.

Examples:

- Checking product availability
- Calculating prices
- Checking order status
- Applying business rules
- Creating support tickets

Business rules should not depend entirely on the LLM.

---

### 5. Data and External Services

Examples:

- PostgreSQL
- pgvector
- Product database
- Order database
- External APIs
- n8n workflows
- File storage

Access should be controlled through application services and explicit tools.

---

## AI System Design Principles

### Deterministic Logic vs AI Logic

Use normal application code when the result must be deterministic.

Use AI when the problem involves:

- Natural language understanding
- Classification
- Summarization
- Information extraction
- Reasoning over retrieved context
- Conversational interaction

---

## Security Boundary

The LLM should be treated as an untrusted component.

User
↓
Application
↓
Security / Validation
↓
LLM
↓
Validation
↓
Application
↓
External Tool

The model should never receive unrestricted access to databases, APIs, or sensitive operations.

---

## Observability

Production AI systems should provide visibility into:

- Request latency
- Model usage
- Token usage
- Cost
- Errors
- Tool calls
- Retrieval results
- Evaluation results

Logs should avoid exposing sensitive user information.

---

## Evaluation

AI systems should be evaluated using representative test cases.

Evaluation may include:

- Response correctness
- Retrieval quality
- Tool selection
- Hallucination rate
- Safety behavior
- Latency
- Cost

---

## Scalability

Architecture should allow individual components to scale independently when necessary.

Potential strategies include:

- Stateless APIs
- Connection pooling
- Caching
- Background jobs
- Queue-based processing
- Database indexing
- Horizontal scaling

Scaling decisions should be based on measured bottlenecks rather than assumptions.

---

## Architecture Decision Rule

Choose technologies based on:

1. Problem requirements
2. Reliability
3. Simplicity
4. Security
5. Maintainability
6. Cost
7. Scalability

Technology should serve the system, not the other way around.
