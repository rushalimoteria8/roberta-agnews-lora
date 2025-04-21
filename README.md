# 🧠 RoBERTa AGNews Classification using LoRA (< 1M Parameters)

This project fine-tunes a frozen `roberta-base` model on the AG News dataset using Low-Rank Adaptation (LoRA), with under 1 million trainable parameters.

---

## 📌 Overview

This notebook demonstrates:
- Tokenizing the AGNews dataset using `RobertaTokenizer`
- Applying LoRA for parameter-efficient fine-tuning
- Training with Hugging Face `Trainer`
- Ensembling predictions from multiple models
- Exporting final predictions to CSV

---

## 🧠 Model Details

| Component           | Value            |
|---------------------|------------------|
| Base Model          | `roberta-base`   |
| LoRA Rank           | 6                |
| LoRA Alpha          | 32               |
| LoRA Dropout        | 0.05             |
| Trainable Params    | ~870K            |
| Task                | Sequence Classification |

---

## 🛠️ Training Configuration

- Epochs: 3  
- Optimizer: AdamW  
- Learning Rate: 2e-4  
- LR Scheduler: Cosine  
- Batch Size: 16 (train), 64 (eval)  
- Weight Decay: 0.01  
- Warmup Ratio: 0.1  

---

## 🤝 Ensemble Strategy

- Trained 3 models with different seeds
- Averaged logits across all models
- Final predictions from `argmax` over averaged logits

---

## 📊 Results

| Metric    | Value   |
|-----------|---------|
| Accuracy  | *94.2%* |

---

## 🛠️ Installation & Setup

### 1. Clone the Repository

```bash
git clone https://github.com/rushalimoteria8/roberta-lora-agnews.git
cd roberta-lora-agnews
```

### 2. Open in Google Colab (Recommended)

Instead of running locally, you can easily run the notebook on Google Colab:

1. Download the Jupyter Notebook (`.ipynb`) file from this repository.
2. Go to [Google Colab](https://colab.research.google.com/).
3. Click on **File > Upload Notebook**.
4. Select the downloaded `.ipynb` file.
5. Run all cells to fine-tune the model and generate predictions.

---

## 🤝 Contributing

Contributions are welcome!  
If you'd like to improve the model or add new features, feel free to open an issue or submit a pull request.

---

## 🪪 License

This project is licensed under the **MIT License**.  
See the [LICENSE](LICENSE) file for details.

---

## 🌟 Show Support

If you found this project useful, give it a star ⭐ on GitHub!  
Happy coding!
