# 🧠 Image Captioning with BLIP-2 and Flickr8k

This repository demonstrates how to use [BLIP-2](https://huggingface.co/Salesforce/blip2-opt-2.7b), a powerful vision-language model from Salesforce, for the task of **image captioning** using the **Flickr8k** dataset.

We explore two approaches for preparing captions and fine-tuning the model:

---

## 📂 Repository Contents

### 📘 `blip2-collected.ipynb`

- Groups all **5 captions per image into a single caption block**, separated by newline characters (`\n`).
- This approach helps the model learn diverse descriptions collectively for one image.
- Suitable when aiming for **context-rich captioning** or trying to represent all perspectives together.

> ✅ Best for scenarios where the full diversity of human annotation needs to be captured per image.

---

### 📘 `finetune-blip2.ipynb`

- Treats each caption **independently**, giving one caption per training sample.
- This significantly increases the number of training samples and focuses on **fine-grained learning**.
- Ideal for traditional supervised training where each image-caption pair is a distinct training point.

> ✅ Best for maximizing dataset size and training depth.

---

## 📦 Dataset Used

- **[Flickr8k](https://www.kaggle.com/datasets/adityajn105/flickr8k)**: A dataset of 8,000 images, each annotated with 5 textual captions.
- Captions are extracted from `captions.txt`, and image-caption mapping is constructed programmatically.

---

## 🚀 Getting Started

1. Clone the repository
2. Install dependencies:
   ```bash
   pip install -q git+https://github.com/huggingface/peft.git transformers datasets bitsandbytes
   ```
