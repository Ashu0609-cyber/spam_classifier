# spam_classifier

# 📧 GPT-2 Spam Classifier

A spam classification project that fine-tunes a pretrained **GPT-2 (124M)** model for binary text classification. The project uses the **SMS Spam Collection Dataset** and demonstrates how a Large Language Model (LLM) can be adapted for downstream NLP tasks using **PyTorch**.

> Instead of training a model from scratch, this project leverages transfer learning by replacing GPT-2's output head with a binary classification layer and fine-tuning the final transformer block.

---

## 🚀 Features

- Fine-tunes a pretrained GPT-2 (124M) model
- Binary classification (Spam / Ham)
- Uses transfer learning for efficient training
- Custom PyTorch Dataset and DataLoader
- Automatic dataset balancing
- Train, validation, and test split
- Model evaluation using accuracy and loss
- Predicts unseen SMS messages

---

## 🛠️ Tech Stack

- Python
- PyTorch
- GPT-2 (124M)
- tiktoken
- Pandas
- Matplotlib
- Jupyter Notebook

---

## 📂 Project Structure

```
spam_classifier/
│
├── Spam.ipynb                  # Complete notebook
├── train.csv                   # Training data
├── validation.csv              # Validation data
├── test.csv                    # Testing data
├── review_classifier.pth       # Saved fine-tuned model
├── README.md
```

---

## 📊 Workflow

```
SMS Dataset
      │
      ▼
Load Dataset
      │
      ▼
Balance Dataset
      │
      ▼
Train / Validation / Test Split
      │
      ▼
GPT-2 Tokenization
      │
      ▼
Custom PyTorch Dataset
      │
      ▼
Load Pretrained GPT-2
      │
      ▼
Replace Output Head
      │
      ▼
Freeze Most Layers
      │
      ▼
Fine-Tune Final Layers
      │
      ▼
Spam / Ham Prediction
```

---

## 📚 Dataset

The notebook automatically downloads the **SMS Spam Collection Dataset** from the UCI Machine Learning Repository.

- **Classes**
  - Ham (Not Spam)
  - Spam

The dataset is balanced before training to improve model performance.

---

## 🧠 Model Architecture

The project uses:

- Pretrained **GPT-2 Small (124M parameters)**
- GPT-2 tokenizer (`tiktoken`)
- Custom classification head
- Fine-tuning of:
  - Final Transformer Block
  - Final LayerNorm
  - Classification Head

Most GPT-2 parameters remain frozen, reducing training time while retaining pretrained language understanding.

---

## ⚙️ Training

Training includes:

- AdamW Optimizer
- Cross Entropy Loss
- Batch Training using PyTorch DataLoader
- Validation after regular intervals
- Model checkpoint saving

---

## 📈 Evaluation

The notebook evaluates the model using:

- Training Loss
- Validation Loss
- Training Accuracy
- Validation Accuracy
- Test Accuracy

It also visualizes:

- Loss Curve
- Accuracy Curve

---

## 💬 Example Predictions

### Spam

```
You are a winner! You have been specially selected to receive a $1000 cash prize.
```

**Prediction**

```
Spam
```

---

### Ham

```
Hey, are we still meeting for dinner tonight?
```

**Prediction**

```
Ham
```

---

## ▶️ Getting Started

### Clone the repository

```bash
git clone https://github.com/Ashu0609-cyber/spam_classifier.git
```

### Navigate to the project

```bash
cd spam_classifier
```

### Install dependencies

```bash
pip install torch pandas matplotlib tiktoken requests llms-from-scratch
```

### Run

```bash
jupyter notebook
```

Open:

```
Spam.ipynb
```

---

## 💾 Model Saving

After training, the fine-tuned model is saved as:

```
review_classifier.pth
```

which can later be loaded for inference without retraining.

---

## 🎯 Future Improvements

- Deploy using Streamlit or Gradio
- Support Email spam detection
- Multi-class text classification
- Fine-tune larger GPT models
- Compare with BERT and RoBERTa
- Export as REST API using FastAPI

---

## 👨‍💻 Author

**Ashutosh Thakur**

- GitHub: https://github.com/Ashu0609-cyber
- LinkedIn: www.linkedin.com/in/ashutosh-thakur-735673357

---

## ⭐ If you found this project helpful, consider giving it a star!
