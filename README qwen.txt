Reasoning Alignment of Qwen3-4B Using GRPO

This project explores aligning Qwen3-4B-Base for improved mathematical reasoning using Group Relative Policy Optimization (GRPO).
We fine-tune the model on the OpenR1 Math dataset, demonstrating that GRPO can significantly boost reasoning accuracy and reduce hallucinations compared to baseline and supervised fine-tuning (SFT).

--------------------------------------------------
📌 Project Overview
--------------------------------------------------
- Model: Qwen3-4B-Base
- Dataset: OpenR1 Math (https://huggingface.co/datasets/openai/openr1-math)
- Objective: Improve chain-of-thought (CoT) reasoning alignment using GRPO.
- Contributions:
  - Pre fine-tuned the model on ~60 curated examples to prime it for custom GRPO formatting.
  - Applied Supervised Fine-Tuning (SFT) on the OpenR1 Math dataset to adapt the model for structured CoT reasoning.
  - Applied GRPO for reasoning alignment, yielding:
    - +14% accuracy improvement on a held-out test set of 2,000 math problems.
    - Reduced hallucinated outputs compared to baseline and SFT-only checkpoints.
  - Evaluated performance by extracting final \boxed{} answers and comparing with ground truth.

--------------------------------------------------
🛠️ Setup
--------------------------------------------------
1. Clone Repo
   git clone https://github.com/<your-username>/qwen3b-grpo-math.git
   cd qwen3b-grpo-math

2. Install Dependencies
   pip install -r requirements.txt

3. Download Model & Dataset
   - Model: Qwen/Qwen2.5-3B (https://huggingface.co/Qwen/Qwen2.5-3B)
   - Dataset: OpenR1 Math (https://huggingface.co/datasets/openai/openr1-math)

--------------------------------------------------
🚀 Training Pipeline
--------------------------------------------------
1. Pre Fine-Tuning
   Train on ~60 curated examples to help the model adapt to custom GRPO formatting.

2. Supervised Fine-Tuning (SFT)
   Fine-tune Qwen3-4B-Base on OpenR1 Math dataset for chain-of-thought reasoning.

3. GRPO Training
   Apply GRPO to align reasoning with correctness and reduce hallucinations.

--------------------------------------------------
📊 Results
--------------------------------------------------
| Model                | Accuracy (2K test set) | Hallucinations |
|-----------------------|-------------------------|----------------|
| Baseline (Qwen3-4B)  | ~40%                    | High           |
| + SFT                | ~48%                    | Reduced        |
| + GRPO               | ~55% (+14%)             | Significantly Reduced |

--------------------------------------------------
🔍 Evaluation
--------------------------------------------------
- Extracted final answers from model outputs using regex on \boxed{} format.
- Compared predicted answers with ground truth from OpenR1 Math dataset.
- Computed accuracy and error breakdown across baseline, SFT, and GRPO models.

--------------------------------------------------
📂 Repo Structure
--------------------------------------------------
.
├── data/               # Dataset scripts / preprocessing
├── models/             # Model checkpoints
├── scripts/            # Training & evaluation scripts
├── results/            # Logs, metrics, plots
├── requirements.txt
└── README.txt

--------------------------------------------------
✨ Key Takeaways
--------------------------------------------------
- GRPO is effective for reasoning alignment in LLMs.
- Even with limited GPU resources (Colab/Kaggle), small-scale experiments can show meaningful improvements.
- Pre fine-tuning helps stabilize GRPO by reducing formatting mismatches.

--------------------------------------------------
📌 Future Work
--------------------------------------------------
- Extend to larger reasoning datasets (e.g., GSM8K, MATH).
- Apply GRPO on multi-step reasoning tasks beyond math.
- Compare GRPO with other alignment methods like PPO or DPO.

--------------------------------------------------
🙌 Acknowledgments
--------------------------------------------------
- Qwen Team for the base model.
- OpenAI OpenR1 for the dataset.
- Kaggle & Colab for compute resources.
