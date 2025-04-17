
# WordSense: Fine-Tuned Mistral-7B for Contextual Vocabulary Assistance

**Author:** Nishanth Chockalingam Veerapandian  
**Course:** CS6120 – Natural Language Processing  
**Instructor:** Professor Uzair Ahmad

---

## Project Overview

WordSense is a fine-tuned large language model that identifies contextually difficult words in a passage and generates simple, concise definitions. Inspired by features available in e-readers like Kindle, this project aims to offer similar vocabulary support for traditional book readers and scanned text users, without needing access to commercial APIs.

The model is designed for integration into reading tools or developer-facing applications that offer real-time vocabulary assistance.

---

## Model

- **Base Model:** [Mistral-7B-Instruct-v0.3](https://huggingface.co/mistralai/Mistral-7B-Instruct-v0.3)
- **Fine-Tuning Technique:** LoRA (Low-Rank Adaptation) via [PEFT](https://github.com/huggingface/peft)
- **Frameworks Used:** HuggingFace Transformers, Datasets, PEFT, PyTorch

---

## Dataset

- **Total Samples:** 45,512
- **Annotation Source:** GPT-3.5 Turbo API
- **Corpus Sources:** Gutenberg, Brown, WikiText-103
- **Format:** JSONL (each entry contains a passage, difficult word, and its definition)
  
---

## How to Run

1. Download all required dependencies before running the code (standard Python ML/NLP libraries).
2. Ensure you have a `.env` file containing your OpenAI API key and HuggingFace (Mistral) token.
3. Run the main file:

```bash
python code.py
```
---
## Results

- **Training Loss:** 0.188800 (Epoch 3 checkpoint used for inference)
- **Evaluation Dataset Size:** 2,412 passages
- **Average Precision:** 0.45  
- **Average Recall:** 0.15  
- **Average F1 Score:** 0.21

---

## Future Work

- Swap GPT-3.5 annotations with Claude or Mistral-generated annotations for comparison
- Experiment with alternative base models (e.g., LLaMA, Falcon)
- Explore domain-specific tuning for legal, medical, and scientific texts
- Improve recall by expanding annotation strategies and training time

---

## Acknowledgements

- Project developed for CS6120 at Northeastern University under Professor Uzair Ahmad
- Annotations generated using OpenAI’s GPT-3.5 Turbo API
- Model development supported by HuggingFace Transformers, Datasets, and PEFT libraries
- Base model: Mistral-7B-Instruct-v0.3 by Mistral AI

---

## License

For academic and research use only.
