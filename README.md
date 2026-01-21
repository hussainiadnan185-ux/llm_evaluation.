# LLM Evaluation & Failure Analysis

This project evaluates and compares open-source large language models using Hugging Face to understand differences in response behavior and inference latency.

## Objective
To analyze how instruction-tuned and base language models perform on factual and explanatory prompts, and identify suitability for question-answering tasks.

## Models Used
- microsoft/Phi-3-mini-4k-instruct
- distilgpt2

## Methodology
- Ran multiple factual and explanatory prompts on each model.
- Measured response latency and output length.
- Compared response quality and observed failure modes.

## Key Observations
- The base model (distilgpt2) produced very fast responses but failed to handle instruction-based prompts.
- The instruction-tuned model (Phi-3 Mini) generated more coherent and informative answers with higher latency.
- The results highlight a clear trade-off between speed and response quality.

## Conclusion
For instruction-heavy tasks such as Q&A and explanations, instruction-tuned models are more suitable than base language models. An improvement would involve replacing base models with instruction-tuned alternatives.

## Tools & Technologies
Python, Hugging Face Transformers, Pandas
