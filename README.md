Agentic RAG with Safety Measures
Project Title: Safe Academic Research Assistant
1. Project Overview
This project implements an Agentic Retrieval-Augmented Generation (RAG) system that answers academic questions from a trusted PDF knowledge base while enforcing correctness, safety, and reliability using a multi-agent orchestration approach.
The system reads uploaded academic PDFs and responds only using retrieved document evidence.
2. System Architecture
Copy code

User Query
   │
   ▼
Input Validation Agent
   │
   ▼
Retriever Agent (Vector Database)
   │
   ▼
Maker Agent (LLM)
   │
   ▼
Checker Agent (Safety & Accuracy Validator)
   │
   ▼
Final Verified Answer
3. Agent Roles
Agent
Role
Input Validator
Blocks malformed and malicious queries
Retriever Agent
Finds relevant document chunks
Maker Agent
Generates draft answer from retrieved context
Checker Agent
Verifies correctness, safety, and completeness
Refiner Agent
Regenerates answer if checker finds issues
4. Maker–Checker Loop
Step
Action
Maker
Produces initial answer
Checker
Reviews for hallucination, safety, and missing info
Refiner
Improves answer until approved
5. Safety Mechanisms
Safety Feature
Description
Input Sanitization
Detects prompt-injection and malformed inputs
Safe Tool Use
Only allows document retrieval tools
Output Filtering
Blocks hallucinated or unsafe content
Loop Validation
Checker must approve before output
6. Technologies Used
Python
LangChain
FAISS / Chroma
SentenceTransformers
OpenAI / Transformers
Google Colab
7. Example Queries & Outputs
Query
Output
What is software engineering?
An engineering discipline concerned with all aspects of software production
What are software process activities?
Requirements engineering, development, testing, and evolution
