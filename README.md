 🛡️ SecureLLMOps – AI Security, Monitoring & Evaluation Framework

An AI Security project exploring LLM security, gateway management, observability, and evaluation of Retrieval-Augmented Generation (RAG) applications.

![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![LLM](https://img.shields.io/badge/AI-Generative%20AI-purple)
![Security](https://img.shields.io/badge/Focus-AI%20Security-red)
![Evaluation](https://img.shields.io/badge/LLM-Evaluation-green)
![Status](https://img.shields.io/badge/Status-Learning%20%26%20Development-orange)

 📌 Project Overview

Large Language Models (LLMs) are increasingly used in chatbots, AI agents, and Retrieval-Augmented Generation (RAG) applications.

However, these applications introduce challenges such as:

- Prompt injection and malicious user inputs.
- Hallucinations and inaccurate responses.
- Sensitive information exposure.
- Unreliable LLM API responses.
- Lack of application monitoring and tracing.
- Difficulty evaluating LLM response quality.

SecureLLMOps is a hands-on learning and experimentation project that explores different techniques and tools to improve the security, reliability, observability, and evaluation of LLM-powered applications.

The project is organized into five Jupyter notebooks, each focusing on a specific component of the LLM application lifecycle.

 🏗️ Project Architecture

```text
                USER INPUT
                    |
                    v
          +--------------------+
          |    LLM Gateway     |
          |      Portkey       |
          +--------------------+
                    |
                    v
          +--------------------+
          |  Security Layer    |
          |   Guardrails AI    |
          |                    |
          | Input Validation   |
          | Output Validation  |
          +--------------------+
                    |
                    v
          +--------------------+
          |   RAG Application  |
          |                    |
          | Embeddings         |
          | Vector Retrieval   |
          | LLM Generation     |
          +--------------------+
                    |
                    v
          +--------------------+
          |  Generated Answer  |
          +--------------------+
                    |
          +---------+----------+
          |                    |
          v                    v
   +-------------+      +-------------+
   | LangSmith   |      | Evaluation  |
   | Observability|     |             |
   |             |      | DeepEval    |
   | Logging     |      | RAGAS       |
   | Tracing     |      |             |
   +-------------+      +-------------+
```

Note: This diagram represents the conceptual relationship between the five independently developed notebooks. They are not yet integrated into one running application.

 📚 Project Modules

 1. LLM Evaluation using DeepEval

Notebook: `deep_eval.ipynb`

Explores evaluation techniques for measuring the quality, correctness, and safety of LLM-generated responses.

Concepts explored:

- Answer Relevancy
- Faithfulness
- Contextual Precision
- Contextual Recall
- Hallucination Detection
- Bias Detection
- Toxicity Detection
- Custom G-Eval Metrics
- DAG-Based Evaluation
- Arena G-Eval for Model/Response Comparison

Objective: Evaluate LLM responses using metrics, thresholds, and LLM-as-a-Judge techniques.

 2. LLM Gateway using Portkey

Notebook: `gateway.ipynb`

Explores how an LLM Gateway provides a unified interface between applications and different LLM providers.

Capabilities explored:

- Unified LLM API Access
- Provider Configuration
- User-Level Request Tracing
- Metadata Tracking
- Retry Mechanisms
- Request Timeout Handling
- Model Fallback
- Load Balancing
- Response Caching

Objective: Understand how to improve the reliability, management, and observability of LLM API requests.

 3. LLM Security and Guardrails

Notebook: `guard_rail.ipynb`

Explores Guardrails AI to validate and control inputs and outputs in LLM applications.

Concepts explored:

- Custom Validators
- Input Validation
- Output Validation
- Prompt Injection Detection Concepts
- Restricted Topic Validation
- Sensitive Information Validation Concepts
- Text Cleaning and Redaction
- Grounded Response Validation
- OnFailAction Mechanisms

OnFailAction techniques:

- FIX
- FILTER
- REFRAIN
- EXCEPTION
- NOOP
- REASK

Objective:Understand how programmatic validation can help prevent unwanted inputs and outputs from reaching users.

 4. LLM Observability using LangSmith

Notebook:`observability.ipynb`

Explores monitoring, tracing, and debugging LLM-powered applications using LangSmith.

Concepts explored:

- LLM Logging
- Execution Tracing
- Prompt and Response Tracking
- Retriever Tracing
- RAG Pipeline Monitoring
- LangGraph Integration
- Tool Calling
- Order Status Lookup
- Refund Calculation Tool

Objective: Understand how to inspect LLM execution flows, troubleshoot failures, and monitor application behaviour.

 5. RAG Evaluation using RAGAS

Notebook: `ragas_evaluation.ipynb`

Explores evaluation of Retrieval-Augmented Generation applications using RAGAS.

The notebook creates a sample customer-support RAG application using LangChain, OpenAI embeddings, and an in-memory vector store.

Evaluation metrics:

- Faithfulness
- Answer Relevancy
- Context Precision
- Context Recall

Objective: Measure retrieval quality and answer generation quality using reference-based evaluation and LLM-as-a-Judge techniques.

 🛠️ Technology Stack

| Category | Technologies |
|---|---|
| Programming Language | Python |
| Notebook Environment | Jupyter Notebook |
| LLM Framework | LangChain |
| Agent Framework | LangGraph |
| LLM Gateway | Portkey |
| AI Guardrails | Guardrails AI |
| Observability | LangSmith |
| LLM Evaluation | DeepEval |
| RAG Evaluation | RAGAS |
| Embeddings | OpenAI Embeddings |
| Vector Database | LangChain InMemoryVectorStore |
| LLM | GPT-4o-mini |
| Environment Management | python-dotenv |

 📂 Project Structure

```text
SecureLLMOps/
│
├── deep_eval.ipynb
│
├── gateway.ipynb
│
├── guard_rail.ipynb
│
├── observability.ipynb
│
├── ragas_evaluation.ipynb
│
├── README.md
│
├── requirements.txt
│
└── .env.example
```

 ⚙️ Installation and Setup

1. Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/SecureLLMOps.git

cd SecureLLMOps
```

2. Create a Virtual Environment

```bash
python -m venv venv
```

Activate it:

Windows:

```bash
venv\Scripts\activate
```

Linux / macOS:

```bash
source venv/bin/activate
```
 3. Install Dependencies

```bash
pip install jupyter python-dotenv
pip install portkey-ai guardrails-ai
pip install deepeval ragas
pip install langchain langchain-openai langchain-core
pip install langsmith langgraph
```
 4. Configure Environment Variables

Create a `.env` file in the project root directory.

```env
# OpenAI
OPENAI_API_KEY=your_openai_api_key

# Portkey
PORTKEY_API_KEY=your_portkey_api_key
PORTKEY_PROVIDER=@openai-prod
PORTKEY_MODEL=gpt-4o-mini

# LangSmith
LANGSMITH_API_KEY=your_langsmith_api_key
LANGSMITH_TRACING=true
LANGSMITH_PROJECT=SecureLLMOps
```

Never upload your actual `.env` file or API keys to GitHub.

 5. Launch Jupyter Notebook

```bash
jupyter notebook
```

Open the notebooks individually and execute their cells in order.

 📊 RAGAS Evaluation Results

The RAGAS notebook contains a sample evaluation using four customer-support questions.

Recorded evaluation output:

| Evaluation Metric | Score |
|---|---:|
| Faithfulness | 1.0000 |
| Answer Relevancy | 0.8414 |
| Context Precision | 1.0000 |
| Context Recall | 1.0000 |

Observations:

- Faithfulness achieved a score of 1.0.
- Answer relevancy achieved a score of 0.8414.
- Context precision and recall achieved scores of 1.0.

These are results from a small experimental dataset of four questions, not a production benchmark or a guarantee of performance on unseen questions.

 🎯 Learning Outcomes

Through this project, I explored:

1. How to evaluate LLM-generated responses.
2. How to configure an LLM Gateway for reliability.
3. How to validate user inputs and model outputs.
4. How to identify and handle potentially malicious prompts.
5. How to trace and monitor LLM applications.
6. How to measure RAG retrieval and generation quality.
7. How to use LLM-as-a-Judge evaluation techniques.
8. How to investigate the reliability and security challenges of LLM applications.

 🚀 Future Improvements

- Integrate the five modules into one application.
- Improve prompt injection detection with adversarial testing.
- Implement stronger input and output security policies.
- Expand RAG evaluation datasets to 50–100+ test cases.
- Add automated security and regression tests.
- Measure false-positive and false-negative rates.
- Add latency, token usage, and cost monitoring.
- Develop a Streamlit-based monitoring dashboard.
- Explore secure AI agent and MCP tool execution.

👨‍💻 Author

Suprith S

B.Tech – Artificial Intelligence and Data Science

Interested in Generative AI, LLM Engineering, AI Security, and LLMOps.

---

project:SecureLLMOps – AI Security, Monitoring & Evaluation Framework

Built as a hands-on exploration of security, reliability, observability, and evaluation techniques for LLM-powered applications.
