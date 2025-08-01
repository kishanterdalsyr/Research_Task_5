
# 📊 Research Task 5: Large Language Models 
**Topic**: Structured Data Q&A on Syracuse Women’s Lacrosse 2024 Stats  
**Notebook**: `Task_05_Large_Language_Models.py`

---

## 🧪 Objective

This project explores the **reasoning accuracy, consistency, and factual reliability** of two prominent open-source LLMs:
- 🟠 **Mistral 7B Instruct**
- 🔵 **Google Gemma 3 12B Instruct**

The evaluation is based on natural language questions generated from a real-world sports dataset (`2024SUStats.pdf`), focusing on how well each model can interpret, calculate, and reason from **structured statistical data**.

---

## 📁 Files & Assets

- `2024SUStats.pdf` – Syracuse Women's Lacrosse 2024 statistics
- `Task_05_Large_Language_Models.py` – Research notebook for model comparison
- `model_comparison_results.csv` – Results table of model outputs and verdicts

---

## 🎯 Research Goals

- Assess factual consistency in answering structured questions
- Evaluate reasoning depth with multi-hop and logic-based prompts
- Detect hallucinations or fabricated information
- Test instruction-following capabilities in simple and ambiguous scenarios

---

## 🔍 Methodology

The experiment consists of **5 test types** to assess different cognitive dimensions of LLMs:

### ✅ 1. Repetition Consistency Test
> Two questions phrased differently but semantically identical  
**Goal**: Should yield consistent answers.

### ✅ 2. Multi-Hop Reasoning Test
> Requires using multiple values to calculate a new one (e.g., averages, percentages)

### ✅ 3. Prompt Robustness Test
> Open-ended, ambiguous prompts to test coherence and focus

### ✅ 4. Math & Logic Test
> Basic arithmetic, proportion, and logic application

### ✅ 5. Ground Truth Comparison Table
> Manually verified evaluation using the PDF data

---

## 📝 Observations from Notebook

- Mistral **struggled with precision**, frequently hallucinating numbers and player names not found in the data.
- Gemma consistently:
  - Reported correct totals
  - Avoided fabrication
  - Followed instructions cleanly and with contextual awareness
- The notebook includes markdown insights and reflections after each evaluation step

---

## 📊 Summary of Results

| Category                  | Mistral 7B | Gemma 12B |
|---------------------------|------------|-----------|
| ✅ Correct Answers (6 Qs) | 1          | **3**     |
| ❌ Hallucinated Data      | Yes        | No        |
| 🧠 Subjective Handling    | Balanced   | Balanced  |
| 🧮 Multi-Step Reasoning   | Weak       | Moderate  |

---

## 🔬 Sample Findings

> **Mistral 7B Instruct**:
- Incorrectly calculated games as 24 (actual = 22)
- Hallucinated total goals as 435 (actual = 335)
- Invented a player (Emily Hawryschuk) with fake defensive stats

> **Gemma 3 12B Instruct**:
- Correctly stated win-loss record (16–6)
- Identified 335 total goals directly from PDF
- Made strategic suggestions without inventing players

---

## ✅ Final Verdict

Google **Gemma 3 12B Instruct** outperformed Mistral 7B in:
- Factual correctness
- Dataset grounding
- Reasoning integrity

This makes Gemma more suitable for **decision-making tools, coaching analysis, and factual Q&A pipelines** involving structured documents.

---

## 🧭 How to Run

1. Install required packages:
   ```bash
   pip install openai pandas
   ```

2. Set your OpenRouter API Key:
   ```python
   client = OpenAI(api_key="your_key", base_url="https://openrouter.ai/api/v1")
   ```

3. Launch and run `Task_05_Large_Language_Models.py`:
   - Prompts both models with defined questions
   - Compares responses
   - Generates a results table with verdicts

---

## 📚 Future Work

- Include more datasets (e.g., NBA season summaries, Olympic stats)
- Use RAG (Retrieval-Augmented Generation) to enrich model inputs
- Score subjective responses with human feedback
- Visualize hallucination frequency and answer confidence


---

## ⚠️ Note on Reproducibility

Large Language Models like Mistral and Gemma are **non-deterministic by default**, meaning:
- The same prompt may yield slightly different answers if executed multiple times.
- Factors such as temperature, load balancing, and context order may influence output.

> To improve reproducibility, you may reduce the temperature to 0.2 or set a fixed `seed` if the API supports it.

---

## ▶️ How to Use This Notebook

### 1. Prerequisites

- Python 3.8+
- Internet connection (for API access)
- A valid API key from [https://openrouter.ai](https://openrouter.ai)

### 2. Installation

Install required dependencies:
```bash
pip install openai pandas
```

### 3. Setup

Configure your OpenRouter API key and client:
```python
from openai import OpenAI
client = OpenAI(api_key="your-key", base_url="https://openrouter.ai/api/v1")
```

### 4. Run the Notebook

- Open `Task_05_Large_Language_Models.py` in Jupyter Notebook or VSCode
- Execute all cells step-by-step
- Compare model responses, view verdicts, and analyze structured results

---

