# Explainable Anomaly Detection using LLM

## Overview

This repository contains materials and results related to the paper **"Explainable Anomaly Detection in Network Traffic Using LLM"** by Kamil Jerabek, Josef Koumar, Jiří Setinský, and Jaroslav Pešek. The study explores how Large Language Models (LLMs) can enhance explainability in network anomaly detection, integrating them with an existing ML-based anomaly detection framework.

## Repository Structure

```
📂 explainable_anomaly_detection_using_LLM
├── 📂 prompts               # Prompts used for querying LLMs
│   ├── 📂 with_future       # Prompts using future datapoints
│   ├── 📂 without_future    # Prompts without future datapoints
│
├── 📂 results               # Results from Promprint evaluation
│   ├── GPT-4_with_future.csv
│   ├── GPT-4_without_future.csv
│   ├── GPT-4o-mini_with_future.csv
│   ├── GPT-4o-mini_without_future.csv
│   ├── GPT-4o_with_future.csv
│   ├── GPT-4o_without_future.csv
│   ├── Gemini_2.0_Flash_Experimental_with_future.csv
│   ├── Gemini_2.0_Flash_Experimental_without_future.csv
│
├── README.md                # This documentation
```

## Methodology

The methodology followed in this study consists of the following steps:

1. **Volumetric Network Time Series Data** - Time series data collected from the CESNET ISP network.
2. **Anomaly Detection** - ML-based framework detecting anomalies in network traffic.
3. **Expert Annotation** - Human experts labeling anomalies as false positives or security incidents.
4. **LLM-Based Explainability** - LLMs generating explanations for flagged anomalies.
5. **Evaluation & Correlation** - Assessing LLM outputs against expert-labeled data.

### LLM Evaluation Cases

We explore three different scenarios for LLM utilization:

- **Case 1: LLM as Autonomous Anomaly Analyst Agent** (Using past and future context)
- **Case 2: LLM as Autonomous Anomaly Alerter Agent** (Using only past context)
- **Case 3: LLM as a Human Analyst Companion** (Explaining anomalies for operators)

## Results

The results from multiple LLMs are stored in the `results/` directory. The evaluation was performed using:

- **GPT-4**
- **GPT-4o**
- **GPT-4o-mini**
- **Gemini 2.0 Flash Experimental**

### Key Findings

- **GPT-4o and Gemini 2.0 Flash Experimental** provided the most accurate explanations.
- **GPT-4o-mini** had lower precision, often misclassifying anomalies.
- **Using future context improved accuracy**, especially for detecting DDoS attacks and network outages.

## Citation

If you use this work, please cite the paper:

```bibtex
@article{jerabek2025llm,
  author    = {Kamil Jerabek and Josef Koumar and Jiří Setinský and Jaroslav Pešek},
  title     = {Explainable Anomaly Detection in Network Traffic Using LLM},
  journal   = {Sumbitter to NOMS 2025},
  year      = {2025}
}
```

If you use the dataset, please cite:

```bibtex
@article{koumar2024cesnet,
  author    = {Josef Koumar and Kamil Hynek and Tomáš Čejka and Petr Šiška},
  title     = {CESNET-Timeseries24: Time series dataset for network traffic anomaly detection and forecasting},
  journal   = {arXiv preprint arXiv:2409.18874},
  year      = {2024}
}
```

## Acknowledgments

This research was partially funded by:

- Ministry of Interior of the Czech Republic (VJ02010024 - "Flow-Based Encrypted Traffic Analysis")
- Grant Agency of CTU in Prague (SGS23/207/OHK3/3T/18)
