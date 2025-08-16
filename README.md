# Qwen3_-4B--GRPO
Reasoning alignment of Qwen3-4B-Base using GRPO with Unsloth for efficient fine-tuning. Trained on the OpenR1 Math dataset via pre fine-tuning, SFT, and GRPO, achieving +14% accuracy on 2K math problems and reducing hallucinations vs. baseline and SFT-only models.

--------------------------------------------------
✨ Key Takeaways
--------------------------------------------------
- GRPO is effective for reasoning alignment in LLMs.
- Even with limited GPU resources (Colab/Kaggle), small-scale experiments can show meaningful improvements.
- Pre-fine-tuning helps stabilize GRPO by reducing formatting mismatches.

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
