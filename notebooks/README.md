# Notebooks for Dataset Generation and Leakage Analysis

This folder contains notebooks designed to evaluate language models' behavior with color-related prompts with the primary focus of investigating semantic leakage. It consists of two Jupyter notebooks: one for prompting large language models to obtain potential examples of semantic leakage and the other for evaluating the results in terms of Mean Leak-Rate.

## Prompting Qwen2.5 models
[This notebook](https://github.com/smilni/semantic_leakage_project/blob/main/notebooks/qwen_output_generation.ipynb) configures and uses transformer-based language models of Qwen2.5 model family to generate responses to prompts from the color-related dataset presented and described in data/.

As an output, the notebook generates several datasets, one for each model, with multiple responses for each prompt. The generation results are presented and described in data/.

## Evaluating Mean Leak-Rate of the models
[This notebook](https://github.com/smilni/semantic_leakage_project/blob/main/notebooks/leakage_analysis.ipynb) calculates semantic leakage rate (Mean Leak-Rate) using similarity metrics such as BERTScore and SentenceBERT for responses generated on the previous step.

As an output, the notebook produces Mean Leak-Rate metric across different models and categories 1, 2, and 3.
