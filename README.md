
# GraphRAG-Enhanced LLM Honeypot

> **Note**: This repository is currently under active development and the GitHub version may not reflect all the latest changes and features described in this README.

## 📜 Overview

This project explores enhancing LLM-powered shell honeypots with Graph-based Retrieval Augmented Generation (GraphRAG) techniques to create more realistic and adaptive cyber deception systems. Building upon the foundation of HoneyLLM, we implement and evaluate two distinct approaches:

1. **Automated Graph Construction** using Microsoft's GraphRAG package with OpenAI models
2. **Custom Graph Implementation** with manual knowledge graph creation and open-source LLM integration (Llama)

Our goal is to improve honeypot fidelity, session consistency, and attacker engagement through structured knowledge representation and advanced retrieval mechanisms.

## 🔍 Research Motivation

Traditional honeypots face limitations in sustaining realistic attacker engagement. While recent LLM-based approaches like HoneyLLM have shown promise, they can be further enhanced through graph-based knowledge structures that better represent command relationships, system states, and attack patterns.

## 🛠️ Technical Approach

### Approach 1: Microsoft GraphRAG Integration

This approach leverages Microsoft's GraphRAG framework to automatically extract and utilize a knowledge graph from attack traces:

- **Graph Construction**: Automatic extraction of entities and relationships from attack trace datasets
- **Community Detection**: Using Hierarchical Leiden Algorithm to identify related command groups
- **Graph Embedding**: Node2Vec for vector representations of graph entities
- **LLM Integration**: OpenAI API (GPT-4o-mini) with context retrieved from the knowledge graph

### Approach 2: Manual Graph Construction with Open Source LLMs

This approach focuses on custom knowledge engineering and model adaptation:

- **Manual Graph Building**: Domain-specific knowledge graph encoding shell commands and system states
- **Fine-Tuning**: Parameter-efficient fine-tuning of open-source LLMs (Llama) on graph-augmented traces
- **Custom Retrieval**: Tailored subgraph retrieval for context enhancement

### Hybrid Architecture

Both approaches implement a hybrid architecture that:
- Routes simple/scripted attacks to low-interaction components
- Processes complex interactive sessions through the GraphRAG-enhanced LLM
- Optimizes for performance and cost-efficiency

## 📊 Evaluation Metrics

- Response accuracy compared to ground truth
- Session consistency during multi-step attacks
- Engagement duration and interaction depth
- Command coverage across attack vectors
- Performance overhead and latency
- Cost efficiency (token consumption)

## 🏁 Current Status

This project is in active development with implementation of both approaches underway. The Microsoft GraphRAG integration is partially complete, while the custom graph implementation with Llama is in early stages.

## 📦 Dependencies

- GraphRAG package
- Sentence-transformers
- NetworkX
- PyTorch
- Transformers
- Streamlit (for demo interface)

## 🚀 Getting Started

### Installation

```bash
# Install main dependencies
pip install graphrag transformers sentence-transformers networkx torch

# For the demo interface
pip install streamlit pyngrok
```

### Basic Usage

```python
# Initialize GraphRAG environment
python -m graphrag init --root ./

# Index knowledge graph
python -m graphrag index --root ./

# Query the system
python -m graphrag query --root ./ --method global --query "your query here"
```

### Running the Demo Interface

```bash
streamlit run app.py
```

## 🔮 Future Work

- Dynamic graph updates based on new attack patterns
- Multi-stage attack modeling
- Cross-honeypot correlation
- Adversarial robustness improvements

## 📄 Citation

If you use this work in your research, please cite:

```
@misc{alaparthi2025graphrag,
  title={Enhancing LLM-powered Shell Honeypots with Graph-based Retrieval Augmented Generation},
  author={Alaparthi, Varunsai},
  year={2025},
  publisher={The Pennsylvania State University}
}
```

## 📝 License

[Insert your preferred license here]

## 🤝 Acknowledgments

This work builds upon HoneyLLM by Guan et al. and Microsoft's GraphRAG package.
