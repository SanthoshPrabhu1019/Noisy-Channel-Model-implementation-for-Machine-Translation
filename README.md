#  Noisy Channel Model for Neural Machine Translation (NMT)


This project presents an implementation of a **Noisy Channel Model** for **Neural Machine Translation (NMT)**

---


## 📷 Demo Images

![Demo Image 1](./images/1.png)
![Demo Image 2](./images/2.png)
![Demo Image 3](./images/3.png)
![Demo Image 4](./images/4.png)
![Demo Image 5](./images/5.png)
---

## 📚 Implementation Based on Research Paper

**Title:**  
**Simple and Effective Noisy Channel Modeling for Neural Machine Translation**

**Paper Link:**  
[Facebook Research Paper (PDF)](https://arxiv.org/pdf/1901.11359.pdf)

---

## 🧾 Summary

This project is inspired by the research paper "Simple and Effective Noisy Channel Modeling for Neural Machine Translation" by Facebook AI Research. The paper introduces a framework designed to enhance neural machine translation (NMT) systems, particularly in low-resource scenarios, by leveraging the noisy channel model.

---


## 💡 Key Concepts

- **Noisy Channel Framework:**  
  Reformulates translation as the problem of maximizing the probability of the source sentence given the target, enabling more reliable translations even with limited data.

- **Channel Model:**  
  Predicts the source sentence from a given target sentence.

- **Language Model:**  
  Estimates the fluency and naturalness of the target sentence.

- **Beam Search Decoder:**  
  Integrates scores from the direct model, channel model, and language model to select the most probable translation.

- **BLEU Score**: Used for quantitative evaluation of translation quality.

---

## 🧩 Components & Architecture

#### 🔁 Direct Model (P(y|x))
A sequence-to-sequence Transformer model trained to translate from the source language (English) directly to the target language (Hindi).

#### 🔄 Channel Model (P(x|y))
A reverse sequence-to-sequence Transformer model that reconstructs the original English sentence from a candidate Hindi translation.

#### 📖 Language Model (P(y))
A standalone causal language model trained on a large Hindi corpus to promote fluent and grammatically correct output.

#### 🚀 Beam Search Decoder
An inference-time algorithm that:
- Generates multiple candidate translations using beam search.
- Computes a **combined score**:
  
  \[
  \text{Final Score} = \log P(y|x) + \alpha \times \left( \log P(x|y) + \log P(y) \right)
  \]

- Selects the candidate with the **highest combined score**.

---

### 📦 Project Overview

This project compares two approaches for English-to-Hindi translation:

**Direct Translation Model** – A standard sequence-to-sequence model that directly translates English to Hindi.

**Noisy Channel Model** – An improved method that selects the best translation by combining:
- Direct translation score  
- Reverse translation (channel model) score  
- Language model fluency score

The implementation provides:
- 🖥️ A command-line evaluation framework (via Jupyter Notebook)  
- 🌐 An interactive Streamlit web app for exploring translations and analyzing scores

---

## 🧰 Installation

```bash
git clone https://github.com/SanthoshPrabhu1019/Noisy-Channel-Model-implementation-for-Machine-Translation.git
cd Noisy-Channel-Model-implementation-for-Machine-Translation
pip install -r requirements.txt