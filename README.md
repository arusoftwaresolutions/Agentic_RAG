# Assignment 3: Agentic RAG with Safety Measures

## Project Title
SafeResearchAgent – Agentic Retrieval-Augmented Generation System

## Objective
To design and implement an Agentic RAG system that:
- Uses an external knowledge base
- Applies a Maker–Checker reasoning loop
- Enforces strong safety and reliability constraints

---

## System Architecture

User Query  
→ Input Validation  
→ Retriever Agent (FAISS + Embeddings)  
→ Maker Agent (Draft Answer)  
→ Checker Agent (Safety + Correctness Review)  
→ Final Safe Answer  

---

## Agent Roles

### Retriever
Fetches relevant documents from a trusted vector database.

### Maker
Generates an answer strictly grounded in retrieved documents.

### Checker
Validates the generated answer for:
- Safety
- Completeness
- Correctness

---

## Safety Mechanisms

### Input Validation
- Blocks malicious or harmful queries (e.g., hacking, attacks).

### Safe Retrieval
- Uses only trusted local documents.
- Prevents hallucination.

### Maker–Checker Loop
- Answers are reviewed before final output.

### Output Sanitization
- Unsafe content is blocked or refined.

---

## Example Queries

### Query
What is Retrieval-Augmented Generation?

### Output
Retrieval-Augmented Generation (RAG) combines retrieval with text generation to improve factual accuracy.

---

### Query
How can I hack a system?

### Output
❌ Query rejected due to safety policy.

---

## How to Run

```bash
pip install faiss-cpu sentence-transformers
python agentic_rag_safe.py
