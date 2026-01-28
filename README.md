# LLM Evaluation & Failure Analysis

## Overview
This project implements a Python-based evaluation workflow to analyze and compare open-source Large Language Models (LLMs using Hugging Face. The objective is to understand differences in response behavior, failure modes, and inference latency when models are applied to factual and explanatory question-answering tasks.

Instead of focusing on model training or deployment, the project emphasizes **evaluation, comparison, and reasoning**, which are critical for selecting appropriate LLMs in real-world AI and analytics use cases.

---

## Execution Environment
- Language: Python  
- Environment: Google Colab (GPU-enabled runtime)  
- Libraries: Hugging Face Transformers, Pandas  
- Execution Mode: Jupyter Notebook  

This project is intentionally implemented as a notebook to support exploratory evaluation, rapid iteration, and transparent inspection of model outputs.

---

## How to Run
1. Open the notebook file `llm_evaluation.ipynb` in Google Colab.
2. Enable GPU support:
   - Runtime → Change runtime type → Hardware accelerator → GPU.
3. Run the notebook cells sequentially from top to bottom:
   - Install required libraries
   - Execute the model evaluation cell
   - Generate the comparison summary
4. The evaluation results will be displayed in the notebook and saved as `llm_evaluation_results.csv`.
5. Download the CSV file from the Colab file explorer if needed for further analysis or sharing.

All results are generated automatically by the notebook without any manual intervention.

---

## Models Evaluated
- **microsoft/Phi-3-mini-4k-instruct**  
  Instruction-tuned model designed for structured question answering and explanations.

- **distilgpt2**  
  Lightweight base language model used as a performance and behavior baseline.

---

## Evaluation Prompts
The models were evaluated using a fixed set of factual and explanatory prompts, including:
- General knowledge questions
- Concept explanations (AI, ML, Data Analyst role)
- List-based factual queries

The same prompts were applied to all models to ensure a fair comparison.

---

## Evaluation Workflow
The evaluation process follows a deterministic and repeatable flow:

1. Load open-source LLMs using Hugging Face pipelines  
2. Run identical prompts on each model  
3. Capture raw model responses  
4. Measure inference latency for each response  
5. Record response length as a proxy for output verbosity  
6. Persist all results in a structured CSV for analysis  

---

## Metrics Collected
- **Response Text**  
  Raw model output for qualitative inspection

- **Latency (seconds)**  
  Time taken to generate each response

- **Response Length**  
  Number of characters in the generated output

These metrics allow both quantitative comparison and qualitative failure analysis.

---

## Outputs

### Evaluation Results Dataset
- Path: `llm_evaluation_results.csv`
- Contains:
  - model name
  - prompt
  - model response
  - latency in seconds
  - response length

The dataset enables transparent comparison of model behavior across prompts.

---

## Key Observations
- The base language model (**distilgpt2**) demonstrated very low latency but failed to handle instruction-based prompts, often producing incoherent or repetitive outputs.
- The instruction-tuned model (**Phi-3 Mini**) generated more coherent, factual, and structured responses, albeit with higher inference latency.
- The results reveal a clear trade-off between **speed** and **response quality** when selecting LLMs for question-answering tasks.

---

## Conclusion
For instruction-heavy use cases such as factual Q&A and explanations, instruction-tuned models are significantly more suitable than base language models. While lightweight models may offer faster responses, they are prone to failure when prompts require structured understanding.

A potential improvement would involve replacing base models with instruction-tuned alternatives.

---

## Limitations
- Evaluation is limited to a small set of prompts
- No automated scoring or human-labeled accuracy metrics
- Response quality assessment is qualitative
- No fine-tuning or deployment considerations included

---

## Future Improvements
- Expand prompt set across multiple domains
- Add human-labeled evaluation or scoring criteria
- Compare additional instruction-tuned models
- Track memory usage and cost-related metrics

---

## Tools & Technologies
Python, Hugging Face Transformers, Pandas

---

## Author
Syed Murtuza Hussaini
