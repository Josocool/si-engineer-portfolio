# Engineering Principles

## 1. Build for Real Problems

Every project should solve a realistic business or user problem.

The goal is not to demonstrate AI capabilities alone, but to build useful and reliable systems.

---

## 2. Prefer Simple Solutions

Use the simplest architecture that can solve the problem.

Do not introduce frameworks, databases, agents, or infrastructure without a clear reason.

---

## 3. Never Trust LLM Output Blindly

LLM responses are probabilistic.

Important outputs must be validated before they are used by the application or passed to external systems.

---

## 4. Use Structured Outputs

When an AI system needs to communicate with application code, prefer structured data over free-form text.

Examples:

- JSON
- Typed schemas
- Validated API responses
- Function/tool calls

---

## 5. Retrieval Before Guessing

When accurate business knowledge is required, the system should retrieve information from trusted sources instead of relying only on the model's internal knowledge.

Examples:

- Product database
- Company documents
- Policies
- FAQs
- Order information

---

## 6. Tools Must Be Explicit

AI agents should only access tools that are explicitly defined and authorized.

Examples:

- Search products
- Check inventory
- Get order status
- Create support ticket

The model should not have unrestricted access to the application.

---

## 7. Security Is Part of the Design

Every AI system should consider:

- Prompt injection
- Sensitive data exposure
- Authentication
- Authorization
- Secret management
- Unsafe tool execution
- Data validation

Security should not be added only after the system is completed.

---

## 8. Evaluate AI Systems

AI systems must be evaluated, not only manually tested.

Important metrics may include:

- Accuracy
- Retrieval quality
- Tool selection accuracy
- Hallucination rate
- Response quality
- Latency
- Cost

---

## 9. Human-in-the-Loop for Risky Actions

High-impact or irreversible actions should require human approval when appropriate.

Examples:

- Refunds
- Account changes
- Financial actions
- Deleting important data
- Sending sensitive communications

---

## 10. Document Important Decisions

Important architectural and engineering decisions should be documented.

Documentation should explain:

- What was built
- Why it was built
- Why a technology was chosen
- What alternatives were considered
- Known limitations

---

## 11. Keep Secrets Out of Git

API keys, passwords, tokens, and credentials must never be committed to the repository.

Use environment variables and `.env` files locally.

---

## 12. Production Mindset

Projects should consider real-world concerns such as:

- Reliability
- Observability
- Error handling
- Performance
- Cost
- Scalability
- Security
- Maintainability
