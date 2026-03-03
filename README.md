Enterprise Incident Copilot (RAG)

Overview

This project implements a Retrieval-Augmented Generation (RAG) assistant designed to analyze enterprise incident logs and provide grounded troubleshooting recommendations using internal runbook guidance. The system combines semantic retrieval with LLM-based generation to reduce hallucinations and improve response relevance.

Problem Statement

Enterprise platforms (e.g., SAP-like systems) generate frequent operational incidents such as login failures, Kafka lag, database timeouts, or high CPU usage. Engineers often rely on internal runbooks for troubleshooting. This project automates that process by retrieving relevant runbook sections and generating context-grounded guidance.

Architecture
	1.	Runbook documents are chunked into smaller segments.
	2.	Chunks are converted into vector embeddings using SentenceTransformers.
	3.	Embeddings are stored in a FAISS vector index.
	4.	Incident logs are embedded and top-k relevant chunks are retrieved.
	5.	A prompt template generates grounded recommendations using retrieved context with citation references.

Key Features
	•	Retrieval-Augmented Generation (RAG)
	•	Embedding-based semantic search
	•	FAISS vector indexing
	•	Prompt engineering with citation enforcement
	•	Retrieval evaluation across simulated enterprise scenarios
	•	Reduced hallucination through context grounding

Tech Stack
	•	Python
	•	Hugging Face SentenceTransformers
	•	FAISS (Vector Similarity Search)
	•	Prompt Engineering
	•	OpenAI API (optional for generation)

Example Use Case

Input: Enterprise incident log (e.g., SAML login failure, Kafka lag)
Output:
	•	Incident summary
	•	Likely root cause
	•	Recommended remediation steps
	•	Citation of relevant runbook sections
